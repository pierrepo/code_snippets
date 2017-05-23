# Entête de script

Pour rendre un script bash moins tolérant aux erreurs et aux déclarations implicites de variables.

    #!/bin/bash
    set -euo pipefail
    IFS=$'\n\t' 

* `-e` arrête le script à la première erreur rencontrée
* `-u` arrête le script lorsqu'une variable non définie est appelée
* `-o pipefail` arrête le script lorsqu'il y une erreur dans un pipe
* `IFS=$'\n\t'` définie le séparateur de mot avec la tabulation ou le retour à la ligne (mais pas l'espace)

Source : <http://redsymbol.net/articles/unofficial-bash-strict-mode/>. 

Voir également l'article <http://jvns.ca/blog/2017/03/26/bash-quirks/> pour de bonnes pratiques Bash.


