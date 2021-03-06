Colorboard
=============

##API Reference

- [Methods, properties and events](api/refs/ui.colorboard.md)
- [Samples](http://docs.webix.com/samples/24_colorpicker/index.html)

##Overview

UI-related colorboard is a tool to get the hex code of a color that you are going to use for [styling](desktop/styling.md). 
By default, colors are presented in a rainbow-like manner. The detalization level you set manually. 

<br>

<img style="display:block; margin-left:auto;margin-right:auto;"  src="desktop/colorboard.png"/>

<br>

##Initialization

Colorboard is used in conjunction with a [colorpicker](desktop/colorpicker.md) control. In such a case, you needn't to initialize a colorboard since it will appear as soon as you click a control. 

When used separately, colorboard is initialized in the following way:

~~~js
webix.ui({
		view:"colorboard",
		cols	:30,
		rows	:30,
		width	:400,
		height	:400
});
~~~
{{sample 24_colorpicker/01_initialization.html }}


####Comments:

- **width** and **height** denote the dimensions of a square with a color palette;
- **cols** and **rows** denote the number of colors in each axle - the bigger it is, the more detailed is the palette;
- gradient nature of the colorboard can be controlled via lightness values: 
	- **minLightness** (0.15 by default) - start value of lightness (the darkest part);
    - **maxLightness** - (1 by default) - end value of lightness (the lightest part).

##Working with Colorboard

You can customize your colorboard by:

- **setting the way of color presentation**

<img src="desktop/colorboard_custom.png" />

~~~js
webix.ui({
	view:"colorboard",
	cols:7,
	rows:4,
	width:600,
	height:370,
	template:"<div class=\"value_cell\">" +
			"<div>{obj.val}</div>" +
			"<div class=\"color_block\" style=\"background:{obj.val};\"></div>" +
			"</div>"
});
~~~

{{sample 24_colorpicker/02_custom_template.html }}

- **defining your own color set**

<img src="desktop/colorboard_custom_colors.png"/>

~~~js
var colors = [
	["#C6D9F0", "#8DB3E2", "#548DD4"],
	["#F2DCDB", "#E5B9B7", "#D99694"],
	["#EBF1DD", "#D7E3BC", "#C3D69B"]
];

webix.ui({
	view:"colorboard",
	...
	palette:colors
});
~~~

{{sample 24_colorpicker/03_custom_colors.html }}

####Deriving Selected Color Value from the colorboard: 

Normally, selected color is derived with the help of the **getValue()** method:

~~~js
$$("colorboard1").getValue();
~~~

In addition, color values can be logged once **val**, **control** and **ev** parameters are passed into the logging function. 

~~~js
function doLog(val, control, ev){
		webix.message(this.config.id + " - " + val);
	}
~~~


##Related Articles

- [Making Templates](desktop/html_templates.md)
- [Component Styling](desktop/styling.md)