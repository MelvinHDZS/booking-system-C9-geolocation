- 2022-02-21
- Members: Melvin Hernández, Juan Manzanero
- RFC PR:

# Sumary

Implement [Google Maps API](https://developers.google.com/maps) to show to the user the locations in the map.

# Basic example

## Installation

    npm install --save react-google-maps
    
## Usage

Import the components to your .jsx | .js file.

The component needs some styles to render on the view.  
It needs some coordinates to focus a point.  
Return the Google Map component inside the LoadSrcipt with your API_KEY.

    import React from 'react';
    import { GoogleMap, LoadScript } from '@react-google-maps/api';

    const Map = () => {
        const mapStyles = {
            width: "100%",
            height: "50vh"
        };

        const defaultCenter = { 0, 0 };

        return (
            <LoadScript googleMapsApiKey='API_KEY'>
                <GoogleMap
                    mapContainerStyle={mapStyles}
                    zoom={10}
                    center={defaultCenter}
                >
                </GoogleMap>
            </LoadScript>
        );
    };

    export default Map;

# Motivation

We are using Google Maps API because is the most complete Geolococation API,  
an as we need show to our users location on a map, this will help with that interaction.

# Detailed design

Using React we need to just import de Google Map component and implmenet the  
attributes specified on the [API Documentation](https://developers.google.com/maps/documentation).

To implement markers, import the Marker component and add it as a child of GoogleMap  
component.  

It needs coordinates like the map.

    
    import React from 'react';
    import { GoogleMap, LoadScript, Marker } from '@react-google-maps/api';
    
    const Map = () => {
        const mapStyles = {
            width: "100%",
            height: "50vh"
        };
        
        const defaultCenter = { 0, 0 };
        
        return (
            <LoadScript googleMapsApiKey='API_KEY'>
                <GoogleMap
                    mapContainerStyle={mapStyles}
                    zoom={10}
                    center={defaultCenter}
                >
                    <Marker position={defaultCenter} />
                </GoogleMap>
            </LoadScript>
        );
    };
    
    export default Map;
