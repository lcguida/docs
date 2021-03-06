{{memo a vertical or horizontal layout without headers}}

The component allows you to define interface structure by organizing views in a vertical or horizontal layout. 
By including layouts one by one, it's possible to create an interface of any complexity. 
Check [Layout](desktop/layout.md) documentation for a more detailed description.

### Constructor

~~~js
var layout = webix.ui({
	rows:[
		{template:"row 1"},
		{template:"row 2"},
		{
			cols:[
				{template:"col 1"},
				{template:"col 2"}
			]
		}
	]
});
~~~

### Where to start

- [Overview of the Layout Widget](desktop/layout.md)
- [Samples](http://docs.webix.com/samples/01_layout/index.html)