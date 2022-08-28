# Svg

## Exemple d'un symbole de débimètre

<div style="width: 400px; height:200px;">
<discovery-tile url="https://sandbox.senx.io/api/v0/exec" type="svg">
<%
  'unit' STORE
  'mesure' STORE

  '<' 'svg ' +
    'viewBox="0 0 100.00001 127.55481"' +
    'version="1.1"' +
    'id="svg5"' +
    'xmlns="http://www.w3.org/2000/svg"' +
    'xmlns:svg="http://www.w3.org/2000/svg">' +
    '<'  + 'defs ' +
      'id="defs2" />' +
    '<' + 'g ' +
      'id="layer1"' +
      'transform="translate(-44.480645,-39.206935)">' +
      '<' + 'ellipse ' +
        'style="fill:none;stroke:#000000;stroke-width:1.03553;stroke-dasharray:none;stroke-opacity:1"' +
        'id="path2388"' +
        'cx="94.480652"' +
        'cy="89.206932"' +
        'rx="49.482239"' +
        'ry="49.482235" />' +
      '<' + 'circle ' +
        'style="fill:none;stroke:#000000;stroke-width:0.5;stroke-dasharray:none;stroke-opacity:1"' +
        'id="path2388-5"' +
        'cx="94.480652"' +
        'cy="89.206932"' +
        'r="44.534012" />' +
      '<' + 'g ' +
        'id="g2658"' +
        'transform="translate(3.5110189,-5.8208336)">' +
        '<path ' +
          'style="fill:none;stroke:#000000;stroke-width:1;stroke-dasharray:none;stroke-opacity:1"' +
          'd="m 86.235808,144.5672 v 27.51537 h 9.46765 v -27.21951 h -0.29586"' +
          'id="path2518" />' +
        '<' + 'path ' +
          'style="fill:none;stroke:#000000;stroke-width:0.462532;stroke-dasharray:none;stroke-opacity:1"' +
          'd="m 87.6252,144.50664 v 25.56541 h 6.688867 v -25.29051 h -0.209025"' +
          'id="path2518-6" />' +
      '<' + '/g>' +
      '<' + 'rect ' +
        'style="fill:none;stroke:#000000;stroke-width:0.668373;stroke-dasharray:none;stroke-opacity:1"' +
        'id="rect2572"' +
        'width="80.010834"' +
        'height="27.642868"' +
        'x="54.475235"' +
        'y="75.385498" />' +
      '<' + 'rect ' +
        'style="fill:none;stroke:#000000;stroke-width:0.5;stroke-dasharray:none;stroke-opacity:1"' +
        'id="rect2572-2"' +
        'width="78.264206"' +
        'height="25.896242"' +
        'x="55.348549"' +
        'y="76.258812" />' +
      '<' + 'text ' +
        'xml:space="preserve"' +
        'style="font-size:10.5833px;line-height:0;fill:none;stroke:#000000;stroke-width:0.494118;stroke-dasharray:none;stroke-opacity:1"' +
        'x="58.421169"' +
        'y="91.33992"' +
        'id="text2736"' +
        'transform="scale(0.98764729,1.0125072)">{{mesure}} {{unit}}' + '<' + '/text>' +
    '<' + '/g>' +
  '<' + '/svg>' + 
  { 
    'mesure' $mesure 
    'unit' $unit
  } TEMPLATE
%> 'svgFlowMeter' STORE

{
  'data' 70 'm3/h' @svgFlowMeter
}
</discovery-tile>
</div>
<div style="min-height: 800px; width: 800px;">
<warp-view-editor url="https://data.hexa-data.fr/api/v0/exec" width-px=800 theme="dark" id="editor horizontal-layout="false" show-result="false" show-execute="false" >
<%
  'unit' STORE
  'mesure' STORE

  '<' 'svg ' +
    'viewBox="0 0 100.00001 127.55481"' +
    'version="1.1"' +
    'id="svg5"' +
    'xmlns="http://www.w3.org/2000/svg"' +
    'xmlns:svg="http://www.w3.org/2000/svg">' +
    '<'  + 'defs ' +
      'id="defs2" />' +
    '<' + 'g ' +
      'id="layer1"' +
      'transform="translate(-44.480645,-39.206935)">' +
      '<' + 'ellipse ' +
        'style="fill:none;stroke:#000000;stroke-width:1.03553;stroke-dasharray:none;stroke-opacity:1"' +
        'id="path2388"' +
        'cx="94.480652"' +
        'cy="89.206932"' +
        'rx="49.482239"' +
        'ry="49.482235" />' +
      '<' + 'circle ' +
        'style="fill:none;stroke:#000000;stroke-width:0.5;stroke-dasharray:none;stroke-opacity:1"' +
        'id="path2388-5"' +
        'cx="94.480652"' +
        'cy="89.206932"' +
        'r="44.534012" />' +
      '<' + 'g ' +
        'id="g2658"' +
        'transform="translate(3.5110189,-5.8208336)">' +
        '<path ' +
          'style="fill:none;stroke:#000000;stroke-width:1;stroke-dasharray:none;stroke-opacity:1"' +
          'd="m 86.235808,144.5672 v 27.51537 h 9.46765 v -27.21951 h -0.29586"' +
          'id="path2518" />' +
        '<' + 'path ' +
          'style="fill:none;stroke:#000000;stroke-width:0.462532;stroke-dasharray:none;stroke-opacity:1"' +
          'd="m 87.6252,144.50664 v 25.56541 h 6.688867 v -25.29051 h -0.209025"' +
          'id="path2518-6" />' +
      '<' + '/g>' +
      '<' + 'rect ' +
        'style="fill:none;stroke:#000000;stroke-width:0.668373;stroke-dasharray:none;stroke-opacity:1"' +
        'id="rect2572"' +
        'width="80.010834"' +
        'height="27.642868"' +
        'x="54.475235"' +
        'y="75.385498" />' +
      '<' + 'rect ' +
        'style="fill:none;stroke:#000000;stroke-width:0.5;stroke-dasharray:none;stroke-opacity:1"' +
        'id="rect2572-2"' +
        'width="78.264206"' +
        'height="25.896242"' +
        'x="55.348549"' +
        'y="76.258812" />' +
      '<' + 'text ' +
        'xml:space="preserve"' +
        'style="font-size:10.5833px;line-height:0;fill:none;stroke:#000000;stroke-width:0.494118;stroke-dasharray:none;stroke-opacity:1"' +
        'x="58.421169"' +
        'y="91.33992"' +
        'id="text2736"' +
        'transform="scale(0.98764729,1.0125072)">{{mesure}} {{unit}}' + '<' + '/text>' +
    '<' + '/g>' +
  '<' + '/svg>' + 
  { 
    'mesure' $mesure 
    'unit' $unit
  } TEMPLATE
%> 'svgFlowMeter' STORE

{
  'data' 70 'm3/h' @svgFlowMeter
}
</warp-view-editor>
</div>