# Angular ScrollSpy

[![Build Status][travis-badge]][travis-badge-url]
[![Coverage Status][coveralls-badge]][coveralls-badge-url]

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.5.4.

A simple lightweight library for [Angular (2/4+)][angular] which automatically updates links to indicate the currently active section in the viewport. Requires [Angular Inviewport][angular-inviewport] to be installed as well.

This is a simple library for [Angular][angular], implemented in the [Angular Package Format v5.0](https://docs.google.com/document/d/1CZC2rcpxffTDfRDs6p1cfbmKNLA6x5O-NtkJglDaBVs/edit#heading=h.k0mh3o8u5hx).


## Install

`npm i @thisissoon/{angular-scrollspy,angular-inviewport} --save`

`app.module.ts`
```ts
import { InViewportModule, WindowRef } from '@thisissoon/angular-inviewport';
import { ScrollSpyModule } from '@thisissoon/angular-scrollspy';

// Provide window object for browser and a suitable replacement
// on other platforms
const getWindow = () => window;
const providers: Provider[] = [
  { provide: WindowRef, useFactory: (getWindow) },
];

@NgModule({
  imports: [
    InViewportModule.forRoot(providers),
    ScrollSpyModule.forRoot()
  ]
})
export class AppModule { }
```


## Example

A working example can be forund in the [src](https://github.com/thisissoon/angular-scrollspy/tree/master/src) folder.

`app.component.html`

```html
<ul role="navigation" snScrollSpy id="foo">
  <li><a snScrollSpyItem for="foo" href="#section1">Section 1</a></li>
  <li><a snScrollSpyItem for="foo" href="#section2">Section 2</a></li>
  <li><a snScrollSpyItem for="foo" href="#section3">Section 3</a></li>
  <li><a snScrollSpyItem for="foo" href="#section4">Section 4</a></li>
</ul>

<sn-scroll-spy-section id="section1" for="foo">content goes here</sn-scroll-spy-section>
<sn-scroll-spy-section id="section2" for="foo">content goes here</sn-scroll-spy-section>
<sn-scroll-spy-section id="section3" for="foo">content goes here</sn-scroll-spy-section>
<sn-scroll-spy-section id="section4" for="foo">content goes here</sn-scroll-spy-section>
```

`app.component.css`

```css

a {
  color: blue;
  transition: color .2s ease-in-out;
}

a.active {
  color: darkblue;
}
```


## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).



[travis-badge]: https://travis-ci.org/thisissoon/angular-scrollspy.svg?branch=master
[travis-badge-url]: https://travis-ci.org/thisissoon/angular-scrollspy
[coveralls-badge]: https://coveralls.io/repos/github/thisissoon/angular-scrollspy/badge.svg?branch=master
[coveralls-badge-url]: https://coveralls.io/github/thisissoon/angular-scrollspy?branch=master
[angular]: https://angular.io/
[angular-inviewport]: https://github.com/thisissoon/angular-inviewport/
