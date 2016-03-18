# Angular Custom Directives

* Step your game up

* What is a custom directive?
  * directives allow us to express custom functionality through custom HTML lags and attributes
  * directives essentially take semantic markup to a whole new level
  * Directives are similar to components in react
  * They are very powerful but hard to learn
  * When you register directives, you return an object, called the Directive Definition Object, that contains configuration properties such as controller, link, transclude, require, etc.

* When should I use one?
 * anytime you need to manipulate the DOM in a way t that cannot be accomplished with Angular's build in directives (ng-if, ng-repeat, etc.)
 * Anytime you want to create reusable functionality (a navigation bar that will exist throughout most of the site)

* Live code
 * directives have to return an object
 * called the directive definition object
 * if something in your directive is going to be updating the DOM, you need to tell the directive to run angular's digest cycle (scope.$apply)

 * Shared vs Isolate Scope
  * You want to use isolate scope
