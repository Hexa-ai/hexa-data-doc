# Macros

Les macros sont des scripts écrits en langage [WarpScript](https://www.warp10.io/content/03_Documentation/04_WarpScript/).
Ces scripts permettent d'interagir avec les données et avec l'extérieur.

Les macros peuvent être utilisées de différentes manières dans Hexa-data :

* Appel cyclique sur intervalle de temps.
* Appel depuis une tuile d'un tableau de bord.
* Appel depuis une autre macro.

Les macros permettent de requêter la base de données WARP10 et de travailler sur ces données pour les analyser, les mettre en forme ou les supprimer.

## Le langage WarpScript

Le langage WarpScript dispose de plus de 1000 fonctions natives et permet entre autres de :

* Récupérer, supprimer ou modifier des enregistrements.
* Réorganiser les enregistrements dans le temps (combler des trous, aligner les timestamp, créer des points intermédiaires).
* Faire des appels à une API-REST.
* Effectuer des calculs mathématiques.
* Gérer des boucles, des conditions et des variables.

?> Cette documentation ne traite pas de l'apprentissage du langage WarpScript. Pour en savoir plus, n'hésitez pas à vous rendre sur la [documentation en ligne de WarpScript](https://www.warp10.io/content/03_Documentation/04_WarpScript/) (développé par [SenX](https://senx.io) Editeur de Warp10 et WarpScript).

### Particularités du WarpScript

* Langage à pile
* Usage de la notation polonaise inverse

![pile WarpScript](./_medias/pileWarpScript.png)

#### Exemple

Dans le WarpScript, tout mot clé est une macro et le passage de paramètre passe par la pile.

Addition de 2 et 3 et stockage dans la variable ```resultat```

```2 3 + 'resultat' STORE ```

#### Dans cette exemple:

* La macro ```+``` prend deux paramètres sur la pile, 2 et 3 et renvoie le résultat sur la pile.
* La macro ```STORE``` prend deux paramètres sur la pile: la valeur à stocker (ici le resultat de l'opération précédente) et le nom de la variable ```'resultat'```


