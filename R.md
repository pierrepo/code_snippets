## Ordonner les éléments d'un dataframe suivant une ou plusieurs colonnes

    > d <- data.frame(x= c("A", "B", "A", "C"), 
                      y = c("Pif", "Paf", "Plouf", "Plouf"),
                      z = c(3, 1, 1, 2))
    > d
      x     y z
    1 A   Pif 3
    2 B   Paf 1
    3 A Plouf 1
    4 C Plouf 2
    
    > d[ order(d[,"z"]), ]
      x     y z
    2 B   Paf 1
    3 A Plouf 1
    4 C Plouf 2
    1 A   Pif 3

avec la function `order()`. Le tri se fait par ordre croissant sur la colonne "z".

    > d[ order(d[,"z"], d[, "x"]), ]
      x     y z
    3 A Plouf 1
    2 B   Paf 1
    4 C Plouf 2
    1 A   Pif 3

Le tri se fait maintenant par ordre croissant sur la colonne "z" puis par ordre croissant sur la colonne "x".

    > d[ order(-d[,"z"]), ]
      x     y z
    1 A   Pif 3
    4 C Plouf 2
    2 B   Paf 1
    3 A Plouf 1

Le tri se fait par ordre décroissant sur la colonne "z".

    > d[ order(d[,3], d[, 1]), ]
      x     y z
    3 A Plouf 1
    2 B   Paf 1
    4 C Plouf 2
    1 A   Pif 3

La notation par indice de colonne fonctionne également.

Source : http://stackoverflow.com/questions/1296646/how-to-sort-a-dataframe-by-columns-in-r


## Utiliser le symbole angstroem dans l'étiquette d'un axe de graphique

    ylab = expression(bold(paste('RMSF ', (ring(A)))))

Et pour l'anstroem au carré :

    xlab=expression(bold(paste('ASA (',  ring(A)^2, ')')))


## Utiliser une variable dans une légende de graphique

    a = 3
    plot (1, 1, xlab = bquote(CO[2] ~ "emissions in" ~ .(a) ~ ring(A)^2))
    
Le notation est `.(nom_de_la_variable)`


## Générer un graphique vide

    plot(1, xaxt="n", yaxt="n", xlab="", ylab="", bty="n", col="white")



