# Input Date

La tuile de type input permet de rentrer une date et une heure . 

Avec cette tuile vous pouvez par exemple:
 * Rentrer une date et un horaire, cette valeur sera ensuite émise en évènement

## Envoyer une date et un horaire avec évènement

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:date">
    { 'data' NOW 'events' [
    { 'type' 'variable' 'tags' 'myTime' 'selector' 'myTime' }
    ] }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myTime)"}'>
  {
    'data' $myTime ISO8601
  }
</discovery-tile>
</div>

Dans cette exemple:

* La variable est initialisée à NOW (maintenant) par ``` 'data' NOW ``` dans le script

* La variable est modifiée en choississant une autre date et un horaire, on va émettre un évènement qui pourra être utiliser dans une autre tuile. Dans notre exemple, on tape ce qu'on veut dans l'input et celui-ci est récupéré par la tuile d'affichage (display) via au paramètre EventHandler.

* Sur la tuile qui va récupérer la valeur (display), il faut mettre ```type=variable,tag=myTime``` dans le champs EventHandler du formulaire.

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" > 

    // Contenu de la tuile
    { 'data' NOW 'events' [
    { 'type' 'variable' 'tags' 'myTime' 'selector' 'myTime' }
    ] }

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