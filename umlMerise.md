# Kékés Voyages (UML + MERISE)


![héritage](https://simplonline.co/_next/image?url=https%3A%2F%2Fsimplonline-v3-prod.s3.eu-west-3.amazonaws.com%2Fmedia%2Fimage%2Fwebp%2Fc19849b0-c035-4391-b8f3-5e4fa4c00caf.webp&w=1280&q=75)

 
 
                                                Rim idrissi zouggari (CDA)




## Table des matières

1. [1.La conception](#con)
2. [2.Contexte du projet ](#pro)
3. [3.Élaborer un MCD.](#liv) 
4. [4.Élaborer un MLD.](#liv) 
5. [5.Élaborer un MPD.](#liv) 	



### Semaine du 05/12

## Pourquoi la conception <a name="con"></a>
Pour lire et analyser un cahier des charges en vue de créer un dossier de spécification de l’application à développer. La méthode adoptée c'est Merise. L’accent sera mis essentiellement sur l’élaboration du MCD et  MLD.

concevoir la modélisation UML d'un système simplifié de réservation de vols pour une agence de voyages ainsi que la conception de la base de données avec MERISE.


## Contexte du projet <a name="pro"></a>
LE client, une agence de voyages, souhaite proposer la possibilité de réserver en ligne des billets d'avion à leurs clients.

Votre mission est de concevoir à l'aide du standard UML la modélisation de la plateforme.

La plateforme devra permettre que :

    Un vol est ouvert à la réservation et refermé sur ordre de la compagnie.
    Un vol peut être annulé par la compagnie
    Un client peut réserver un ou plusieurs vols, pour des passagers différents.
    Une réservation concerne un seul vol et un seul passager.
    Une réservation peut être annulée ou confirmée.
    Un vol a un aéroport de départ et un aéroport d’arrivée.
    Un vol a un jour et une heure de départ, et un jour et une heure d’arrivée.
    Un vol peut comporter des escales dans des aéroports.
    Une escale a une heure d’arrivée et une heure de départ.
    Chaque aéroport dessert une ou plusieurs villes.
    Des compagnies aériennes proposent différents vols.
    
##Livrable <a name="liv"></a>
Pour la base de données :
# Conceptuel 
* Un MCD : Modéle conceptuel des données
* Pourquoi réaliser un modèle conceptuel de données (MCD) ?
Un modèle conceptuel de données (MCD) est réalisé pour représenter les données d'un système d'information. 
Les données sont représentées sous forme d'entités et d'associations entre entités.
Les entités et associations sont les briques essentielles de réalisation d'un MCD. Ces briques essentielles sont complétées par:

    Les propriétés des entités

    Les types de données des propriétés
    
# Un vol est ouvert à la réservation et refermé sur ordre de la compagnie.
3 entités 
Vol / Réservation / Compagnie 
# Un client peut réserver un ou plusieurs (La cardinalité(1.n)) vols, pour des passagers différents.
2 entités 
Client /Passager
# Un vol a un aéroport de départ et un aéroport d’arrivée.
1 entité
Aéroport
# Un vol a un jour et une heure de départ, et un jour et une heure d’arrivée.
un vol à des propriétés date départ ,heure de départ , date d'arrivée , heure d'arrivée
# Un vol peut comporter des escales dans des aéroports.
1 entité 
Escale
# Une escale a une heure d’arrivée et une heure de départ.
une escale a des propriétés(attributs) heure d'arrivée , heure départ
# Chaque aéroport dessert une ou plusieurs (1,n) villes.
1 entité 
ville
# Entités : Vol , Compagnie , Réservation , Client , Passager , Aéroport , Escale , Ville.
# Propiétés (attributs): vol(date départ ,heure de départ , date d’arrivée , heure d’arrivée ); Réservation(n°réservation ) ; Compagnie(nom compagnie); Client( nom client ,prenom client , date de naissance ,adresse mail); Passager(nom passager, prenom passager); Aéroport(nom aéroport); Escale (heure d’arrivée , heure de départ) ; Ville(nom ville).

L'association :L'association est le lien sémantique qui unit deux ou plusieurs entités. L'association n'existe qu'au travers des entités qu'elle relie.
On désigne l'association par un verbe à l'infinitif (reserver,comporter,appartenir,proposer,contenir)

La cardinalité :
Une valeur minimale de 0, indique que la participation est optionnelle.
Une valeur minimale de 1, indique que la participation est obligatoire.
Une valeur maximale de 1, indique l'unique participation.
Une valeur maximale de n, indique une infinité de participations. 
* Une réservation concerne un seul 1 vol et un seul 1 passager .
Aéroport dessert une ou plusieurs (1,n) villes
Un client peut réserver un ou plusieurs (La cardinalité(0.n)) vols, pour des passagers différents.

(voir l'image MCD.pdf)

Pour élaborer un MCD il faut :
- recenser les propriétés du système
- regrouper des propriétés par entité pour établir un dictionnaire de données
- construire des entités
- rechercher des associations
- rechercher des cardinalités entre association
    
# Organisationel / logique
* Un MLD : Modèle Logique de Données
 Passage du MCD au MLD
Le MCD (Modèle Conceptuel de Données) ne peut pas être implanté dans une base de données sans modification.
Il est obligatoire de transformer ce modèle. On dit qu’on effectue un passage du modèle conceptuel de données vers le modèle logique de
données.
Le MLD pourra être implanté dans une base de données relationnelle.

Règles de passage du MCD au MLD :
* a) Une entité du MCD devient une relation, c’est à dire une table (Réservation)
* b) Son identifiant devient la clé primaire de la relation (N°réservation)
* c) Les autres propriétés deviennent les attributs de la relation.
# MLD
la table réservation (N°réservation : c'est la clé primaire )
la table passager(N°passport : c'est la clé primaire ,nom passager, prenom passager)         
# Physique 
* Un MPD: Modèle Physique des Données
*  on crée les tables dont on met le nom dans l'en-tête, ensuite à l'intérieur de ces tables on répertorie l'ensemble des champs qu'elles contiennent. Dans un second temps, il faut souligner les champs qui sont des clés primaires et mettre un “#” devant les champs qui sont des clés étrangères.
*  la table réservation (souligner N°réservation : c'est la clé primaire )
la table passager(souligner N°passport : c'est la clé primaire ,nom passager, prenom passager)  
pas # des clés étrangères 


Pour l'application :
* Un dictionnaire de données
* Des règles de gestion
* Un diagramme de cas d'utilisation
* Un diagramme de classe
* Un diagramme de Séquence

 
