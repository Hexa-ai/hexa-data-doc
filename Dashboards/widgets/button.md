# Button

## Paramètres spécifiques au widget ```button``` ( attribut ```button``` de ```globalParams```)

| Attribut         | Type    | Description                       |
|------------------|---------|-----------------------------------|
| ```label``` | booléen | Texte à afficher sur le bouton   |


## Exemple de bouton simple

<div style="width: 400px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="button">
<%
    {
    'data' <% RAND  %> 
    'globalParams' { 
        'scheme' 'ECTOPLASM'
        'button' { 'label' 'Envoyer' } 
    } 
    'events' [
        { 'type' 'data' 'tags' 'myVar' 'value' 1 }
    ]
    }
%>
</discovery-tile>
</div>
<div style="width: 200px; height:100px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=data,tag=(myVar)"}'>
 { 'data' '' }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
<%
    {
    'data' <% RAND  %> 
    'globalParams' { 
        'scheme' 'ECTOPLASM'
        'button' { 'label' 'Envoyer' } 
    } 
    'events' [
        { 'type' 'data' 'tags' 'myVar' 'value' 1 }
    ]
    }
%>
</warp-view-editor>
</div>