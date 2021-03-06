bootstrap-tabdrop
=================

A dropdown tab tool for @twitter bootstrap forked from Stefan Petre's (of eyecon.ro),

The dropdown tab appears when your tabs do not all fit in the same row.

Original site and examples: http://www.eyecon.ro/bootstrap-tabdrop/

Added functionality: Displays the text of an active tab selected from the dropdown list instead of the text option on the dropdown tab.


## Requirements

* [Bootstrap](http://twitter.github.com/bootstrap/) 2.0.4+
* [jQuery](http://jquery.com/) 1.7.1+

## Example

No additional HTML needed - the script adds it when the dropdown tab is needed.

Using bootstrap-tabdrop.js
Call the tab drop via javascript on .nav-tabs and .nav-pills:
```js
$('.nav-pills, .nav-tabs').tabdrop()
```

### Options

#### text
Type: string
Default: icon
```html
<i class="icon-align-justify"></i>
```
To change the default value, call
```javascript
.tabdrop({text: "your text here"});
```
when initalizing the tabdrop. The displayed value will change when a tab is selected from the dropdown list.

### Methods

```js
.tabdrop(options)
```

Initializes an tab drop.

```js
.tabdrop('layout')
```

Checks if the tabs fit in one single row.

### Event

```
tabdrop.layout.complete
```

Triggered when the DOM updates are complete. This can be used to manually initialize the dropdown and the contained tabs.

```js

$('.nav-tabs').tabdrop().on('tabdrop.layout.complete', function () {
  
  // initialize dropdown
  $('.dropdown-toggle').dropdown();

  // initialize items
  $('.dropdown-menu a[data-toggle="tab"]').click(function (e) {
    e.stopPropagation();
    e.preventDefault();
    $(this).tab('show');
  });

});

```

