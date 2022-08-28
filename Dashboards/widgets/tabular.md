# Tabular

# Afficher un tableau de variables / GTS

<div style="width: 400px; height:600px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="tabular" chart-title="">
0 0 <% 'j' STORE
    NEWGTS 'serie' $j TOSTRING + RENAME 'g' STORE
    1 500 <%
    'ts' STORE
    NOW $ts STU * 50.0 / - 'ts' STORE
    $g $ts NaN NaN NaN $ts 50 * STU / 60.0 / SIN ADDVALUE DROP %> FOR
    $g
%> FOR STACKTOLIST 'result' STORE

{
    'data' $result
}
</discovery-tile>
</div>
<div style="min-height: 250px; width: 600px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false"> 
0 0 <% 'j' STORE
    NEWGTS 'serie' $j TOSTRING + RENAME 'g' STORE
    1 500 <%
    'ts' STORE
    NOW $ts STU * 50.0 / - 'ts' STORE
    $g $ts NaN NaN NaN $ts 50 * STU / 60.0 / SIN ADDVALUE DROP %> FOR
    $g
%> FOR STACKTOLIST 'result' STORE

{
    'data' $result
}
</warp-view-editor>
</div>

# Afficher un tableau personnalisé

<div style="width: 400px; height:200px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="tabular" chart-title="">
{
    'title' ''
    'columns'  [ 'Name' 'A' 'B' 'C' 'Link' ]
    'rows' [
        [ 'label X' 15 56 44 '<' 'a href="https://hexa-ai.fr/">Hexa-AI</' + 'a>' + ]
        [ 'label Y' 1 5 4 '<' 'a href="https://hexa-ai.fr/">Hexa-AI</' + 'a>' + ]
        [ 'label Z' 14 45 78 '<' 'img src="https://hexa-ai.fr/wp-content/uploads/2021/06/cropped-Logo-Ligne-Hexa-AI.png" height="40"/>' + ]
    ]
} 'result' STORE

{
    'data' $result
}
</discovery-tile>
</div>
<div style="min-height: 250px; width:600px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false"> 
{
    'title' ''
    'columns'  [ 'Name' 'A' 'B' 'C' 'Link' ]
    'rows' [
        [ 'label X' 15 56 44 '<' 'a href="https://hexa-ai.fr/">Hexa-AI</' + 'a>' + ]
        [ 'label Y' 1 5 4 '<' 'a href="https://hexa-ai.fr/">Hexa-AI</' + 'a>' + ]
        [ 'label Z' 14 45 78 '<' 'img src="https://hexa-ai.fr/wp-content/uploads/2021/06/cropped-Logo-Ligne-Hexa-AI.png" height="40"/>' + ]
    ]
} 'result' STORE

{
    'data' $result
}
</warp-view-editor>
</div>