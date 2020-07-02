# zakMicroJs

**A simple JavaScript micro-library**

**The sweet, juicy bits**
- zakMicroJs is really tiny: 5KB, 2KB gzipped, small enough to stick inline on single page web apps, saving an extra HTTP request.
- Supports modern desktop and mobile browsers including Chrome, Firefox, Internet Explorer, Opera and Safari.
- Even supports creaky old browsers like IE6, I don't know why you would do this.
- No animation cruft, instead use CSS transitions like a nice person.

## Installation

```bash
<script src="zak.min.js"></script>
```

## Usage
Syntax is simple: `_.method(selector)`. We use `_` namespace.

**CSS selector**
```javascript
_.findAll("p"); // Returns an array of all paragraph elements
_.findAll("p", "hide"); // Hides all paragraphs
_.find("#foo", "hide"); // Shows element with id equal to "foo"
_.find(".foo", "show");  // Hides elements with "foo" CSS class
```
## Methods
**_.ready( () => { });**

Fires handler when the DOM is ready.
```javascript
_.ready( () => { 
	// Do awesome things here
});
```
**_.find(selector, "hide")**

Hides matching elements.
```javascript
<!DOCTYPE html>
<html>
<head>
<script src="zak.min.js"></script>
</head>
<body>
<p id="foo">Foo</p>
<p>Bar</p>
<script>
	_.find("#foo", "hide"); // Hides element with id equal to "foo"
</script>
</body>
</html>
```
**_.find(selector, "show")**

Shows matching elements.
```javascript
<!DOCTYPE html>
<html>
<head>
<script src="zak.min.js"></script>
</head>
<body>
<p  id="foo">Foo</p>
<p>Bar</p>
<script>
	_.find("#foo", "show"); // Shows element with id equal to "foo"
</script>
</body>
</html>
```
**_.find(selector, "styleAdd", "property: value");**

Gets or optionally sets the CSS property for matching elements.

```javascript
<!DOCTYPE html>
<html>
<head>
<style>
.bold {font-weight:900}
</style>
<script src="zak.min.js"></script>
</head>
<body>
<p id="foo">Foo</p>
<p class="bold">Bar</p>
<script>
	_.find('#foo', 'styleAdd', "color: green; font-size: 1rem;"); // sets multiple css element with id equal to "foo"
	_.find('.bold', 'styleAdd', "color: red;"); // sets all blod class color to red
</script>
</body>
</html>
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
Please make sure to update tests as appropriate.