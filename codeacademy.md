Had an opportunity to rewrite the frontend for product reasons

https://www.youtube.com/watch?v=U5yjPG5mHZ8

Started by rtfm.  Took a while to figure out how to think in React.

Big, single page app.  Lots of feedback that needs to be given to the user.  Not enough just to communication down the tree.  Docs at first just said callbacks everywhere.  "Just use callbacks" wasn't good enough to move up and across the component tree.  Most of the communication needs were pretty basic, though.  A lot was just responding to user action on the client.

**Adapters** - parent component always has one.  Built based on major components present.  Listens to communication "Events" broadcasted by components.

Code Academy built a communication system for #reactjs in 120 lines of code.
