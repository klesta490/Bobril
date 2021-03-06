![Bobril Logo](https://raw.githubusercontent.com/Bobris/Bobril/master/logo.png)
Bobril
======

[![Join the chat at https://gitter.im/Bobris/Bobril](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Bobris/Bobril?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Version 3.6.0

Component oriented framework inspired by ReactJs (Virtual DOM, components with state) and Mithril (size, more complete framework). 
Easy automatic generation of code and its speed has higher priority over simplicity. Basically Bobril has most interesting features from ReactJs plus is faster, more complete, smaller, more polyfills for IE9. Isomorphic JavaScript is not implemented because it would increase size and is not needed for SEO anyway (Google bot supports JavaScript).
Because it is already used in Production code, further development must not broke any functionality. Any new feature must be optional or its perceived value to minified size ratio must be high enough.
If you need compatibility with IE8 look at 2.x branch.

Examples: http://bobris.github.io/Bobril/

See it in vdom-benchmarks: http://vdom-benchmark.github.io/vdom-benchmark/

Documentation: https://github.com/Bobris/Bobril/blob/master/src/bobril.md

Chrome plugin to help you to inspect running Bobril application: https://chrome.google.com/webstore/detail/clouseau/npfemnefhbkiahihigplihehpbgkbhbj
(Github source for it is here: https://github.com/klesta490/bobril-clouseau)

If you want to speed up your Angular app use: https://github.com/karasek/ngBobril

Available in npm as bundle of most interesting and useful plugins

Features in core:
- No additional dependencies
- Virtual DOM diffing
- Components remember state in VDom cache
- Components does not need to be HTML Elements - where is component(0-1) to HTMLNode(0-n) mapping (New in 2.0)
- Support for partial invalidates for even faster redraws (including recursion deepness limited new in 2.0)
- Normalization of Events
- support for IE9+, Android 4.1+ (Support for IE8 removed in 3.0)
- batching of redrawing
- any html element could be root
- automatic passing of global configuration/context to children
- automatic adding of "px" to length like inline style (New in 2.0)
- reference to children nodes ala React (New in 2.0)
- under 14kb minified (6kb gzip)

Features in extensions:
- OnChange event and value attribute normalization
- Key events
- Mouse, Touch and Swipe Events (includes polyfill pointerEvents:none and userSelect:none) (Swipe events not in bundle)
- Vector graphic in spirit of React-Art just very limited in features, but under 2kb with SVG backend (only SVG helpers in bundle)
- Router inspired by https://github.com/rackt/react-router/
- Media detection
- Focus, Blur, FocusIn, FocusOut events
- Transparently add vendor prefixes for inline styles
- Asap (setImmediate) and Promise A+ polyfill - simplified https://github.com/taylorhakes/setAsap and https://github.com/taylorhakes/promise-polyfill
- Scroll notification
- Drag and Drop - uses browser one except on IE9, multi touch, allows animating drag, state of the art as usual
- Style - create css dynamicaly for even faster speeed, allow recomputing styles for theming
- L10n - Localization + Internalization - behind uses format.io

All extensions + core are 46kb minified (20kb gzip)
Of course you don't need all extensions, it is pure a la carte, so actual application could be shorter.

Near term planned extensions:
- Style -> add more features sprites recoloring, build system around

Longer term extensions:
- New/Deleted Node animation (prototype in Router2 example)
- Prevent exit (Should be integrated with Router)
- Ajax (should mostly copy Mithril implementation)

Uses NodeJs, NPM, TypeScript 1.5 Beta, Karma, Jasmine, Coverage

MIT Licensed


How to develop
--------------

Use `npm up` to download all needed node modules.

For helping writing TypeScript you can use Atom.io with atom-typescript plugin. Compilation on save is disabled. So you have to work with gulp started in background.

Start `gulp` for TS compilation, minification and generating statistic for LibSize example.

`gulp compilets` force compilation of all TS files. It reads tsconfig.json files for information how to compile each subproject.

`gulp pages` upload examples to GitHub pages.

If you want to work on something create bug with description, so work is not duplicated.
