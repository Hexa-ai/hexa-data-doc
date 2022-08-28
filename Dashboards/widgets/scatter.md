# Scatter

## Paramètres par série

| Attribut           | Type   | Description                                             | Valeurs                                                                                  |
|--------------------|--------|---------------------------------------------------------|------------------------------------------------------------------------------------------|
| ```datasetColor``` | string | Couleur du jeux de données                              |                                                                                          |
| ```type```         | string | Type d'affichage pour le jeux de données                | line, area, scatter, step-area,<br>spline-area, spline, step, step-after,<br>step-before |
| ```xAxis```        | LONG   | Dans le cas d'axes X multiples, index de l'axe concerné |                                                                                          |
| ```yAxis```        | LONG   | Dans le cas d'axes Y multiples, index de l'axe concerné |                                                                                          |


## Exemple d'affichage d'une variable/GTS

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="scatter">
1 4 <% 'i' STORE 
    NEWGTS 'var-' $i TOSTRING + RENAME 'g' STORE
    1 10 <% 'ts' STORE 
        $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP 
    %> FOR
    $g 
%> FOR STACKTOLIST 'result' STORE
{
    'data' $result
    'globalParams' {  'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' }
}
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
1 4 <% 'i' STORE 
    NEWGTS 'var-' $i TOSTRING + RENAME 'g' STORE
    1 10 <% 'ts' STORE 
        $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP 
    %> FOR
    $g 
%> FOR STACKTOLIST 'result' STORE

{
    'data' $result
    'globalParams' {  'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' }
}
</warp-view-editor>
</div>

## Exemple d'affichage de données personnalisées

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="scatter">
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - ] %> FOR ] %> 'rand' STORE
{
    'data' [
        { 'label' 'A' 'values' @rand }
        { 'label' 'B' 'values' @rand }
    ]
    'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' }
}
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - ] %> FOR ] %> 'rand' STORE
{
    'data' [
        { 'label' 'A' 'values' @rand }
        { 'label' 'B' 'values' @rand }
    ]
    'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' }
}
</warp-view-editor>
</div>

## Exemple d'affichage de bulles avec des données personnalisées

Les listes de points fournis contiennent trois valeurs x, y et diamètre de la bulle

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="scatter">
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - RAND 100 * ] %> FOR ] %> 'rand' STORE
{
    'data' [
        { 'label' 'A' 'values' @rand }
        { 'label' 'B' 'values' @rand }
    ]
    'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' }
}
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - RAND 100 * ] %> FOR ] %> 'rand' STORE
{
    'data' [
        { 'label' 'A' 'values' @rand }
        { 'label' 'B' 'values' @rand }
    ]
    'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' }
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