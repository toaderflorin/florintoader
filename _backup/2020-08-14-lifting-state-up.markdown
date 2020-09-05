---
layout: post
title:  "Lifting State Using The useState Hook"
date:   2020-04-09 09:39:37 +0300
description: "
Lifting state up is a common pattern in React because it solves a simple problem: it simplifies the information and control flow when an action performed in one child component affects a sibling component.
"
icon: "closures/js.png"
categories:
---
Lifting state up is a common pattern in React because it solves a simple problem: it simplifies the information and control flow when an action performed in one child component affects a sibling component.

With class based React components, `setState` behaves differently. Whenever you are calling `setState`, the properties you are passing to the method get merged into the existing. It's worth mentioning that `setState` is async -- it merely tells React to schedule an update at the next available time at the next available time. 

But the fundamental difference between functional React and classic React is `setState` merges the new state properties at the particular moment when React.

With Hooks, `setState` replaces the whole state object so you have to do the JavaScript spread / property merge yourself.

A tenet of functional programming is you are never mutating existing instances of objects. You are merely creating new ones based on the old instance and changing some properties.

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
function App() {
  const [state, setState] = useState(initialAppState)
  
  async fetchData1(() => {
    const data1 = await api.getData1()
    setState({ ...state, data1 })
  })

  async fetchData2(() => {
    const data2 = await api.getData2()
    setState({ ...state, data2 })
  })

  return (
    <>
      <Child1 state={state} fetchData1={fetchData1} />
      <Child2 state={state} />
    </>
  )
}
</code></pre>
</div>

Because the functional component is a closure, it captures the value of the component state at the moment it was called by the React rendering engine. If fetching X took 5 seconds and in the user fetched Y, the component at that time will still keep a reference to the old state and it will cause the loss of the updates. One simple thing we can do is to separate the state into different variables, like this.

<div class="margin-bottom">
<pre><code class="language-js line-numbers">
function App() {
  const [data1, setData1] = useState(initialAppState)
  const [data2, setData2] = useState(initialAppState)
  
  async fetchData1(() => {
    const data1 = await api.getData1()
    setData(data1)
  })

  async fetchData2(() => {
    const data2 = await api.getData2()
    setState(data2)
  })

  return (
    <>
      <Child1 state={state} fetchData1={fetchData1} />
      <Child2 state={state} />
    </>
  )
}
</code></pre>
</div>

Of course, the problem with this is if your state is complex and hierarchical, having a lot of disjointed variables breaks your 