## Entête de scripts

Permet de rendre plus strict un script bash

    #!/bin/bash
    set -euo pipefail
    IFS=$'\n\t' 

* `-e` stoppe le script à la première erreur rencontrée
* `-u` stoppe le script lorsqu'une variable non définie est appelée
* `-o pipefail` stoppe le script lorsqu'il y une erreur dans un pipe
* `IFS=$'\n\t'` définie le séparateur de mot avec la tabulation ou le retour à la ligne (mais pas l'espace)

Source : 

* http://redsymbol.net/articles/unofficial-bash-strict-mode/

