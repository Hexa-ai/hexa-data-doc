# Input Date

## Paramètres spécifique au widget ```input``` ( attribut ```input``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```showButton``` | booléen | Affiche un bouton de validation   |

## Si ```showButton``` est égale à ```true```, paramètres spécifiques au widget ```button``` ( attribut ```button``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```label``` | booléen | Text à afficher sur le bouton   |


## Exemple d'un champd de saisie simple

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:date">
    { 'data' NOW 'events' [
    { 'type' 'variable' 'tags' 'myTime1' 'selector' 'myTime' }
    ] 
    'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false } 
    'button' { 'label' 'Valider' } 
  } }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myTime1)"}'>
  {
    'data' $myTime ISO8601
  }
</discovery-tile>
</div>

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
  'data' NOW 
  'events' [
    { 'type' 'variable' 'tags' 'myTime1' 'selector' 'myTime' }
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

<div style="width: 300px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:date">
    { 'data' NOW 'events' [
    { 'type' 'variable' 'tags' 'myTime2' 'selector' 'myTime' }
    ] 
    'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' true } 
    'button' { 'label' 'Comfirmer' } 
  } }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myTime2)"}'>
  {
    'data' $myTime ISO8601
  }
</discovery-tile>
</div>

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
  'data' NOW 
  'events' [
    { 'type' 'variable' 'tags' 'myTime1' 'selector' 'myTime' }
  ] 
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false } 
    'button' { 'label' 'Valider' } 
  }
}
</warp-view-editor>
</div>

## Exemple d'un champd de saisie de plage (```ìnput:date-range```)

<div style="width: 300px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:date-range">
{ 
  'data' [ NOW 1 d - NOW ]
  'events' [
    { 'type' 'variable' 'tags' 'myTime3' 'selector' 'myTime' }
  ] 
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false } 
    'button' { 'label' 'Comfirmer' } 
  }
}
</discovery-tile>
</div>

<div style="width: 600px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myTime3)"}'>
  {
    'data' 'Plage de: ' $myTime 0 GET ISO8601 + ' à ' + $myTime 1 GET ISO8601 +
  }
</discovery-tile>
</div>

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
  'data' [ NOW 1 d - NOW ]
  'events' [
    { 'type' 'variable' 'tags' 'myTime3' 'selector' 'myTime' }
  ] 
  'globalParams' { 
    'scheme' 'ECTOPLASM' 
    'input' { 'showButton' false } 
    'button' { 'label' 'Comfirmer' } 
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