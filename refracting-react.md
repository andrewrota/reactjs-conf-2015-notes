People make judgments simply because they don't have the information to process it so they immediately dismiss it.

It's important to not pass judgment until you've taken the time to assess the thing.

We often are building smaller systems and then we look at the crazy big systems that someone else built, and think those are built on different rules.

Big != complex.

Ember, backbone, angular: all didn't work out for the same reason.  React won out in a huge way.  All for one reason: mutability is an implementation detail in React.

Om was an experiment.

"How do you hide the entire world from everybody [in an immutable model]?"  Om uses slices from a piece of the app state.  Relatively nice.  Doesn't solve everything.

based on zippers/lenses in frp

"Not everything is awesome." - Rich Hickey

Usually when something is awesome, there's something not awesome about it too.

60% of the time the waterfall model is fine.  But there are a few cases when you need to swim in another direction.

Flux: "Here's one way, because we're not sure yet what the right way is."

There's nothing fundamentally wrong with observation.  We already do this with event handlers on DOM elements.

Reference cursors allow Om components to listen to data structure changes as you would a virtual DOM element.

Reference cursors are not two way data binding.  List of observed path, no explicit calling of anything, no messaging.  Don't have the events problem.

After normal render of the component tree from the root, walk list of reference cursors to see if they've changed (like an extra compiler pass).  If it changed, we forceupdate.

Serializable app state - very cool.

Interesting UIs are inherently complex.  Doesn't mean there aren't ample opportunities to discover incidental complexity.  A lot of times we assume "that's just how it is."

React is moving from a DOM virtual machine to a UI virtual machine.