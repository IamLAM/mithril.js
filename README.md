# Mithril.js - A framework for building brilliant applications

Note: This branch is a sneak peek for the upcoming version 1.0. It's a rewrite from the ground up and it's not backwards compatible with [Mithril 0.2.x](http://mithril.js.org)

This rewrite aims to fix longstanding API design issues, significantly improve performance, and clean up the codebase.

## Status

Code still is in flux. Most notably, components and thunks (`{subtree: "retain"}`) are currently not implemented yet and there are several use cases that still need to be polished. DO NOT USE IN PRODUCTION YET!

Some examples of usage can be found in the [examples](examples) folder. [ThreadItJS](examples/threaditjs/index.html) has the largest API surface coverage and comments indicating pending issues in framework usability. Note that the APIs those examples use may not become the final public API points in v1.0.

## Performance

Mithril's virtual DOM engine is now less than 400 lines of well organized code and it implements a modern search space reduction diff algorithm and a DOM recycling mechanism, which translate to top-of-class performance. See the [dbmon implementation](http://cdn.rawgit.com/lhorie/mithril.js/rewrite/examples/dbmonster/mithril/index.html) (for comparison, here's dbmon for [React v15.0.2](http://cdn.rawgit.com/lhorie/mithril.js/rewrite/examples/dbmonster/react/index.html) and [Angular v2.0.0-beta.17](http://cdn.rawgit.com/lhorie/mithril.js/rewrite/examples/dbmonster/angular/index.html)).

## Lifecycle methods and Animation Support

Mithril's `config` method is now replaced by several lifecycle methods to improve separation of concerns and allow better control over animations.

## Robustness

There are over 1800 assertions in the test suite, and tests cover even difficult-to-test things like `location.href`, `element.innerHTML` and `XMLHttpRequest` usage.

## Modularity

Despite the huge performance improvements, the new codebase is smaller than v0.2.x, currently clocking at 4.5kb min+gzip

In addition, Mithril is now completely modular: you can import only the modules that you need and easily integrate 3rd party modules if you wish to use a different library for routing, ajax, and even rendering
