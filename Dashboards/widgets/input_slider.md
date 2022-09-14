# Slider

## Paramètres spécifiques au widget ```input``` ( attribut ```input``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```showButton``` | booléen | Affiche un bouton de validation   |
| ```value``` | string/number | Valeur sélectionnée par défaut   |
| ```min``` | number | Valeur minimum du slider   |
| ```max``` | number | Valeur maximum du slider   |

## Si ```showButton``` est égale à ```true```, paramètres spécifiques au widget ```button``` ( attribut ```button``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```label``` | booléen | Text à afficher sur le bouton   |

## Exemple d'un ```input-slider``` simple

<div style="width: 400px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:slider">
{
  'data' 42
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'min' 0 'max' 100 } 
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
  'data' 42
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false 'min' 0 'max' 100 } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
</div>

## Exemple d'un ```input-slider``` avec confirmation

<div style="width: 400px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:slider">
{
  'data' 42
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true 'min' 0 'max' 100 } 
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
  'data' 42
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true 'min' 0 'max' 100 } 
    'button' { 'label' 'Valider' } 
  } 
  'events' [
    { 'type' 'variable' 'tags' 'myVar1' 'selector' 'myVar' }
  ]
}
</warp-view-editor>
