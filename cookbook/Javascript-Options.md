Yesod by default gives you Shakespearean Javascript, also known as Julius. It is just Javascript that you can insert Haskell (JSON) values into. Also Shakespearean Coffee and Shakespearean Typescript. Coffeescript is a thin veneer that papers over Javascript to make a convenient and consistent language, but there is still no type system. TypeScript adds a type system and compiles down the latest Javascript standard to an older version. It is likely the easiest way to get some types into your Javascript, although its type system does allow anything to be null.

There is prior art for Julius: [jmacro](http://hackage.haskell.org/package/jmacro-0.5.1) has QQ value insertion, but also supports a haskell-ish version of javascript.


## Using Javascript Frameworks

The most robust and portable approach is to use one of the above javascript template tools and integrate with an existing javascript framework.

* AngularJS
* [Montage](http://hackological.com/blog/?p=5)
* ReactJS (Note: [Hom](https://github.com/arianvp/Hom) ReactJS for Haskell
* [Virtual DOM Bindings](https://github.com/ghcjs/ghcjs-vdom) may be worth looking at


## Compile Haskell

Fay is a new alternative that we would love to hear some experience reports about.

* [Fay, Haskell code translated to JS](http://fay-lang.org/). Upside: produces a small amount of understandable javascript. Downside: only a subset of Haskell is supported.
* [UHC js compiler](http://www.haskell.org/haskellwiki/The_JavaScript_Problem#UHC). Downsides: alpha, not completely integrated with cabal, not GHC.
* [ghcjs](https://github.com/pedromartins/ghcjs) - [example Yesod app](https://github.com/hamishmack/yesod-slides) - directly compile ghc core to javascript. Downside: produces large amounts of javascript.
* [PureScript](http://www.purescript.org) - small, stronly typed, very similar to Haskell. Downside: not actually Haskell. Maybe worth looking at [Purescript Virtual DOM](https://github.com/purescript-contrib/purescript-virtual-dom) , similar FRP-style thing to ReactJS.

### Alternative experimental ways to compile Haskell

* [Emscripten](https://github.com/kripken/emscripten) — compiles LLVM/Clang output to JavaScript. If you use features of the GHC runtime you also have to compile it, which nobody has made an effort to figure out.
* [PNaCL](http://www.chromium.org/nativeclient/pnacl) - run native code on Google Chrome with NaCL. PNaCL is the next generation that will run LLVM byte code. Won't work on other browsers.
* [JS Haskell interpreter](https://github.com/johang88/haskellinjavascript)


## A Haskell-like language that only compiles to Javascript

We would really like to hear about your experience with Elm or Roy, which are 2 nice options with Yesod integration.

* [Elm](http://elm-lang.org/) - Yesod integration available. Haskell inspired language that also offers an FRP GUI. Downside: not quite Haskell, not Javascript.
* [Roy](http://roy.brianmckenna.org/) - Yesod integration (Roy templates) available. Javascripty semantics with Haskelly features. Project is starting to mature. Upside: should be easier to use with existing JS than many other alternatives. Downside: not Haskell.
* [lambdascript](https://github.com/valderman/lambdascript)
* [Forml](http://texodus.github.io/forml/) - Haskell-inspired syntax & type safety with Ruby-inspired expresiveness


## Haskell code that explicitly generates Javascript

* [Reactive-banana](http://apfelmus.nfshost.com/blog/2012/05/15-frp-banana-0-6.html) - an FRP GUI framework can now output html/javascript
* [Panther-Ajax](http://osdir.com/ml/general/2011-06/msg41431.html) Experimental library to write server side code that accesses the dom and uses continuations.
* [Ji](https://github.com/chrisdone/ji) - experimental library not currently working with Yesod. Same as Panther-Ajax, but under active development.
* [HJScript](http://hackage.haskell.org/package/HJScript-0.5.0) - javascript DSL.
* [yesod-js](https://github.com/snoyberg/yesod-js.git) - currently stalled while investigating Fay/Elm/ghc-js




## Other strongly typed functional languages that compile to Javascript

* [Ur/Web](http://impredicative.com/ur/demo/) - A Haskell-like programming language tailored to web programming. Automatically generates FRP javascript code. Appropriate for taking the FRP plunge, but Heavyweight (large library and difficult to debug) if you just want some strongly-typed JS. [Opa](http://opalang.org) is a very similar concept.
* [JS of OCaml](http://ocsigen.org/js_of_ocaml/) - There is also an in-browser OCaml bytecode interpreter!