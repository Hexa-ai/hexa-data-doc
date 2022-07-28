# Input Text

La tuile de type input permet de rentrer du texte/chiffre.

Avec cette tuile vous pouvez par exemple:
 * Rentrer un texte ou un chiffre, cette valeur sera émise en évènement (ex: recherche, filte...)

## Envoyer une valeur avec évènement

<div style="width: 250px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:text">
    { 'data' 12 'events' [
    { 'type' 'variable' 'tags' 'saisieText' 'selector' 'myVar' }
    ]
    'globalParams' { 'scheme' 'ECTOPLASM' } }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(saisieText)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>

Dans cette exemple:

* La variable est initialisée à 12 par ``` 'data' 12 ``` dans le script

* La variable peut être modifier par un texte/chiffre, on va émettre un évènement qui pourra être utiliser dans une autre tuile. Dans notre exemple, on tape ce qu'on veut dans l'input et celui-ci est récupéré par la tuile d'affichage (display) via au paramètre EventHandler.

* Sur la tuile qui va récupérer la valeur (display), il faut mettre ```type=variable,tag=saisieText``` dans  le champs EventHandler du formulaire.


### Script
<div style="min-height: 100px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 
    // Contenu de la tuile 
    { 'data' 12 'events' [
    { 'type' 'variable' 'tags' 'saisieText' 'selector' 'myVar' }
    ]
    'globalParams' { 'scheme' 'ECTOPLASM' } }
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