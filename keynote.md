# Where did React come from

Started in Ads org

Used classic models/event system.  But things became more complex.

Had to deal with cascading updates.

Overtime engineers couldn't keep in their heads what was causing these cascading updates to happen.  Code became unpredictable.

For a long time on FB the chat buddy list would just create a new string and use innerhtml to throw it in the DOM.  The mental model was right, but the performance and UX was problematic.

The like and comments experience was the first react application on facebook.com.

On the Ads side, they were building a complex app and there ended up being a lot of models that had to be managed.

Instagram wanted to use React, but at the time it was very coupled to the fb specific software stack.  Pete Hunt convinced them that it was worth it to decouple it.  And this was a lot of the work to make it open sourcable.  At JS Conf 2013 they announced it.  People paid attention until the JSX slide.

"Huge step backwards".  But internally this wasn't conterversial at all because they had been using XHP for years now.  It made XSS a thing of the past.  Most important piece was that it allowed them to create composite components.  It sent down markup and css and js necessary for the component.  And it would do the necessary data fetching.

React: Rethinking Best Practices.

Most powerful features?  Virtual DOM?  Server rendering?  Descriptive warnings?  Custom events system?  But all of these are possible because it replaces an imperative mutative API with a declarative one that favors immutability.

Delcarative --> predictable.  Predictable --> confidence.  Confidence --> reliability.

Ads create flow used to break multiple times a week.  It never goes down now that it's in React.  And they've added more features in less time.

React's real power is how it makes you structure your code.

A lot of frameworks have figured out that web components are the right seperation of concerns.  All the other methods force you to write imperative code to create components.  But React allows you to make declarative components.

Right now, React is only being used for web.  They've tried hybrid apps, but the reason it doesn't work is because building for native is different.

**Native:**

* Ability to parallelize work (and web workers are a crippled API)
* Sophisticated gesture handling
* Access to native capabilities/widgets

On native we might want to reimplement widgets sometimes.  But on web we're forced to.

Native environment is more powerful and flexible, at least today.  But it's more hostile to developers.

Adds a lot of development/infrastructure overhead.  Native environment is imperative.

From the beginning, React has been designed to replace any view system.

What if we take the same exact React JS that we've been running on the web.