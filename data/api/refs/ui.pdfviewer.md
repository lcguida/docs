ui.pdfviewer 
=============


{{memo A tool for displaying the content of PDF files on the screen. }}

Webix PDF Viewer is a useful tool for viewing PDF files. It consists of a toolbar that contains buttons for paging and zooming and the viewer itself.

Check desktop/pdfviewer.md documentation for a more detailed information.

### Constructor

~~~js
var pdfviewer = webix.ui({
	view:"pdfviewer", 
    id:"pdf", 
    toolbar:"toolbar", 
    url:"binary->files/WebixDocs.pdf"
}).
~~~

### Where to start

- [Overview of the PDF Viewer Widget](desktop/pdfviewer.md)
- [Samples](http://docs.webix.com/samples/60_pro/10_viewers/)
<div class='webixdoc_parents'><span>Based on: </span>
<a href="api/refs/eventsystem.md">EventSystem</a>, <a href="api/refs/atomdataloader.md">AtomDataLoader</a>, <a href="api/refs/ui.view.md">ui.view</a>, <a href="api/refs/ui.baseview.md">ui.baseview</a>, <a href="api/refs/settings.md">Settings</a>, <a href="api/refs/destruction.md">Destruction</a>, <a href="api/refs/basebind.md">BaseBind</a>, <a href="api/refs/uiextension.md">UIExtension</a></div>


<div class='h2'>Methods</div>

{{api
- api/link/ui.pdfviewer_adjust.md - adjusts the component to the size of the parent HTML container
- api/link/ui.pdfviewer_attachevent.md - attaches the handler to an inner event of the component (allows behavior customizations)
- api/link/ui.pdfviewer_bind.md - binds components
- api/link/ui.pdfviewer_blockevent.md - temporarily blocks triggering of ALL events of the calling object
- api/link/ui.pdfviewer_callevent.md - calls an inner event
- api/ui.pdfviewer_clear.md - clears the content of PDF Viewer
- api/link/ui.pdfviewer_define.md - redefines a single configuration property (or a hash of properties)
- api/link/ui.pdfviewer_destructor.md - destructs the calling object
- api/link/ui.pdfviewer_detachevent.md - detaches a handler from an event (which was attached before by the attachEvent method)
- api/link/ui.pdfviewer_disable.md - disables the calling view (makes it dimmed and unclickable)
- api/ui.pdfviewer_download.md - downloads viewer contents as PDF file
- api/link/ui.pdfviewer_enable.md - enables the calling view that was disabled by the 'disable' method
- api/link/ui.pdfviewer_getchildviews.md - returns child views of the calling component
- api/link/ui.pdfviewer_getformview.md - returns master form for the input
- api/link/ui.pdfviewer_getnode.md - returns the main HTML container for the calling object
- api/link/ui.pdfviewer_getparentview.md - returns the parent view of the component
- api/link/ui.pdfviewer_gettopparentview.md - returns top parent view
- api/link/ui.pdfviewer_hasevent.md - checks whether the component has the specified event
- api/link/ui.pdfviewer_hide.md - hides the view
- api/link/ui.pdfviewer_isenabled.md - checks whether the view is enabled
- api/link/ui.pdfviewer_isvisible.md - checks whether the view is visible
- api/link/ui.pdfviewer_load.md - loads data from an external data source.
- api/link/ui.pdfviewer_mapevent.md - routes events from one object to another
- api/ui.pdfviewer_nextpage.md - renders the page that follows the viewed one
- api/link/ui.pdfviewer_parse.md - loads data to the component from an inline data source
- api/ui.pdfviewer_prevpage.md - renders the page that precedes the viewed one
- api/ui.pdfviewer_renderpage.md - renders the specified page in the viewer
- api/link/ui.pdfviewer_resize.md - adjusts the view to a new size
- api/ui.pdfviewer_setscale.md - sets a new value for a zooming scale and renders current page with the new scale
- api/link/ui.pdfviewer_show.md - makes the component visible
- api/link/ui.pdfviewer_unbind.md - breaks "bind" link
- api/link/ui.pdfviewer_unblockevent.md - cancels blocking events that was enabled by the 'blockEvent' command
- api/ui.pdfviewer_zoomin.md - zooms the viewed page in
- api/ui.pdfviewer_zoomout.md - zooms the viewed page out
}}


<div class='h2'>Events</div>


{{api
- api/link/ui.pdfviewer_onafterload_event.md - fires after data loading is complete
- api/link/ui.pdfviewer_onafterscroll_event.md - occurs when some webix view has been scrolled
- api/link/ui.pdfviewer_onbeforeload_event.md - occurs immediately before data loading has been started
- api/link/ui.pdfviewer_onbindrequest_event.md - fires when the component is ready to receive data from the master component
- api/link/ui.pdfviewer_onblur_event.md - fires when focus is moved out of the view
- api/link/ui.pdfviewer_ondestruct_event.md - occurs when component destroyed
- api/ui.pdfviewer_ondocumentready_event.md - fires after the PDF file is fully loaded and the initial page is rendered
- api/link/ui.pdfviewer_onfocus_event.md - fires when a view gets focus
- api/link/ui.pdfviewer_onkeypress_event.md - occurs when keyboard key is pressed for the control in focus
- api/link/ui.pdfviewer_onloaderror_event.md - fires when an error occurs during data loading ( invalid server side response )
- api/link/ui.pdfviewer_onlongtouch_event.md - fires on holding finger in some position for a certain period of time
- api/ui.pdfviewer_onpagerender_event.md - fires after a page is rendered in the viewer body
- api/ui.pdfviewer_onscalechange_event.md - fires after the page has been zoomed
- api/link/ui.pdfviewer_onswipex_event.md - occurs on a horizontal swipe movement
- api/link/ui.pdfviewer_onswipey_event.md - occurs on a vertical swipe movement
- api/link/ui.pdfviewer_ontimedkeypress_event.md - fires after typing has been finished in the field
- api/link/ui.pdfviewer_ontouchend_event.md - occurs when the touch event is ended
- api/link/ui.pdfviewer_ontouchmove_event.md - occurs during touch movement
- api/link/ui.pdfviewer_ontouchstart_event.md - when some webix view has been touched
- api/link/ui.pdfviewer_onviewresize_event.md - view size was changed by resizer
}}


<div class='h2'>Properties</div>

{{api
- api/link/ui.pdfviewer_animate_config.md - defines or disables view change animation.
- api/link/ui.pdfviewer_borderless_config.md - used to hide the component borders
- api/link/ui.pdfviewer_container_config.md - an HTML container (or its id) where the component should be initialized
- api/link/ui.pdfviewer_css_config.md - the name of a css class that will be applied to the view container
- api/link/ui.pdfviewer_data_config.md - JavaScript array containing data for the component
- api/link/ui.pdfviewer_datafeed_config.md - the URL that the component will use to reload data during binding
- api/link/ui.pdfviewer_datatype_config.md - the type of loaded data
- api/link/ui.pdfviewer_disabled_config.md - indicates whether an item is enabled or not
- api/ui.pdfviewer_downloadname_config.md - sets the name of the downloaded file without the .pdf extension
- api/link/ui.pdfviewer_gravity_config.md - sets the view gravity (1 by default)
- api/link/ui.pdfviewer_height_config.md - sets the height of the component
- api/link/ui.pdfviewer_hidden_config.md - defines whether the view will be hidden initially
- api/link/ui.pdfviewer_id_config.md - the component ID
- api/link/ui.pdfviewer_maxheight_config.md - sets the maximum height for the view
- api/link/ui.pdfviewer_maxwidth_config.md - sets the maximum width for the view
- api/link/ui.pdfviewer_minheight_config.md - sets the minimal height for the view
- api/link/ui.pdfviewer_minwidth_config.md - sets the minimal width for the view
- api/link/ui.pdfviewer_on_config.md - allows attaching custom handlers to inner events of the component
- api/ui.pdfviewer_scale_config.md - current scale value
- api/ui.pdfviewer_toolbar_config.md - the id of the PDF toolbar related to the viewer
- api/link/ui.pdfviewer_url_config.md - the URL which the component will use to load data after its initialization
- api/link/ui.pdfviewer_width_config.md - sets the width of the component
}}





<div class='h2'>Other</div>


{{api
- api/link/ui.pdfviewer_$getsize_other.md - returns the current size of the component
- api/link/ui.pdfviewer_$height_other.md - current height of the view
- api/ui.pdfviewer_$numpages_other.md - total number of pages in the document
- api/ui.pdfviewer_$onload_other.md - default action on data loading
- api/ui.pdfviewer_$pagenum_other.md - the number of a currently visible page
- api/link/ui.pdfviewer_$scope_other.md - scope for resolving event and method names
- api/link/ui.pdfviewer_$setsize_other.md - sets the component size
- api/link/ui.pdfviewer_$skin_other.md - the method which will be called when skin is defined
- api/link/ui.pdfviewer_$view_other.md - reference to top html element of the view
- api/link/ui.pdfviewer_$width_other.md - current width of the view
- api/link/ui.pdfviewer_config_other.md - all options from initial component configuration
- api/link/ui.pdfviewer_name_other.md - indicates the name of the component (a read-only property)
}}


@index:
- api/refs/ui.pdfviewer_methods.md
- api/refs/ui.pdfviewer_props.md
- api/refs/ui.pdfviewer_events.md
- api/refs/ui.pdfviewer_others.md

