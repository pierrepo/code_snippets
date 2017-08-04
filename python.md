# Formatage de chaînes de caractères

    >>> a = 12
    >>> b = 3.4567
    >>> c = "hello"

    >>> print a, b, c
    12 3.4567 hello
    >>> print "a= %i b= %.2f c= %s" %(a, b, c)
    a= 12 b= 3.46 c= hello

    >>> print "a= %8i b= %8.2f c= %8s" %(a, b, c)
    a=       12 b=     3.46 c=    hello

La méthode `print("xxx {y}".format())` est la méthode d'affichage compatible Python 2.7 et Python 3.x.

    >>> print("a= {0} b= {1} c={2}".format(a, b, c))
    a= 12 b= 3.4567 c=hello
    >>> print("a= {2} b= {0} c={1}".format(a, b, c))
    a= hello b= 12 c=3.4567
    >>> print("a= {} b= {} c={}".format(a, b, c))
    a= 12 b= 3.4567 c=hello
    
    >>> print("a= {0:8d} b= {1:8.2f} c={2:8s}".format(a, b, c))
    a=       12 b=     3.46 c=hello  
    >>> print("a= {0:<8d} b= {1:<8.2f} c={2:<8s}".format(a, b, c))
    a= 12       b= 3.46     c=hello  
    >>> print("a= {0:0>8d} b= {1:0>8.2f} c={2:0>8s}".format(a, b, c))
    a= 00000012 b= 00003.46 c=000hello
    >>> print("a= {0:*^8d} b= {1:*^8.2f} c={2:*^8s}".format(a, b, c))
    a= ***12*** b= **3.46** c=*hello**

    >>> print("a= {val_a} b= {val_b} c={val_c}".format(val_a=a, val_c=c, val_b=b))
    a= 12 b= 3.4567 c=hello

    >>> test = "a= {0} b= {1} c={2}".format
    >>> print(test(a,b, c))
    a= 12 b= 3.4567 c=hello
    >>> test = "a= {val_a} b= {val_b} c={val_c}".format
    >>> print(test(val_c = c, val_a = a, val_b = b))
    a= 12 b= 3.4567 c=hello

    >>> my_list = [12, 3.4567, 'hello']
    >>> print("a= {0} b= {1} c={2}".format(*my_list))
    a= 12 b= 3.4567 c=hello
    >>> print("a= {} b= {} c={}".format(*my_list))
    a= 12 b= 3.4567 c=hello

    >>> my_dic = {'a_value': 12, 'b_value': 3.4567, 'c_value': 'hello'}
    >>> print("a= {a_value} b= {b_value} c={c_value}".format(**my_dic))
    a= 12 b= 3.4567 c=hello

    >>> print("Les {} sont obtenues avec {{}}".format("accolades"))
    Les accolades sont obtenues avec {}

Le site <https://pyformat.info/> fait une comparaison entre l'opérateur `%` et la méthode `.format()`


# Taille d'un objet en Python

    >>> t = "test"
    >>> v = 123
    >>> import sys
    # sys.getsizeof() donne la taille en octets
    >>> sys.getsizeof(t)
    41
    >>> sys.getsizeof(v)
    24

Attention, cette méthode ne fonctionne a priori pas avec des conteneurs (liste, tuple, dictionnaire).


# Serveur web minimaliste

Avec Python 2.7 :

    python -m SimpleHTTPServer 8080

Avec Python 3.x :

    python -m http.server 8080

Ces commandes ouvrent un serveur web sur le port 8080. Accessible depuis un navigateur internet à l'adresse <http://localhost:8080/> ou <http://0.0.0.0:8080/>. 

Exemples plus élaborés avec le microframework web Bottle, pour Python 2.7 : <https://gist.github.com/Arthraim/994641>


# Modèle de script

    #! /usr/bin/env python3
    
    """Short description of program

    More description here.
    """
    
    __author__ = "Toto, titi"
    __copyright__ = "Copyright 2014, Toto & Titi"
    __credits__ = ["Tutu"]
    __license__ = "GPL"
    __version__ = "0.1"
    __maintainer__ = "toto"
    __email__ = "toto@bob.com"
    
    # import modules from standard library

    # import modules from third parties

    def my_function():
        """
        First description line

        Mode detailed description.

        Parameters
        ----------
        param1 : int
            The first parameter.
        param2 : str
            The second parameter.

        Returns
        -------
        bool
            True if successful, False otherwise.

        """
        # function core
        

    # start of main program
    if __name__ == "__main__":
        # do something here


# Commande dans subprocess avec un timeout

Pour éviter que les commandes lancées avec subprocess ne s'arrêtent pas.

http://stackoverflow.com/questions/1191374/subprocess-with-timeout

Code multiplateforme compatible Python 2.x et 3.x

    import subprocess, threading

    class Command(object):
    def __init__(self, cmd):
        self.cmd = cmd
        self.process = None

    def run(self, timeout):
        def target():
            print 'Thread started'
            self.process = subprocess.Popen(self.cmd, shell=True)
            self.process.communicate()
            print 'Thread finished'

        thread = threading.Thread(target=target)
        thread.start()

        thread.join(timeout)
        if thread.is_alive():
            print 'Terminating process'
            self.process.terminate()
            thread.join()
        print self.process.returncode

    command = Command("echo 'Process started'; sleep 2; echo 'Process finished'")
    command.run(timeout=3)
    command.run(timeout=1)

Sortie :

    Thread started
    Process started
    Process finished
    Thread finished
    0
    Thread started
    Process started
    Terminating process
    Thread finished
    -15

Autre méthode, mais à partir de Python 3.3 ou avec le module subprocess32 pour Python 2.x :

    from subprocess import STDOUT, check_output as qx

    output = qx(cmd, stderr=STDOUT, timeout=seconds)

 
