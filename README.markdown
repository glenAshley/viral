# viral

viral is a tiny, pure prototypal OO library for javascript; taking the best parts of [boo](https://github.com/killdream/boo).

## Why

JavaScript supports objects inheriting from prototypes; and making this an easy process is ridiculously simple.

## API

viral exposes a base object to inherit from - viral.Base.  It has two methods:

### viral.Base.extend

viral.Base.extend creates an object that inherits from viral.Base, and copies any
properties passed to .extend into that new object:

```javascript
var viral = require('viral')

var Person = viral.Base.extend({
	constructor: function(firstName, lastName){
		this.firstName = firstName
		this.lastName = lastName
	},
	fullName: function(){ return this.firstName + this.lastName }
})
```

### viral.Base.make

viral.base.make creates an object that inherits from viral.Base, and calls the constructor method
of this new object with any arguments you pass in.


```javascript
// continuing with the Person example from `viral.Base.extend`

var hugh = Person.make('hugh', 'jackson')   // Person inherits .make from viral.Base

hugh.fullName() //= 'hugh jackson'
```

## Install

### node

`npm install viral`, then require:

```javascript
var viral = require('viral')

// use `viral` here
```

### browser

include as a script tag:

```html
<doctype html>
<html>
	<head></head>
	<body>
		<script src="libs/viral.js"></script>
		<script>
		// use `viral` here
		</script>
	</body>
</html>
```

### requirejs

include as a script.  e.g., from the libs/ folder:

```javscript
require(['libs/viral'], function(viral){
	// use `viral` here
})
```