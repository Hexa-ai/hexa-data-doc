# Line

La tuile de type line permet d'afficher des courbes. Avec cette tuile vous pouvez par exemple:
 * Afficher une ou plusieurs courbe(s) d'une ou plusieurs variable(s)/GTS
 * Afficher le resultat d'une macro

## Afficher une ou plusieurs courbe(s) d'une ou plusieurs variable(s)/GTS

### Exemple d'affichage de 2 courbes


<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="line">
NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

NEWGTS 'dgeDemo.r1.cons.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g



STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' {  'showLegend' true 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

### Script

Dans cette exemple:

* La variable interne ```$readToken``` (jeton d'identification)

* Les variables de données qu'on souhaite afficher ```edgeDemo.r1.mesu.temp.salon``` et ```dgeDemo.r1.cons.temp.salon```

* La plage de requete (les 24 dernières heures):
   * ```'start' NOW 1 d -``` (timestamp actuel moin 1 jour)
   * ```'end' NOW``` (timestamp actuel)

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{ 
  'token' $readToken 
  'class' '~edgeDemo.r1.mesu.temp.salon|edgeDemo.r1.cons.temp.salon' 
  'labels' {}
  'start' NOW 1 d -
  'end' NOW
} FETCH 'data' STORE

{ 'data' $data 'globalParams' {  'showLegend' true 'scheme' 'ECTOPLASM' } }

</warp-view-editor>
</div>


## Afficher le resultat d'une macro

### Exemple d'affichage d'une macro

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="line">
NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

NEWGTS 'dgeDemo.r1.cons.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' {  'showControls' true 'showLegend' true 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
<%
  [
    NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
    1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
    $g
    NEWGTS 'dgeDemo.r1.cons.temp.salon' RENAME 'g' STORE
    1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
    $g
  ]
%> 'maMacro' STORE
{ 
  'data' @maMacro
  'globalParams' {  'showControls' true 'showLegend' true 'scheme' 'ECTOPLASM' } 
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