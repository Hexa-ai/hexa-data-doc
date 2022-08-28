# Export CSV

<div style="width: 200px; height:250px;">
<discovery-tile url="https://data.hexa-data.fr/api/v0/exec" type="csv-export" chart-title="" debug>
<%
    // discovery-tile
    [] 'gts' STORE
    1 500 <% 'i' STORE
    NEWGTS $i TOSTRING RENAME 'g' STORE
    1 172800 <%
    'ts' STORE $g $ts RAND + STU * NOW + NaN NaN NaN RAND ADDVALUE DROP
    %> FOR
    $gts $g +! 'gts' STORE
    %> FOR

    // List of classnames
    [] 'classnames' STORE
    $gts <% NAME $classnames SWAP +! 'classnames' STORE %> FOREACH
    // CSV header
    [ 'timestamp' ] $classnames APPEND 'header' STORE
    // CSV Body init
    [ ] 'body' STORE


    // Append datas to CSV Body
    [ $gts [ ] <%
    'parameter' STORE
    $parameter  0 GET 'ts' STORE
    $parameter 7 GET 'values' STORE


    [ $ts ] $values APPEND 'line' STORE

    [ $line ] $body APPEND 'body' STORE

    [ NOW NaN NaN NaN 0 ]

    %> MACROREDUCER ] REDUCE DROP

    // Append boy to CSV
    [ $header ] $body APPEND 'return' STORE

    // Return the CSV
    $return
%> 'formatCsv' STORE

{ 
    'data'  @formatCsv
    'globalParams' { 'button' { 'label' 'Téléchargement' } }
}
</discovery-tile>
</div>