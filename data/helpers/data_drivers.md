Data Drivers
============

There are 6 default data drivers: 

- *json*
- *xml*
- *html*
- *csv*
- *jsarray*
- *excel*


Customizing data driver
------------------------

###XML

In case of XML you can redefine 
<table class='list'>
	<tr><th>Element</th><th>Type</th><th>Code</th></tr>
    <tr><td>data tag</td>
    <td>xpath</td>
    <td>
~~~js
webix.DataDriver.xml.records = "/*/item";
~~~
    </td></tr>
	<tr><td>configuration tag</td>
    <td>xpath</td>
    <td>
~~~js
webix.DataDriver.xml.config = "/*/config";
~~~
    </td></tr>
	<tr><td>child tag</td>
    <td>tag name</td>
    <td>
~~~js
webix.DataDriver.xml.child = "item";
~~~
    </td></tr>
</table>

For example to alert the default processing of XML data you can add the following line to your code: 

~~~js
webix.DataDriver.xml.records = "/*/book";
webix.DataDriver.xml.child = "part";
~~~

The line above will redefine data parsing logic for all XML sources; if you wish to put apart default and custom logic
you need to create a custom XML processor on the base of the default one. 

~~~js

var myxml = webix.DataDriver.myxml = webix.copy(webix.DataDriver.xml);
myxml.records = "/*/book";
myxml.child = "part";
~~~

{{sample 17_datatree/01_loading/02_xml_data.html}}

Child tags can be specified by a function: 

~~~js
var myxml2 = webix.DataDriver.myxml2 = webix.copy(webix.DataDriver.xml);
myxml2.records = "/*/book";
myxml2.child = function(obj){
	if (obj.$level == 1)
		return obj.part;
	if (obj.$level == 2)
		return obj.page;
}
~~~

{{sample 17_datatree/01_loading/02_xml_data.html}}

### CSV

It is possible to define row and cell separators:

~~~js
webix.DataDriver.csv.row = "\n";
webix.DataDriver.csv.cell = ",";
~~~

The above line resets processing of all the SCV sources in the application. To avoid this, create a custom CSV format: 

~~~js
var myscv = webix.DataDriver.myscv = webix.copy(webix.DataDriver.scv);
csv.row = "\n";
csv.cell = ",";
~~~


### HTML

You can redefine which tag in html will be processed as data tag:

~~~js
webix.DataDriver.html.tag = "LI";
~~~

The above line resets processing of all the HTML sources in the application. To avoid this, create a custom HTML format: 

~~~js
var myhtml = webix.DataDriver.myhtml = webix.copy(webix.DataDriver.html);
html.tag = "LI";
~~~

###JSON

You can redefine which object property stores sub-items ( used for hierarchical dataset, like one for tree, treegrid, grouplist etc. )

~~~js
webix.DataDriver.json.child = "data";
~~~

The above line resets processing of all the JSON sources in the application. To avoid this, create a custom JSON format: 

~~~js
var myjson = webix.DataDriver.json = webix.copy(webix.DataDriver.json);
myjson.child = "data";
~~~

Methods of data driver
----------------------

All data drivers share the following methods: 

~~~js
//converts string to object
var data = driver.toObject(data);

//returns array of all records in data source
var records = driver.getRecords(data);

//returns single data object
var data = driver.getDetails(records[0]);
~~~


###XML specific methods

~~~js
//runs xpath
var elements = driver.xpath("/some/xpath", data);

//converts xml tag to json object
var obj = driver.tagToObject(elements[0]);

//converts string to js data-types, numbers and booleans
obj = driver.assignTypes(obj);
~~~

Creating new data driver
------------------------

In addition to built-in data types, it possible to define custom ones by creating a custom data driver:

The structure of driver is the following:

~~~js
webix.DataDriver.driverName={ //driverName - the name of the type
	toObject:function(text,xml){
        ...
		return text; 
	},
	getRecords:function(data){ 
        var result = [];
        ...
		return result;
	},
	getDetails:function(data){
        var result = {}
        ... 
		return result;
	},
	getInfo:function(data){
		return { 
		   size:0, 
		   from:0 
		};
	}
};

~~~

You can check the structure of existing data drivers in Webix source code ([webix_debug.js](desktop/debug.md))

For a start, we have some data that we want to use as a new data type.
The first thing we need to make with this data - conversion into an intermediate object (an object that will be used as an input parameter in the other functions). 
  
1 . So, our first step -  **toObject(text, xml)** function. The function is called after data loading or directly in the **parse** method and returns the intermediate data object:
  
- text - incoming data;
- xml - xml object (for xml loading scenario. For other data types can be ignored).

2 . Then, we form an array of records using data from our intermediate object -  **getRecords(data)** function.

- data - the intermediate object from the previous step.

3 . Having an array of records we need to specify a set of properties for each single record - the third step - **getDetails(data)**.
  
- data - an element of the array from the previous step.

4 . The last action has sense just for dynamic data loading scenarios. It's the **getInfo(data)** function that gets total count of the data and position at which new data needs to be inserted. 

- data - the intermediate object from step 1.

The function returns an object with the following properties: 

- size - total count of the data (*total_count*) or 0 is dynamic loading is not enabled/not possible;
- from - index f the last data item at the moment  (*pos*) or 0 is dynamic loading is not enabled/not possible.

JSON and XML data drivers add extra properties to these object: 

- parent - index of the root branch (*parent*);
- config - configuration object loaded together with the data (*config*);
- key - security key (*webix_security*).

So, making these four or even three steps you can specify any data type and then use it while developing.  

Creating new data driver based on an existing one
------------------------

Creating a completely new driver is not the most common task, but a user may need to alter the processing logic of 
some built-in driver. 

It can be done with the help of Webix [extending pattern](desktop/extend.md) that allows to extend any JSON object: 

~~~js
webix.DataDriver.custom = webix.extend({
	records:"/data/items/item",
	getDetails:function(obj){
		var res = {};
		var cells = this.xpath(obj, "cell");
		for (var i = 0; i < cells.length; i++)
			res[cells[i].getAttribute("id")] = this.nodeValue(cells[i]);
		return res;
	}
}, webix.DataDriver.xml);
~~~

{{sample 15_datatable/01_loading/12_custom_xml.html}} 

@complexity:3