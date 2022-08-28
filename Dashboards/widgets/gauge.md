# Gauge / Circle / linear-gauge / Compass

La tuile de type ```gauge``` permet d'afficher une jauge.

## Paramètres spécifique au widget ```gauge``` ( attribut ```gauge``` de ```globalParams```)

| Attribut         | Type    | Description                        |
|------------------|---------|------------------------------------|
| ```horizontal``` | booléen | Affiche la ```linear-gauge``` à l'horizontale  |

## Afficher la dernière valeur d'une variable/GTS

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="gauge">
{ 'data' 42 'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
// Requète de récupération des données (FETCH)
{ 
    'token' $readToken 
    'class' 'edgeDemo.r2.mesu.temp.chAdam'
    'labels' {} 
    'end' NOW 
    'count' 1 
} FETCH  0 GET VALUES 0 GET 'result' STORE 

// Contenu de la tuile
{ 
    'data' $result 
    'globalParams' {
        'maxValue' 100
        'unit' '°C'
        'scheme' 'ECTOPLASM'
    }
}
</warp-view-editor>
</div>

## Variantes ```circle```

<div style="width: 250px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="circle">
{ 'data' 35.7 'globalParams' { 'maxValue' 55 'unit' '°C' 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

## Afficher la dernière valeur d'une variable/GTS, variante ```linear-gauge``` horizontale

<div style="width: 400px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="linear-gauge">
{ 'data' 42 'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' 'gauge' { 'horizontal' true } } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
// Requète de récupération des données (FETCH)
{ 
    'token' $readToken 
    'class' 'edgeDemo.r2.mesu.temp.chAdam'
    'labels' {} 
    'end' NOW 
    'count' 1 
} FETCH  0 GET VALUES 0 GET 'result' STORE 

// Contenu de la tuile
{ 
    'data' $result 
    'globalParams' {
        'maxValue' 100
        'unit' '°C'
        'scheme' 'ECTOPLASM'
    }
}
</warp-view-editor>
</div>

## Afficher la dernière valeur d'une variable/GTS, variante ```linear-gauge``` verticale

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="linear-gauge">
{ 'data' 42 'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' 'gauge' { 'horizontal' false } } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
// Requète de récupération des données (FETCH)
{ 
    'token' $readToken 
    'class' 'edgeDemo.r2.mesu.temp.chAdam'
    'labels' {} 
    'end' NOW 
    'count' 1 
} FETCH  0 GET VALUES 0 GET 'result' STORE 

// Contenu de la tuile
{ 
    'data' $result 
    'globalParams' {
        'maxValue' 100 
        'unit' '°C' 
        'scheme' 'ECTOPLASM' 
        'gauge' { 'horizontal' false }
    }
}
</warp-view-editor>
</div>

## Variante ```compass```

<div style="width: 250px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="compass">
{ 'data' 200 'globalParams' { 'maxValue' 360 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

<style>
    discovery-tile {
        border: black;
        border-width:  1px;
        background-color: #3A3C4622;
        border-radius: 50px;
    }
</style>