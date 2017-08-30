Angular Connect Lighting Talk
=============================

## "Let's componentize our brand!"

https://speakerdeck.com/mdo/build-your-own-bootstrap?slide=21

https://www.mozilla.org/en-US/styleguide/websites/sandstone/


## "...in Angular!"

left side: code file tree

```
 |- button.component.html
 |- button.component.scss
 |- button.component.spec.ts
 |- button.component.ts
```

right hand side: super duper picture of button


## Reach out!

publish to npm repository

```ts
import { ButtonModule } from '@my/brand';
```

Icon wall of tools: webpack, rollup, gulp, angular CLI, ember CLI, system.js

then fade in as last icon: bazel - uh, ah! yet another one!


## And then came Angular Package Format

screenshot of document beginning: https://docs.google.com/document/d/1CZC2rcpxffTDfRDs6p1cfbmKNLA6x5O-NtkJglDaBVs/preview

Purpose of Angular Package Format: is compatible w/ most build tool chains.


## Mamma mia! Here we go again!

rollup, scss, less, browserslistrc, tsc, ngc, AoT, FESM'15, module, typings, main, and on and on and on...


## I came for you!

the only slide on ng-packagr :-)

record an animated gif showing...

```
$ yarn add --dev ng-packagr
// edit ng-package.json
// create package.json
$ yarn package
// show file tree w/ generated dist folder
```
