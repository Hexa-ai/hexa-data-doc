# Pie / Doughnut

## Exemple d'affichage ```pie``` (liste de variables / GTS)

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="pie">
        0 2 <% 'j' STORE
        NEWGTS 'serie' $j TOSTRING + RENAME NOW NaN NaN NaN RAND ADDVALUE
        %> FOR STACKTOLIST 'result' STORE
        {
            'data' $result
            'globalParams' { 'scheme' 'ECTOPLASM' }
        }
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
0 2 <% 'j' STORE
NEWGTS 'serie' $j TOSTRING + RENAME NOW NaN NaN NaN RAND ADDVALUE
%> FOR STACKTOLIST 'result' STORE

{
    'data' $result
    'globalParams' { 'scheme' 'ECTOPLASM' }
}
</warp-view-editor>
</div>

## Exemple d'affichage ```pie``` avec données personnalisées (list de maps)

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="pie">
[
0 2 <% 'j' STORE
{ 'key' 'series-' $j TOSTRING + 'value' RAND }
%> FOR
] 'result' STORE
{
    'data' $result
    'globalParams' { 'scheme' 'ECTOPLASM' }
}
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
[
    0 2 <% 'j' STORE
    { 'key' 'series-' $j TOSTRING + 'value' RAND }
    %> FOR
] 'result' STORE
{
    'data' $result
    'globalParams' { 'scheme' 'ECTOPLASM' }
}
</warp-view-editor>
</div>

## Exemple d'affichage ```doughtnut``` (liste de variables / GTS)

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="doughnut">
0 2 <% 'j' STORE
NEWGTS 'serie' $j TOSTRING + RENAME NOW NaN NaN NaN RAND ADDVALUE
%> FOR STACKTOLIST 'result' STORE
{
    'data' $result
    'globalParams' { 'scheme' 'ECTOPLASM' }
}
</discovery-tile>
</div>
<div style="min-height: 200px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
0 2 <% 'j' STORE
NEWGTS 'serie' $j TOSTRING + RENAME NOW NaN NaN NaN RAND ADDVALUE
%> FOR STACKTOLIST 'result' STORE

{
    'data' $result
    'globalParams' { 'scheme' 'ECTOPLASM' }
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