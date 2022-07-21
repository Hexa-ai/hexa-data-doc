# Display

La tuile de type display permet d'afficher du texte ou du HTML. Avec cette tuile vous pouvez par exemple:
 * Afficher la derniere valeur d'une variable/GTS
 * Afficher le resultat d'une macro
 * Générer un lien hypertexte
 * Afficher une image avec la balise HTML ```<img/>```.


## Afficher la dernière valeur d'une variable/GTS

### Exemple d'affichage d'une variable/GTS

<div style="width: 200px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" chart-title="Température">
  {
    'data' 18
    'globalParams' { 'unit' '°C' }
  }
</discovery-tile>
</div>

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false"> 
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
</div>

### Exemple d'affichage d'une macro

<div style="width: 200px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" chart-title="Température">
<% 'coef' STORE 523 5 + $coef * %> 'demoMacro' STORE
{
    'data' 12 @demoMacro
    'globalParams' { 'unit' '°C' }
}
</discovery-tile>
</div>

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
// Definition de la macro
<% 'coef' STORE 523 5 + $coef * %> 'demoMacro' STORE

// Contenu de la tuile
{
    'data' 12 @demoMacro
    'globalParams' { 'unit' '°C' }
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