# AngularAttributeDirectives

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 11.2.8.

ng generate directive highlight

The CLI creates src/app/highlight.directive.ts, a corresponding test file src/app/highlight.directive.spec.ts, and declares the directive class in the AppModule.

To use the HighlightDirective, add a <p> element to the HTML template with the directive as an attribute

<p appHighlight>Highlight me!</p>

detect when a user mouses into or out of the element and to respond by setting or clearing the highlight color.

Import HostListener from '@angular/core'
import { Directive, ElementRef, HostListener } from '@angular/core';

Add two event handlers that respond when the mouse enters or leaves, each with the @HostListener() decorator

@HostListener('mouseenter') onMouseEnter() {
  this.highlight('yellow');
}

@HostListener('mouseleave') onMouseLeave() {
  this.highlight(null);
}

private highlight(color: string) {
  this.el.nativeElement.style.backgroundColor = color;
}

With the @HostListener() decorator, you can subscribe to events of the DOM element that hosts an attribute directive, the <p> in this case.

The handlers delegate to a helper method, highlight(), that sets the color on the host DOM element, el.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
