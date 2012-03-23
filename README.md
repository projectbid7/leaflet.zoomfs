# Leaflet.Control.ZoomFS

This is a simple extension of [Leaflet.Control.Zoom](http://leaflet.cloudmade.com/reference.html#control-zoom) that adds a fullscreen button above the zoom in and zoom out controls.

## Features

- adds a fullscreen button to the default zoom in and zoom out controls
- retains original map container CSS
- use ESC button to exit fullscreen

## Usage

Do all your normal Leaflet [initialization stuff](http://leaflet.cloudmade.com/examples/quick-start.html), except make sure that you initialize the map *without* the default zoom controls:

    var map = new L.Map('map', { zoomControl:false });

Then instantiate the custom ZoomFS control and add it to the map:

    var zoomFS = new L.Control.ZoomFS(); 
    map.addControl(zoomFS);

That's it!

## Style

There's no style supplied in this extension, so you'll need to set it up yourself. Basic style is handled internally by *Leaflet.Control.Zoom* so we don't need to do much:

    .leaflet-control-full-screen {
      background-image: url(your/amazing/icon.png);
      margin-bottom: 5px;
    }

## Events

There are 2 events you can bind to: **enterFullscreen** and **exitFullscreen**. Not that these events are on the Map object; not ZoomFS.

    map.on('enterFullscreen', function(){
      console.log('enterFullscreen');
    });

    map.on('exitFullscreen', function(){
      console.log('exitFullscreen');
    });

# Notes

- If you want the fullscreen button below the zoom in and zoom out buttons check the source in *leaflet.zoomfs.js*. Just switch the order the controls are added.
- This extension was built and testing for Leaflet version 0.3.1. Hopefully it will be updated soon after 0.4 is stable.
- Ideally some of this code should reside in Leaflet.Map...and maybe some day it will. 