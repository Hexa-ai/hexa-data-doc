# Display

La tuile de type display permet d'afficher du texte ou du HTML. Avec cette tuile il est possible :
 * Afficher la derniere valeur d'une variable/GTS
 * Afficher le resultat d'une macro
 * Générer un lien hypertexte
 * Afficher une image avec la balise HTML ```<img/>```

## Afficher la dernière valeur d'une variable/GTS

<div style="width: 200px; height:250px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="display" chart-title="">
  {
    'data' 18
    'globalParams' { 'unit' '°C' 'scheme' 'ECTOPLASM' }
  }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false"> 
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
    'globalParams' { 'unit' '°C' 'scheme' 'ECTOPLASM' }
}
</warp-view-editor>
</div>

## Exemple d'affichage d'une macro

Dans cet example nous utilisons la macro ```@utils/getWather``` pour récupèrer des informations météo depuis le service [OpenWeather](https://openweathermap.org/)

<div style="width: 200px; height:250px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="display" chart-title="">
{
    'data' 32.3
    'globalParams' { 'unit' '°C' }
}
</discovery-tile>
</div>

La macro ```@utils/getWather``` récupère les informations météo aux coordonnées GPS ```48.609539 -2.494735```. L'exemple récupère ensuite l'attribut ```temp``` de la map ```main``` afin de n'afficher que la température.

?> Dans l'exemple ci-dessous ```xxxOpenWeatherTokenxxx``` est à remplacer par un jeton [OpenWeather](https://openweathermap.org/) valide.

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
// Contenu de la tuile
{
    'data' 48.609539 -2.494735 'xxxOpenWeatherTokenxxx' @utils/getWather 'main' GET 'temp' GET
    'globalParams' { 'unit' '°C' }
}
</warp-view-editor>
</div>

## Exemple d'affichage d'un lien hypertexte

<div style="width: 300px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display">
 {
  'data' '<' 'a href="https://hexa-ai.fr/" target="_blank"' + '>Hexa-AI<' + '/a>' +
  'globalParams' { 'bgColor' '#fffff' 'fontColor' '#bc5100' }
  }
</discovery-tile>
</div>
<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
 {
  'data' '<' 'a href="https://hexa-ai.fr/" target="_blank"' + '>Hexa-AI<' + '/a>' +
  'globalParams' { 'bgColor' '#f57f17' 'fontColor' '#bc5100' }
}
</warp-view-editor>
</div>




## Exemple d'affichage d'une image

<div style="width: 300px; height:250px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="display">
{
    'data' '<' 'img src="https://hexa-ai.fr/wp-content/uploads/2021/06/cropped-Logo-Ligne-Hexa-AI.png" target="_blank"' + '>' +
}
</discovery-tile>
</div>

### Script

<div style="min-height: 300px; width: 800px;">
<warp-view-editor url="https://warp.senx.io/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
{
    'data' '<' 'img src="https://hexa-ai.fr/wp-content/uploads/2021/06/cropped-Logo-Ligne-Hexa-AI.png" target="_blank"' + '>' +
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