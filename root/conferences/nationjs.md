NationJS Notes
==================================

Kyle Simpson

http://54y.geti.fi/slides
@getify

New Rules for javascript

youdontknowjs.com

Kyle's new rules
* stop thinking js doesn't have types
* stop thinking variables have types
    * values have types, variables can hold different value
* stop thinking == is bad
    * use == when you want coercian
    * useful feature in some cases, but only if you know what you're doing
    * never treat null and undefined as different values
        * more verbose (a === null || typeof a === "undefined")
        * more performant
* stop using anonymous functions!
    * name the functions:

        $("").click(function handler(event) {...})
        (function IIFE() {...})
    * stop bloating function closures
    * don't assume it will be optimized
* stop abusing your functions scope
    * getting block scoping in ES6 (let statement)

        let (e) {
            e = 12 * 6;
        }
    * try catch is actually block scoped

        try{throw void 0;}catch
        /*let*/(a) {

        }
    * let is not the new var (only use where block scoping is wanted)
    * let loops!
* stop using this until you understand how it works
    * find the call-site
    * var self = this is often just misguided (a smell)
        * use bind
    * fat arrow functions are coming in ES6
        * doesn't obey this rules
        * don't mix styles
* stop using new Someting(), "constructors" to "instantiate" and "inherit classes"
    * OO vs. OLOO
    * don't call it prototypical inheritance (doesn't work at all like inheritance)
    * complicated
    * delegation oriented
    * think of objects and tasks. If an object can't handle a task, it delegates
      to the next

John K. Paul - Strong Type System Withdrawal
johnkpaul.com

* Tools to catch typos
    * esprima, grunt-jsvalidate, Google Closure
    * IDE can do that
    * linting, catches common semantic mistakes
    * use "use strict"!
    * complexity - cyclomatic complexity is a measure of code paths
        * somewhere between 3 and 8 is normal
        * tools: JSComplexity and Plato
            * maintainability index
        * Plato looks really nice (nice complement to istanbul code coverage)
    * beautification
        * Editor Config
        * code painter - generate config file based on source
        * js-beautify ***
        * esformatter ***
    * Enforcement
        * svn pre commit hooks

Pam Selle (thewebivore.com)

Prototyping
* If you make it pretty, they'll focus on the pretty and not on the function
* not first iteration of the project
* many prototyping tools are built for those who "don't know how to code"
* Express - web app framework (analogous to sinatra in ruby)
    * routes, requests and views
* U's of usability
* You are not your user's audience
* Test early, watch for:
    * Look for heuristics violations (rule of thumb)
    * Look for anger
    * People will try and make you happy, diffuse that, talk out loud
    * Don't do what people say


Brian McKenna (Functional programming)

* Design patterns vs. algebraic structures
* Referential Transparency
    * no side effects
    * everthing is a value
* monoids = semigroups + identity element
* functors
    * covariant - map
* monad
    * chainable and constructable
* comonads
    * 

three.js - Chris Strom

*

D3 - mike tierney

intridea.com

The GUI turns 50 - **********
