# Annotation

### Exemple d'affichage d'annotations

<div style="width: 800px; height:150px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="annotation" chart-title="annotation chart">
0 0 <% 
  'j' STORE
  NEWGTS 'serie' $j TOSTRING + RENAME 'gts' STORE
  0 300 <%
    'ts' STORE $gts $ts RAND + STU * NOW +  NaN NaN NaN "t" ADDVALUE DROP
  %> FOR
  $gts
%> FOR STACKTOLIST 'result' STORE
{
    'data' $result
    'globalParams' {  
        'showControls' false 
        'showLegend' false 
        'showRangeSelector' false 
        'scheme' 'ECTOPLASM' 
    }
}
</discovery-tile>
</div>

<div style="min-height: 350px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
0 0 <% 
  'j' STORE
  NEWGTS 'serie' $j TOSTRING + RENAME 'gts' STORE
  0 300 <%
    'ts' STORE $gts $ts RAND + STU * NOW +  NaN NaN NaN "t" ADDVALUE DROP
  %> FOR
  $gts
%> FOR STACKTOLIST 'result' STORE
{
    'data' $result
    'globalParams' {  
        'showControls' false 
        'showLegend' false 
        'showRangeSelector' false 
        'scheme' 'ECTOPLASM' 
    }
}
</warp-view-editor>


<style>
    discovery-tile {
        border: black;
        border-width:  1px;
        background-color: #3A3C4622;
        border-radius: 50px;
    }
</style>