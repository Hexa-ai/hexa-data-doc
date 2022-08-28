# Input Text

## Paramètres spécifique au widget ```input``` ( attribut ```input``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```showButton``` | booléen | Affiche un bouton de validation   |

## Si ```showButton``` est égale à ```true```, paramètres spécifiques au widget ```button``` ( attribut ```button``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```label``` | booléen | Text à afficher sur le bouton   |


## Exemple d'un champd de saisie simple

<div style="width: 250px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:text">
    { 'data' '' 'events' [
    { 'type' 'variable' 'tags' 'saisieText1' 'selector' 'myVar' }
    ]
    'globalParams' { 'scheme' 'ECTOPLASM' 'input' { 'showButton' false } 'button' { 'label' 'Valider' } } }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(saisieText1)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>
<div style="min-height: 100px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
  'data' ''
  'events' [
    { 'type' 'variable' 'tags' 'saisieText1' 'selector' 'myVar' }
  ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false } 
    'button' { 'label' 'Valider' } 
  } 
}
</warp-view-editor>
</div>

## Exemple d'un champd de saisie avec confirmation

<div style="width: 250px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:text">
    { 'data' '' 'events' [
    { 'type' 'variable' 'tags' 'saisieText2' 'selector' 'myVar' }
    ]
    'globalParams' { 'scheme' 'ECTOPLASM' 'input' { 'showButton' true } 'button' { 'label' 'Valider' } } }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(saisieText2)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>
<div style="min-height: 100px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
  'data' ''
  'events' [
    { 'type' 'variable' 'tags' 'saisieText2' 'selector' 'myVar' }
  ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true } 
    'button' { 'label' 'Valider' } 
  } 
}
</warp-view-editor>
</div>
<style>
    discovery-tile {
        border: black;
        border-width:  1px;
        background-color: #3A3C4622;
        border-radius: 50px;
    }
</style>