Previous title was on the future of layout systems: GSS is probably not the answer though.

Shared mutable state is the root of all evil.

Classic DOM manipulation / data technique is problematic.  Solution: observable data model.  No more DOM ops.  Still a problem: handle multiple data questions in multiple actions.  Becomes more complex with more features.

Flux helps by putting all the actions in the stores and only answer one question there.

What about the backend?

Similiar problems when building backend services as well.  Cache invalidation.  But if you want to ask a new question of your data you need to implemment a new accessor and cache it separately.

What would a server side flux implementation look like that would solve this for us?

A flux store is a reduce() + a change event.  Takes in a log of every event and returns current state.

Derived data: search indexs, caches, data warehouses, DB shards, etc.

Your app == derived data  ...using the history of every action that ever happened.

Process every action for every query request.  Sound like a good idea?  Can we make it fast enough? (the real question)

Action --> Message Broker --> Stores listening on that message queue

A message queue is equivalent to a dispatcher.  But a MQ in a distributed system has to be fast, durable, shardable, compactable, cheap.

A store is a little bit of code and some piece of state.

Lots of advantages:  Data is always warm.  Sharding is easy.  Rebuilds and migrations are easy (disposable stores...just replay the messages the queue received).  Manage trade-offs of your data store granularly.

Make as many servies as stateless as possible.  Push state into distributed message queue.

Choose the best data store for your question at the current point of the lifecycle of the project.  Concerns: write latency, read latency, query flexibility, costs, durability.  We can manage these tradeoffs.

This is an attractive way to build systems today.

Stores can emit change events too.  That's part of how flux works.  So rather than asking stores on the server what the value of a query, we subscribe to queries and ask to be told when the result of the query changes

Action --> MQ --> getItem(id) --> App --> Action --> Dispatcher --> App --> Repeat.  Adjust tradeoffs at each component.

Some things didn't work too well: Communcation between stores doesn't work in a distributed system.  waitFor() doesn't work.  Best solution is to enrich data and set up our system as a DAG (directed async graph).