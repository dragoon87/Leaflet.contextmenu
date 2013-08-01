#Leaflet.contextmenu
====================
A context menu for Leaflet. See the [demo](http://aratcliffe.github.io/Leaflet.contextmenu/examples/index.html).

##Usage
The context menu is implemented as a map interaction handler.  To use the plugin include the script and enable using the map `contextmenu` option.

````javascript
var map = L.map('map', {
	contextmenu: true,
    contextmenuWidth: 140,
	contextmenuItems: [{
	    text: 'Show coordinates',
	    callback: showCoordinates
	}, {
	    text: 'Center map here',
	    callback: centerMap
	}, '-', {
	    text: 'Zoom in',
	    icon: 'images/zoom-in.png',
	    callback: zoomIn
	}, {
	    text: 'Zoom out',
	    icon: 'images/zoom-out.png',
	    callback: zoomOut
	}]
});    
````

###All Options
####Map Context Menu Options

| Option | Type | Default | Description
| --- | --- | --- | ---
| contextmenu | Bool | `false` | Enables the context menu.
| contextmenuWidth | Number | `undefined` | If defined sets the context menu width, if `undefined` the menu will be sized by the maximum width of its menu items.
| contextmenuItems | Array | `[]` | Specification for the context menu items. See following options for individual menu items. A separator can be added with a dash character `'-'`.

####Menu Item Options

| Option | Type | Default | Description
| --- | --- | --- | ---
| text | String | `undefined` | The label to use for the menu item (required).
| icon | String | `undefined` | Url for a 16x16px icon to display to the left of the label.
| iconCls | String | `undefined` | A CSS class which sets the background image for the icon (exclusive of the `icon` option).
| callback | Function | `undefined` | A callback function to be invoked when the menu item is clicked. The callback is passed a [MouseEvent](http://leafletjs.com/reference.html#event-objects) object.
| context | Object | The map | The scope the callback will be executed in.

###Methods

A reference to the map's context menu can be obtained through the map variable e.g. `map.contextmenu`.

````javascript
showAt(L.Point/L.LatLng)
````
Opens the map's context menu at the specified point.

````javascript
hide()
````
Hides the map's context menu if showing.

````javascript
addItem(options)
````
Adds a new menu item to the context menu.

````javascript
insertItem(options, index)
````
Adds a new menu item to the context menu at the specified index. If the index is invalid the menu item will be appended to the menu.

````javascript
removeItem(index)
````
Removes the menu item at the specified index.

````javascript
isVisible()
````
Returns `true` if the context menu is currently visible.

###Events

The following events are triggered on the map:

####contextmenu.show

Fired when the context menu is shown.

| Property | Type | Description
| --- | --- | ---
| contextmenu | Map.ContextMenu | The context menu.

####contextmenu.hide

Fired when the context menu is hidden.

| Property | Type | Description
| --- | --- | ---
| contextmenu | Map.ContextMenu | The context menu.

####contextmenu.additem

Fired when a menu item is added to the context menu.

| Property | Type | Description
| --- | --- | ---
| contextmenu | Map.ContextMenu | The context menu.
| el | HTMLElement | The context menu item element.
| index | Number | The index at which the menu item was added.

####contextmenu.removeitem

Fired when a menu item is removed from the context menu.

| Property | Type | Description
| --- | --- | ---
| contextmenu | Map.ContextMenu | The context menu.
| el | HTMLElement | The context menu item element.

##License
This software is released under the [MIT licence](http://www.opensource.org/licenses/mit-license.php). Icons used in the example are from [http://glyphicons.com](http://glyphicons.com).

