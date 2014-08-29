## Taille d'un objet en Python
    
    >>> t = "test"
    >>> v = 123
    >>> import sys
    # sys.getsizeof() donne la taille en octets
    >>> sys.getsizeof(t)
    41
    >>> sys.getsizeof(v)
    24

## Server web minimaliste

    python -m SimpleHTTPServer 8080

Ouvre un serveur web sur le port 8080. Accessible depuis un navigateur internet à l'adresse http://localhost:8080/ ou http://0.0.0.0:8080/ 

## Exemples avec le microframework web Bottle

https://gist.github.com/Arthraim/994641
