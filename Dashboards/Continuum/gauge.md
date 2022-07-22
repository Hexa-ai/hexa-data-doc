# Gauge

La tuile de type gauge permet d'afficher jauge. Avec cette tuile vous pouvez par exemple:
 * Afficher une variable/GTS
 * Afficher le resultat d'une macro


## Afficher la dernière valeur d'une variable/GTS

### Exemple d'affichage d'une variable/GTS 

<div style="width: 400px; height:300px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="gauge">
{ 'data' 42 'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

### Script

Dans cette exemple:

* La variable interne ```$readToken``` (jeton d'identification)

* Les variables de données qu'on souhaite afficher ```edgeDemo.r2.mesu.temp.chAdam```

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 

    // Requète de récupération des données (FETCH)
    { 
        'token' $readToken 
        'class' 'edgeDemo.r2.mesu.temp.chAdam'
        'labels' {} 
        'end' NOW 4 h + 
        'count' 1 
    } FETCH  0 GET VALUES 0 GET 'data' STORE 

    // Contenu de la tuile
    { 
        'data' $data 
        'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' }
    }

</warp-view-editor>
</div>

### Exemple d'affichage d'une macro

Pour cet example la macro est definie dans la tuile

Syntaxe pour une macro locale:
```@nomDeLaMacro```

<div style="width: 200px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="gauge">
{ 'data' 35.7 'globalParams' { 'maxValue' 100 'unit' '°C' 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

### Script

Dans cet example nous passons 1.02 en paramètre de la macro.

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
// Definition de la macro
// La macro demande un paramètre et effectue (20 + 15) * le parametre
//
<% 'coef' STORE 20 15 + $coef * %> 'maMacro' STORE
// Contenu de la tuile
{
  'data' 1.02 @maMacro
  'globalParams' {  'unit' '°C' 'showLegend' true 'scheme' 'ECTOPLASM' } 
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