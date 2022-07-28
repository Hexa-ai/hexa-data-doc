# Bar_Chart

La tuile de type Bar Chart permet d'afficher un graphique en forme de barre. Avec cette tuile vous pouvez par exemple:
 * Afficher une ou plusieurs valeur(s) d'une variable/GTS
 * Afficher le resultat d'une macro

## Afficher une variable/GTS

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="bar">
NEWGTS 'edgeDemo.r1.mesu.temp.salon' RENAME 'g' STORE
  1 10 <% 'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP %> FOR
  $g

STACKTOLIST 'data' STORE
{ 'data' $data 'globalParams' { 'bar' { 'stacked' true 'scheme' 'ECTOPLASM' } } }
</discovery-tile>
</div>

### Script

Dans cette exemple:

* La variable interne ```$readToken``` (jeton d'identification)

* La variable de données qu'on souhaite afficher ```edgeDemo.r1.cons.temp.salon```

* Si on veut ajouter une variable de données il suffit de rajouter ```|```  puis la variable ```edgeDemo.r1.cons.temp.salon2```

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
    // Requète de récupération des données (FETCH)
    {   'token' $readToken
        'class' '~edgeDemo.r1.mesu.temp.salon' 
        'labels' {} 
        'start' NOW 1 d -
        'end' NOW
    } FETCH 'data' STORE
    { 'data' $values 'globalParams' { 'bar' { 'stacked' true 'scheme' 'ECTOPLASM' } } }
</warp-view-editor>


<style>
    discovery-tile {
        border: black;
        border-width:  1px;
        background-color: #3A3C4622;
        border-radius: 50px;
    }
</style>