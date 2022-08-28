# Map

## Exemple d'affichage d'une carte avec GEOJSON

<div style="width: 800px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="map" chart-title="">
<'
[
    {
        "type":"Feature",
        "properties":{
            "nom":"ERQUY",
            "code":"22430",
            "codeDepartement":"22",
            "population":3898
        },
        "geometry": {
            "type":"Point",
            "coordinates":[-2.404063,48.6414466]
        }
    },
    {
        "type":"Feature",
        "properties":{
            "nom":"LYON",
            "code":"69003",
            "codeDepartement":"69",
            "population":513275
        },
        "geometry": {
            "type":"Point",
            "coordinates":[4.8467100,45.7484600]
        }
    }
]     
'> 
JSON-> 'geoJson' STORE

{
    'data' $geoJson
    'params' [ { 'marker' 'circle' } ]
    'globalParams' {
        'map' {
            'mapType' 'OCEANS'
        }
    }
}
</discovery-tile>
</div>
<div style="min-height: 800px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
<'
[
    {
        "type":"Feature",
        "properties":{
            "nom":"ERQUY",
            "code":"22430",
            "codeDepartement":"22",
            "population":3898
        },
        "geometry": {
            "type":"Point",
            "coordinates":[-2.404063,48.6414466]
        }
    },
    {
        "type":"Feature",
        "properties":{
            "nom":"LYON",
            "code":"69003",
            "codeDepartement":"69",
            "population":513275
        },
        "geometry": {
            "type":"Point",
            "coordinates":[4.8467100,45.7484600]
        }
    }
]     
'> 
JSON-> 'geoJson' STORE

{
    'data' $geoJson
    'params' [ { 'marker' 'recycle' } ]
    'globalParams' {
        'map' {
            'mapType' 'OCEANS'
        }
    }
}
</warp-view-editor>
</div>