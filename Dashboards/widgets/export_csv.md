# Export CSV

## Télécharger une liste de listes (tableau à deux dimenssions)

<div style="width: 200px; height:100px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="csv-export" chart-title="" debug>
{ 
    'data'  [ [ 'col1' 'col2' ] [ '12' '13' ] ]
    'globalParams' { 'button' { 'label' 'Téléchargement' } }
}
</discovery-tile>
</div>

<div style="min-height: 100px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
{ 
    'data'  [ [ 'col1' 'col2' ] [ '12' '13' ] ]
    'globalParams' { 'button' { 'label' 'Téléchargement' } }
}
</warp-view-editor>
</div>