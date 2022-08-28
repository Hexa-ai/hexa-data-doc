# Line / Area / Bar

## Paramètres spécifique au widget ```bar``` ( attribut ```bar``` de ```globalParams```)

| Attribut         | Type    | Description                        |
|------------------|---------|------------------------------------|
| ```horizontal``` | booléen | Affiche les barres à l'horizontal  |
| ```stacked```    | booléen | Affiche les barres en mode empilés |

## Paramètres par série

| Attribut           | Type   | Description                                             | Valeurs                                                                                  |
|--------------------|--------|---------------------------------------------------------|------------------------------------------------------------------------------------------|
| ```datasetColor``` | string | Couleur du jeux de données                              |                                                                                          |
| ```type```         | string | Type d'affichage pour le jeux de données                | line, area, scatter, step-area,<br>spline-area, spline, step, step-after,<br>step-before |
| ```xAxis```        | LONG   | Dans le cas d'axes X multiples, index de l'axe concerné |                                                                                          |
| ```yAxis```        | LONG   | Dans le cas d'axes Y multiples, index de l'axe concerné |                                                                                          |


## Exemple d'affichage ```line```

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="line">
NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

NEWGTS 'dgeDemo.r1.cons.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' {  'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' 'showDots' true } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'token' $readToken 
  'class' '~edgeDemo.r1.mesu.temp.salon|edgeDemo.r1.cons.temp.salon' 
  'labels' {}
  'start' NOW 1 d -
  'end' NOW
} FETCH 'result' STORE

{ 
  'data' $data 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' true 
    'scheme' 'ECTOPLASM' 
    'showDots' true
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```line``` avec données personnalisées (list de maps)

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="line">
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - ] %> FOR ] %> 'rand' STORE

[
  { 'label' 'A' 'values' @rand }
  { 'label' 'B' 'values' @rand }
] 'result' STORE

STACKTOLIST 'data' STORE
{ 'data' $result 'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' 'showDots' true } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
<% [ 0 10 <% DROP [ RAND 10 * 5 -   RAND 10 * 5 - ] %> FOR ] %> 'rand' STORE
[
  { 'label' 'A' 'values' @rand }
  { 'label' 'B' 'values' @rand }
] 'result' STORE 

{ 
  'data' $result 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' false 
    'scheme' 'ECTOPLASM' 
    'showDots' true
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```line``` et ```area```

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="line">
NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

NEWGTS 'dgeDemo.r1.cons.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' { 'showControls' true 'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' 'showDots' true } 'params' [ { 'type' 'bar' } ] }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'token' $readToken 
  'class' '~edgeDemo.r1.mesu.temp.salon|edgeDemo.r1.cons.temp.salon' 
  'labels' {}
  'start' NOW 1 d -
  'end' NOW
} FETCH 'result' STORE

{ 'data' $data 'globalParams' { 'showControls' true 'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' 'showDots' true } 'params' [ { 'type' 'bar' } ] }

</warp-view-editor>
</div>

## Exemple d'affichage ```area```

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="area">
{ 'data' 400 @fake/simpleSinusoid 'globalParams' {  'showControls' true 'showLegend' true 'showRangeSelector' true 'scheme' 'ECTOPLASM' 'showDots' false } }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'data' 400 @fake/simpleSinusoid 
  'globalParams' {  
    'showControls' true 
    'showLegend' true 
    'showRangeSelector' true 
    'scheme' 'ECTOPLASM' 
    'showDots' false 
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```bar```

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="bar">
NEWGTS 'dgeDemo.statVisites' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' 'showDots' false } }
</discovery-tile>
</div>
<div style="min-height: 350px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'token' $readToken 
  'class' '~edgeDemo.statVisites' 
  'labels' {}
  'start' NOW 1 d -
  'end' NOW
} FETCH 'result' STORE

{ 
  'data' $data 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' false 
    'scheme' 'ECTOPLASM' 
    'showDots' false
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```bar``` horizontale

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="bar">
NEWGTS 'dgeDemo.statVisites' RENAME 'g' STORE
  1 5 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' 'showDots' false  'bar' { 'horizontal' true } } }
</discovery-tile>
</div>
<div style="min-height: 350px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'token' $readToken 
  'class' '~edgeDemo.statVisites' 
  'labels' {}
  'start' NOW 1 d -
  'end' NOW
} FETCH 'result' STORE

{ 
  'data' $data 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' false 
    'scheme' 'ECTOPLASM' 
    'showDots' false
    'bar' {
      'horizontal' true 
    }
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```bar``` horizontale avec des données personnalisées

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="bar">
{ 
  'data' {
    'title' 'Test'
    'columns' [ 'A' 'B' 'C' 'D' ]
    'rows' [
      [ 'label X' 15 56 44 22 ]
      [ 'label Y' 1 5 4 2 ]
      [ 'label Z' 14 45 78 12 ]
    ]
  } 
  'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' 'showDots' false  'bar' { 'horizontal' true } } 
}
</discovery-tile>
</div>
<div style="min-height: 350px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'data' {
    'title' 'Test'
    'columns' [ 'A' 'B' 'C' 'D' ]
    'rows' [
      [ 'label X' 15 56 44 22 ]
      [ 'label Y' 1 5 4 2 ]
      [ 'label Z' 14 45 78 12 ]
    ]
  } 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' false 
    'scheme' 'ECTOPLASM' 
    'showDots' false  
    'bar' { 'horizontal' true } 
  } 
}
</warp-view-editor>
</div>

## Exemple d'affichage ```bar``` horizontale avec des données personnalisées (emplilées)

<div style="width: 700px; height:300px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="bar">
{ 
  'data' {
    'title' 'Test'
    'columns' [ 'A' 'B' 'C' 'D' ]
    'rows' [
      [ 'label X' 15 56 44 22 ]
      [ 'label Y' 1 5 4 2 ]
      [ 'label Z' 14 45 78 12 ]
    ]
  } 
  'globalParams' {  'showLegend' true 'showRangeSelector' false 'scheme' 'ECTOPLASM' 'showDots' false  'bar' { 'horizontal' true 'stacked' true } } 
}
</discovery-tile>
</div>
<div style="min-height: 350px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'data' {
    'title' 'Test'
    'columns' [ 'A' 'B' 'C' 'D' ]
    'rows' [
      [ 'label X' 15 56 44 22 ]
      [ 'label Y' 1 5 4 2 ]
      [ 'label Z' 14 45 78 12 ]
    ]
  } 
  'globalParams' {  
    'showLegend' true 
    'showRangeSelector' false 
    'scheme' 'ECTOPLASM' 
    'showDots' false  
    'bar' { 
      'horizontal' true 
      'stackerd' true 
    } 
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