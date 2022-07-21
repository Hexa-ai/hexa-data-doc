# Bar_Chart

La tuile de type display permet d'afficher du texte ou du HTML. Avec cette tuile vous pouvez par exemple:
 * Afficher la derniere valeur d'une variable/GTS
 * Afficher le resultat d'une macro
 * Générer un lien hypertexte
 * Afficher une image avec la balise HTML ```<img/>```.


## Afficher la dernière valeur d'une variable/GTS

### Exemple d'affichage d'une variable/GTS

<div style="width: 700px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="bar">
    NOW 'now' STORE
    1 4 <% DROP NEWGTS 'g' STORE
    1 10 <% 'ts' STORE $g $now $ts STU * - NaN NaN NaN RAND ADDVALUE DROP %> FOR
    $g
    %> FOR
</discovery-tile>

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 

    // Requète de récupération des données (FETCH)
    { 
        'token' $readToken //Jeton de lecture
        'class' 'edgeDemo.r2.mesu.temp.chAdam' //Nom de la variable/GTS à récupèrer
        'labels' {} 
        'end' NOW 4 h + 
        'count' 1 
    } FETCH  0 GET VALUES 0 GET 'data' STORE 

    // Contenu de la tuile
    { 
        'data' $data 
        'globalParams' { 'unit' '°C' }
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