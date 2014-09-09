## Print

    >>> a = 12
    >>> b = 3.4567
    >>> c = "hello"

    >>> print a, b, c
    12 3.4567 hello
    >>> print "a= %i b= %.2f c= %s" %(a, b, c)
    a= 12 b= 3.46 c= hello

    >>> print "a= %8i b= %8.2f c= %8s" %(a, b, c)
    a=       12 b=     3.46 c=    hello

    >>> print("a= {0} b= {1} c={2}").format(a, b, c)
    a= 12 b= 3.4567 c=hello
    >>> print("a= {0:8d} b= {1:8.2f} c={2:8s}").format(a, b, c)
    a=       12 b=     3.46 c=hello  
    >>> print("a= {0:<8d} b= {1:<8.2f} c={2:<8s}").format(a, b, c)
    a= 12       b= 3.46     c=hello  
    >>> print("a= {0:0>8d} b= {1:0>8.2f} c={2:0>8s}").format(a, b, c)
    a= 00000012 b= 00003.46 c=000hello
    >>> print("a= {val_a} b= {val_b} c={val_c}").format(val_a=a, val_c=c, val_b=b)
    a= 12 b= 3.4567 c=hello

    >>> test = "a= {0} b= {1} c={2}".format
    >>> print(test(a,b, c))
    a= 12 b= 3.4567 c=hello
    >>> test = "a= {val_a} b= {val_b} c={val_c}".format
    >>> print(test(val_c = c, val_a = a, val_b = b))
    a= 12 b= 3.4567 c=hello

    

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

## Modèle de script

    #! /usr/bin/env python
    # -*- coding: utf-8 -*-
    
    """Short description of program

    More description.
    """
    
    #==============================================================================
    # Modules
    #==============================================================================
    ### Sstandard modules


    ### Third party modules

    #==============================================================================
    # Info
    #==============================================================================

    __author__ = "Toto, titi"
    __copyright__ = "Copyright 2014, Toto & Titi"
    __credits__ = ["Tutu"]
    __license__ = "GPL"
    __version__ = "0.1"
    __maintainer__ = "toto"
    __email__ = "toto@bob.com"
    
    #==============================================================================
    # Functions
    #==============================================================================

    def my_finction():
        """
        Do this and that
        """
        # do someting
        

    #==============================================================================
    # Main
    #==============================================================================
    if __name__ == "__main__":
        # do something here




