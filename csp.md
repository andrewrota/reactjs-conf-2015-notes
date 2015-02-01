**Channels and Communicating Sequential Processes**

Simplifies async operations and complex workflows.

js-csp project implements channels in JavaScript

Higher order operations: mult, mix, merge, pipeline

A transducer can be passed through a channel.  Transducers are awesome.

Why isn't this used?  Generators not available until recently.  Susceptible to deadlocks.

Advantages: composability of event flows, cursor abstraction removes need for emitting change events, potential global app state structure, component subscribing to events
