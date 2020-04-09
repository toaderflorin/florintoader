---
layout: post
title:  "Reactivity, Immutability And Reconciliation In React"
date:   2020-04-02 09:39:37 +0300
description: "
Before getting into library-specific details, it's worth starting with a definition of what constitutes reactivity. A typical example would be an Excel spreadsheet: if a cell aggregates data from other cells, that cell instantly changes if we change a value in any of the aggregated cells. In reactive programming, if a variable A depends on B and C, a change in either B or C would also trigger a change in A.
"
icon: "reactivity/reactivity-icon.png"
categories:
---
Before getting into library-specific details, it's worth starting with a definition of what constitutes reactivity. A typical example would be an Excel spreadsheet: if a cell aggregates data from other cells, that cell instantly changes if we change a value in any of the aggregated cells. In reactive programming, if a variable A depends on B and C, a change in either B or C would also trigger a change in A. While there seems to be an ongoing debate whether React is truly reactive, there's no doubt that the UI reacts to changes in the data model, even if parts of the model itself don't react to other parts being changed, so from now on we'll consider this definition of reactivity.

Since in most programming languages mutating an existing instance doesn't notify other objects or the runtime of the change, a typical pattern is to use events or callbacks for this. As an example, Windows Presentation Foundation uses models that implement an interface called
<span class="code">INotifyPropertyChanged</span> for data-binding and wraps class fields in getters and setters, and it's the setter's responsibility to fire change events. .NET provides a convenient base class object that implements the interface, so a typical observable view model would look like this:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
public class ObservableViewModel: ObservableObject 
{
  get Field1 
  {
    _field1 = value;
    NotifyPropertChanged('field1');
  }
  set
  {
    return _field1;
  }
}
</code></pre>
</div>

The WPF rendering system receives these events and then uses .NET's reflection system to read the properties that are named like that. So if you are passing a different string in the notify event, it won't work. 

VueJS does something similar, but it's a little bit less transparent; it looks at the model the component was initialized with and then wraps the existing fields in getters and setters that also notify it. These wrappers aren't directly visible to the user, which is why it is crucial to understand what the library does under the hood — adding a property to the model that wasn't present when the component was initialized means that property isn't observable.

Directly from the VueJS documentation:

![diagram2](/images/reactivity/vue-reactivity.png){:class="img-responsive"}

Mutations play a central role when it comes to observability in these libraries, but React works a little bit differently because it is much more functional in nature. 

## React
Rendering in React is done by calling the <code class="code">setState()</code> method on a component, or that component receives new props from a parent and here's the important aspect: React always rerenders the whole subtree, unless we override the <code class="code">shouldComponentUpdate()</code> method in the class and tell it not to.

If we wanted to only rerender if something is changed, we would have to deeply compare the new props and state to the old ones which can be time consuming. But by using a little functional trick called *immutability* in our code, we can avoid this and use a shallow compare instead.

Let us use the typical task manager example and look at the following code:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
const taskA = {
  id: '4b390f82-8b6f-4176-b28e-455ce9c24150',
  text: 'Send email to John.',
  completed: false
}

const taskB = {
  id: '32557639-ca7a-4188-868a-2b5938d2bd01'
  text: 'Play foosball.',
  completed: false
}

const taskC = taskA

console.log('This should be false.', taskA === taskB)
console.log('This should be true.', taskA === taskC)
</code></pre>
</div>

This, of course, is nothing new because JavaScript doesn't check the values of the fields, it checks the instances and in the case of person A and B we have two different instances of an object with fields of equal value. 

Let's say we now have a method that is called <code>removeLastName()</code>. In the case of mutable languages we could write something like this:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
function completeTask(task) {
  task.completed = true
}
</code></pre>
</div>

But functional languages prohibit mutations, and even if JavaSript allows them, if we want to abide by functional principles, we can write it like this instead:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
function completeTask(task) {
  return {
    text: task.text,
    completed: true
  }
}
</code></pre>
</div>

