Angular Connect Lighting Talk
=============================

## "Let's componentize our brand!"

https://speakerdeck.com/mdo/build-your-own-bootstrap?slide=21

https://www.mozilla.org/en-US/styleguide/websites/sandstone/

## "...in Angular!"

```html
<ng-datepicker>

<button ngButton>

<ng-tabs>
  <ng-tab></ng-tab>
</ng-tabs>
```


```bash
npm publish
```

```ts
import { ButtonModule } from '@branded/components';
```

## Angular Package Format

Distribute sources? No good.
Build tools are complex: JavaScript module formats, TypeScript declaration files, AoT metadata, ...

#### left side: code file tree

```
|- button
|  |- button.component.html
|  |- button.component.scss
|  |- button.component.spec.ts
|  |- button.component.ts
|- public-api.ts
```

#### right hand side: dist artefacts

```
.umd.js
.es5.js
.es2015.js
.metadata.json
.d.ts
```

Design Doc / Spec:
https://docs.google.com/document/d/1CZC2rcpxffTDfRDs6p1cfbmKNLA6x5O-NtkJglDaBVs/preview

Purpose of Angular Package Format: is compatible w/ most build tool chains.
E.g. `es5.js` for webpack / ng CLI.
`umd.js` for module loders, e.g. SystemJS.

Packaging Angular - Jason Aden at ng-conf:
https://youtu.be/unICbsPGFIA

#### but wait...

_(fade in in the middle)_

Icon wall of tools: webpack, rollup, gulp, angular CLI, ember CLI, system.js

then fade in as last icon: bazel - uh, ah! yet another one!

and fluxbox!

Configuratioon needed for a lot of tools

(rollup, scss, less, browserslistrc, tsc, ngc, AoT, FESM'15, module, typings, main, and on and on and on...)

## Give ng-packagr a try!

(play gif on this slide)

```
$ yarn add --dev ng-packagr
// edit ng-package.json
// edit package.json
$ yarn package
// show file tree w/ generated dist folder
```

## Pros and Cons

`ng-packagr: (publicApi: TsFile) => NgPackageFormat`

 - It's an opinionated tool
   - less configuration (_"best practice"_)
   - _"tool orchestrator"_ for rollup, ngc, scss, less, stylus, ...
 - Can be used alongside `ng` CLI or other build tools
 - Secondary entrypoints (like `@angular/cdk/portal`)

#### Drawbacks

 - It's an opionated tool
   - less configuration (do you need complex, highly-customized build scripts?)
 - Issues w/ some 3rd party dep's ([#101](https://github.com/dherges/ng-packagr/issues/101), [#129](https://github.com/dherges/ng-packagr/issues/129))

## Closing Slide

(contact)


---

##### Backup slide

screenshot of 227 lines of gulpfile.js

rollup, scss, less, browserslistrc, tsc, ngc, AoT, FESM'15, module, typings, main, and on and on and on...

`ng-package.json`
