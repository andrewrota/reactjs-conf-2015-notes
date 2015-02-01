Web workers: the plan is experimental at this point and the architecture is slightly different than native.

React was originally built in standard ML.  Jordan couldn't get it to work so he used JS instead.

You can take the ideas of React and put them in other environments.

Server side rendering is pretty bad.

Relay: there are multiple modes for the web version.  In the normal mode everything is read on the client but it would require a seperate trip to the server for data.  SO they run it on the server to generate the query to start with, and send the js to the client and the data you already have fetched.  In the other mode there is server rendering as well so you get the markup and data for the page.

Server rendering: it wasn't actually desiged that way [in react].  Just happened to be the fastest way to implement it on the client was the simplest on the server.  We don't use server rendering that heavily.  There's a lot of things that can be done there.  Autobinding comes at some cost.  Things we can do by ignoring any state that gets set up in continuous loops.

Context: we told you they would find it.  It will stick around.  There's a warning in 0.13 that says if you're using it from the owner instead of the parents.

Viewer: see profile from perspective of another users.  Built with XHP using context.  Understanding difference between who's logged in, who's viewing the profile, who can do what, etc.  Realized it was just a subtree of the UI.  Focus and selection are two interesting global states, but currently you need to work very imperatively to use focus(), etc.  Eventually this could be implemented with context.

Plan for supporting new OS features: two approaches to every component.  Wrap or reimplement.  There are cases where you want to reimplemente.  The tab bar at the bottom of the facebook os app is actually reimplemented.  Wrapping is more flexible if public API doesn't change.  Any time there's an OS update you need to update your app to get it to look like it.  So you never get it for free.  But this is different because you can choose to reimplement or to simply wrap and get the upgrade cheaper.  React native shouldn't just be as fast, it should be better to work with.  Reimplementing gives you an opportunity for building a more declarative API.

Upgrade path between iOS and Android.   Certain views only exist in one platform.  So if you want to port iOS to Android you can swap in the reimplementation on Android which gives you a sort of working model so you can incrementally update your app.

Mixins?  In ES6 there was a plan to implement hooks for mixins.  No one knows how to do it well.  There's no standard.  ES6 needs to be standarized and finalized.  All those things were ripped out of the spec, so there's no nice way to do it in ES6.  But it's being pushed as a high priority in ES7.  We will get mixins back in ES, and they're not going away in React.  Mixins are a great way to experimentally add features not in the framework.  But a lot of the features should be built into the framework and then there are better ways to use them.

tl;dr: Continue using mixins until there's a better solution.

"We don't use webpack for Facebook.com"  We use 'haste' (package manager) and 'makehaste'.

Internationalization transformations, graphQL transformations.

Packager uses machine logging.  Log production data from CDN on what packages are requested.  Figure out what next week's site is going to need based on that.  Packager has going through a bunch of iterations.  Cache wasn't a huge performance advantage.  Profile pics invalidated browser caches a while back.

Packaging JS for react native is different then for the web.  For native it's more about developer experience.

In Relay you can defer queries.

Experimenting with caching with Relay (save to the client on disk)

Keystone: best looking and feeling implementing of webview



