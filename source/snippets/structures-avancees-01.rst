Structures avancées
###################

Planning de la journée
======================

::

    position = int(input())
    nbLieux = int(input())

    nbPossibles = 0

    for loop in range(nbLieux):
       distance = int(input()) - position
       if distance >= 0:
          if distance <= 50:
             nbPossibles = nbPossibles + 1
       else:
          if distance >= -50:
             nbPossibles = nbPossibles + 1
          
    print(nbPossibles)

Autre possibilité
-----------------

::

    posActuelle = int(input())
    nbVillages = int(input())
    nbAccessibles = 0

    for loop in range(nbVillages):
       posVillage = int(input())
       ecart = posActuelle - posVillage

       if ecart < 0:
          ecart = -ecart

       if ecart <= 50:
          nbAccessibles = nbAccessibles + 1

    print(nbAccessibles) 

    
Etape la plus longue
====================

::



    nbJours = int(input())

    record = 0

    for loop in range(nbJours):
       distance = int(input())
       
       if distance > record:
          record = distance
          
    print(record)


Types d'arbres (reformulation de conditions)    
============================================

Solution naïve
--------------

::

    hauteur = int(input())
    folioles = int(input())

    if hauteur <= 5:
       if folioles >= 8:
          print("Tinuviel")

    if hauteur >= 10:
       if folioles >= 10:
          print("Calaelen")

    if hauteur <= 8:
       if folioles <= 5:
          print("Falarion")

    if hauteur >= 12:
       if folioles <= 7:
          print("Dorthonion")

Solution intelligente
---------------------

Voici une solution plus intelligente qui fait appel au schéma suivant :

..  figure:: figures/structures_avancees_schema_FR
    :align: center

::

    hauteur = int(input())
    nbFolioles = int(input())
    if hauteur < 9:
       if nbFolioles > 6:
          print("Tinuviel")
       else:
          print("Falarion")
    else:
       if nbFolioles < 8:
          print("Dorthonion")
       else:
          print("Calaelen")