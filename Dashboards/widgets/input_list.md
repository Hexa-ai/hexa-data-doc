# Input List

## Paramètres spécifique au widget ```input``` ( attribut ```input``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```showButton``` | booléen | Affiche un bouton de validation   |
| ```value``` | string/number | Valeur sélectionnée par défaut   |

## Si ```showButton``` est égale à ```true```, paramètres spécifiques au widget ```button``` ( attribut ```button``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```label``` | booléen | Text à afficher sur le bouton   |


## Exemple d'une liste déroulante simple

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:list">
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
}
</discovery-tile>
</div>
<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
</div>

## Exemple d'une liste déroulante avec confirmation

<div style="width: 300px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:list">
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true 'value' 'Capteur 2' } 
    'button' { 'label' 'Confirmer' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar1' 'selector' 'myVar' }
  ]
}
</discovery-tile>
</div>
<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar1)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true 'value' 'Capteur 2' } 
    'button' { 'label' 'Confirmer' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar1' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
</div>

## Exemple d'une liste déroulante avec auto-complètion ```input:autocomplete```

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:autocomplete">
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar2' 'selector' 'myVar' }
  ]
}
</discovery-tile>
</div>
<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar2)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
</div>`

## Exemple d'une liste déroulante avec sélection multiple ```input:multi-cb```

<div style="width: 200px; height:150px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:multi-cb">
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar3' 'selector' 'myVar' }
  ]
}
</discovery-tile>
</div>
<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar3)"}'>
  {
    'data' $myVar SIZE
  }
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
</div>

## Exemple d'une liste déroulante avec sélection multiple ```input:multi-cb``` et filtre

<div style="width: 200px; height:150px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:multi-cb">
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' 'showFilter' true } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar3' 'selector' 'myVar' }
  ]
}
</discovery-tile>
</div>
<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar3)"}'>
  {
    'data' $myVar SIZE
  }
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{
  'data' [ "Capteur 1" "Capteur 2" "Capteur 3" ]
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'value' 'Capteur 2' 'showFilter' true } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
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