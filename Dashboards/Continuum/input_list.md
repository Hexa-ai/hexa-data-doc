# Input List

La tuile de type input permet de rentrer une date et une heure . 

Avec cette tuile vous pouvez par exemple:
 * Choisir un texte ou un chiffre dans une liste définit, une fois validé, cette valeur sera ensuite émise en évènement

## Envoyer une valeur qui fait partie d'une liste avec évènement

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="input:list">
    {
    'data' [ "admiring" "adoring" "agitated" "amazing" "angry" "awesome" "backstabbing" "berserk" "big" "boring" "clever" "cocky" "compassionate" "condescending" "cranky" "desperate" "determined" "distracted" "dreamy" "drunk" "ecstatic" "elated" "elegant" "evil" "fervent" "focused" "furious" "gigantic" "gloomy" "goofy" "grave" "happy" "high" "hopeful" "hungry" "insane" "jolly" "jovial" "kickass" "lonely" "loving" "mad" "modest" "naughty" "nauseous" "nostalgic" "pedantic" "pensive" "prickly" "reverent" "romantic" "sad" "serene" "sharp" "sick" "silly" "sleepy" "small" "stoic" "stupefied" "suspicious" "tender" "thirsty" "tiny" "trusting"  ]
    'globalParams' { 'input' { 'value' 'focused' } }
    'events' [
    { 'type' 'variable' 'tags' 'myVar' 'selector' 'myVar' }
    ] }
</discovery-tile>
</div>

<div style="width: 200px; height:50px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display" options='{"eventHandler":"type=variable,tag=(myVar)"}'>
  {
    'data' $myVar
  }
</discovery-tile>
</div>

Dans cette exemple:

* La variable est initialisée une liste de nom par ``` 'data' NOW ``` dans le script

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