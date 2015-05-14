# meteor-notes
Notepad for Meteor packages &amp; best practices

# Approaches & Best Practices
* `"use strict"` always
* testing! git! jslint!
  * Meteor .jshint file https://github.com/raix/Meteor-jshintrc/blob/master/.jshintrc
* when submitting an issue, provide an example or a demo app, must easier for the developer
* limit the fields sent in the subscription, start with what you need only and go from there (good for security and speed), also limit the rows (documents) sent.
* publishing ordered does NOT mean it will be sorted on client, do this there also
* `data-action="insert-thing"` is useful for working with template.events, separates out classes to be for style
* Break functionality up into local pacakges (still testing this one out, takes a lot of work to maintain)
  * Good article about packages/namespacing for a large app http://meteor.redandivory.com/
  * however, building out commonly solved problems into a package is SO useful eg. https://atmospherejs.com/lbee/moment-helpers
* good article: http://sahandsaba.com/nine-anti-patterns-every-programmer-should-be-aware-of-with-examples.html
  * Premature Optimization, Bikeshedding, Analysis Paralysis, God Class, Fear of Adding Classes, Inner-platform Effect (writing something that the OS or platform already has), Magic Numbers and Strings (unnamed variables), Management by Numbers, Useless (Poltergeist) Classes (class that just initiates another class)

# Packages to try
* [ ] https://atmospherejs.com/nicolaslopezj/roles
  * new roles package, alternative approach to https://atmospherejs.com/alanning/roles
* [ ] https://atmospherejs.com/msavin/mongol
  * package to help you develop (UI for collections and other things)
  * looks good, guy is selling other packages too FYI
* [ ] https://atmospherejs.com/jagi/astronomy
  * model layer for Meteor
  * has a cool name
* [ ] https://atmospherejs.com/babrahams/transactions
  * undo/redo for mongo documents
  * seems easy to implement, could be really useful
* [ ] https://atmospherejs.com/ongoworks/security
  * different approach to the allow/deny rules & security

# Other things to try
* Meteor Typescript
  *  http://jacob-foster.azurewebsites.net/typescript-and-meteor-2-lets-start/
  *  Makes a whole lot of sense
* Actual testing for an app (not just packages)
* Page animations / transitions (seems complex at the moment)
* Other text editors (loving atom but people say it is slow)
* Set up a boilerplate 

# Must Remember (forever re-googling)
* Publish anything
  * http://meteorcapture.com/publishing-anything/
  * Great post for publishing things that aren't mongo collections (eg. settings or app name)
* Template Level Subscriptions
  * https://www.discovermeteor.com/blog/template-level-subscriptions/
* `meteor test-packges ./` remember the `./` when in the actual package folder
* better to build something than spend time on crater.io (non-link intentional)

# Packages that rock (with some reminder notes)
* https://atmospherejs.com/chrismbeckett/toastr
  * by far my favourite 'alerts' package, not too complex but looks good and works well
  * remember not to get distracted finding yet another new alerts package, this one is fine!
* https://atmospherejs.com/dburles/collection-helpers
  * extends a collection (document) with things like virtual fields
  * remember that the client must have the related fields for this
* https://atmospherejs.com/aldeed/autoform
  * form builder based on a schema
* https://atmospherejs.com/aldeed/simple-schema & https://atmospherejs.com/aldeed/collection2
  * schemas in meteor, most popular and covers most use cases
  * remember if you want custom fields in the schema, you must declare them
  * remember the debug mode
* https://atmospherejs.com/meteorhacks/npm
  * bringing in npm packages is needed, this is the one to do it with
  * Arunoda is an absolute gun
* https://atmospherejs.com/underscorestring/underscore.string
  * remember use `str.` not `_.` as that is the best approach (now)
* https://atmospherejs.com/mousetrap/mousetrap
  * this is used to easily set keyboard shortcuts
  * remember to set this up on the template.body (sometimes does not work otherwise)
* https://atmospherejs.com/risul/chance
  * much better IMO than https://github.com/anticoders/meteor-fake/
  * has lots of options
  * remember to initiatlise it properly (otherwise you always get the same initial result argh)
* https://atmospherejs.com/cmather/handlebars-server
  * wow, so useful (server side rendering) uses handlebars (blaze is based on this)
  * Goes great with https://atmospherejs.com/sacha/juice for prepaing html emails
* https://atmospherejs.com/raix/handlebar-helpers
  * common helpers you always end up writing anyway, just put it in
  * note: says handlebars but does work with blaze


# Core Packages (notes mainly)
* `reactive-var` (remember, this does not come by default)
* `email` (needed to send emails, but not for the built in accounts emails - I think)