Since we are never mutating an existing object, checking for value equality reduces to instance equality checking. React also provides the concept of [pure components](https://reactjs.org/docs/react-api.html#reactpurecomponent) that automatically do a shallow compare on props and state, so we don't have to provide our own <code class="code">shouldComponentUpdate()</code> implementation.

Quite often, beginner React developers write code like this:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
updateTask = (id, newText, completed) => {
  const tasks = this.state.tasks
  const existingTask = tasks.find(task => task.id === id)
  
  if (task) {
    existingTask.text = newText
    existingTask.completed = lastName

    this.setState({
      tasks
    })
  }
}
</code></pre>
</div>

*Remember: never mutate the component state directly.*

<code class="code">setState()</code> works asynchronously and it can be interpreted as a request to React to queue an update to the component at the next available moment in the rendering loop. Also internally, <code class="code">setState()</code> doesn't modify the state, it creates a new instance, just like our previous <code class="code">completeTask()</code> function did. So we need to do something else instead.

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
updateTask = (id, text, completed) => {
  this.setState({
    persons: [...state.persons, persons: state.persons.map(task => 
      task.id ===  action.id 
        ? { ...task, { completed: !task.completed} } 
        : task      
    })
  })
}
</code></pre>
</div>

This ensures updating works.

## Redux
Redux is in some ways similar to the concept of [lifting state up](https://reactjs.org/docs/lifting-state-up.html), but instead of lifting it up to a parent component, we push it to a single shared store. Architecturally, an application that uses both React and Redux looks like this:

![diagram2](/images/reactivity/react-redux.png){:class="img-responsive"}

Let us first review its three central tenets.

1. Redux is the single source of truth of the application.
2. The Redux state is read-only.
3. Changes to the state are made with pure functions.

While there is some debate about whether we should fully and dogmatically stick to number one, the second and third principles are universally accepted. A reducer is simply a function that takes the initial value of the state, an action object (that contains some parameters) and returns a new state based on that action.

Based on them we would write our reducer like this:

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
const ADD_TASK = 'ADD_TODO'
const TOGGLE_TASK = 'TOGGLE_TASK'
const CLEAR_TASKS = 'CLEAR_TASKS'

const tasksReducer = (state = [], action) => {
    case ADD_TASK: {
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    }
    
    case TOGGLE_TASK: {
      return state.map(task => 
        task.id ===  action.id 
          ? { ...task, { completed: !task.completed} } 
          : task      
      })
    }

    case CLEAR_TASK: {
      return []
    }
    
    default: {
      return state
    }
  }
}
</code></pre>
</div>

A pure function is a function is that: 

1. For a set of input parameters *always* returns the same result, so it's predictable. So if a function depends on a subset of the global state or the current time, it is not pure.
2. Doesn't have any *side-effects*. A side-effect might be mutating one of the input parameters, for example.

*It's worth noting that making calls to a backend service is definitely considered a side-effect, and it shouldn't be part of a reducer. There is a special way to handle that in Redux, but it's beyond the scope of this article.*

Another thing worth mentioning is that Redux is a standalone datastore, so we don't necessarily have to use it with React. When used with React, a library called redux-connect is used which passes down Redux state as props to the components that subscribe to it. 

## Reconciliation And The Virtual DOM
Whenever <code class="code">setState()</code> is called in a component, or it receives props from a parent component (or Redux), rerendering takes place. Of course, just replacing elements DOM elements as we've done for the component state not only would be slow but would also cause issues with controls losing focus and other artifacts.

Because of this, React creates a virtual copy of the DOM in memory. <code class="code">setState()</code> only triggers a process that marks the affected nodes in the VDOM as dirty, and then there's a *reconciliation process* that takes care of updating the actual DOM based on deltas.

In a nutshell, this process works like this:

1. Diffing is recursive and starts at the root of the DOM / VDOM.
2. If a node isn't marked as dirty in the VDOM, nothing happens to the corresponding node in the DOM, and React doesn't traverse the child nodes.
3. If the node is marked as dirty, the diffing algorithm looks at whether the type has changed. If the node has gone from a <code class="code">BlogPost</code> to a <code class="code">WarningMessage</code> component, or from a button to a div, the whole subtree (including children) is recreated. React doesn't try to reuse the existing DOM elements (by transplanting them as children them to the newly created element) because even if that were possible, it would be to slow to figure out which ones can be kept.
4. If, however, the type hasn't changed, only the properties (like text, width, etc.) and the children will be evaluated and updated if needed.
5. When it comes to lists, React needs a little help in the form of keys. Because elements can move up and down in order, using the index is not reliable for comparison. It is recommended we set the key to a stable value, such as the UUID of the underlying data model.

## Summary
React can be very fast, but knowledge about how it works under the hood is essential. Not understanding the inner workings of <code class= "code">setState()</code> can lead to issues with updating, and the same thing goes with setting inappropriate keys on list items. Understanding immutability, pure functions, and components can also provide a significant performance boost.

