# Introduction #

EJS provides a lot of flexibility for using JavaScript templates.  This article documents EJS's template API.

EJS is typically used by loading a template and rendering it with data.

# Loading a template #

Load a template by creating a new EJS template.  Templates are cached by default.

### Example ###
```
template = new EJS({url: '/mytemplate.ejs'})
```
options is a hash that can include the following attributes:

  * url {string} - loads a template from a file
  * text {string} - uses the provided text as the template
  * element {string or element} - loads a template from the innerHTML or value of the element.
 type {string} (optional) - '<' or '[', default is '<', except for loading a template from an element.
  * name {string} (optional) - an optional name that is used for caching.  This defaults to the element ID or URL provided.
  * cache {boolean} (optional) - defaults to true.  True if you want to enable caching of templates, false if otherwise.


# Rendering #

There are 2 ways to render a template.  The first method, render, simply returns text.  Other method, update, is used to update the inner HTML of an element.

## render(data) ##
Renders the template with the provided data.
```
  html = new EJS({url: '/template.ejs'}).render(data)
```

## update(element, url\_or\_data) ##
Updates an element with the result of the template.

### options ###
**element** {string or element} - the element you want updated

**url\_or\_data** - can be one of the following:
> {null} - returns a function that takes an object as its first argument.  That object will be used to render the template and update the element.

> {string} - The string is used as a url to perform an AJAX request.  The data returned from the ajax request is used to render the template and update the element.

> {object} - Data used to render the template and update the element.

### Examples ###
```
f = new EJS({url: '/mytemplate.ejs'}).update('my_element')

new EJS({url: '/mytemplate.ejs'}).update('my_element', '/data.json')

new EJS({url: '/mytemplate.ejs'}).update('my_element', {supplies: ['mop']})
```