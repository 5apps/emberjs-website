## Problem
You want to base the value of one property on the value of another property.

## Solution
Use one of the computed property macros like `Ember.computed.alias` or `Ember.computed.equal`

```js
App.Person = Ember.Object.extend({
	firstName : null,
	lastName : null,
	surname : Ember.computed.alias("lastName"),
	eligibleForRetirement: Ember.computed.gte("age", 65)
});
```

## Discussion
Ember.js includes a number of macros that will help create properties whose values are based
on the values of other properties, correctly connecting them with bindings so they remain
updated when values change. These all are stored on the `Ember.computed` object
and [documented in the API documentation](http://emberjs.com/api/#method_computed)

#### Example
<a class="jsbin-embed" href="http://jsbin.com/iFusaSe/5/embed?js,output">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>
