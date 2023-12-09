# Analyse des mauvaises pratiques dans les logiciels à base de microservices

Le contexte de ce projet s'agit de faire une recherche approfondie sur les logiciels à base des microservices afin de detecter les mauvaises odeurs au niveau du code et de l'architecture et à la fin de la recherche, sortir avec un catalogue de mauvaises pratiques. Ensuite, faire une étude de cas sur quelques projets logiciels qui utilisent les microservices, dans laquelle nous utilisons des outils qui aident à analyses les projets étudiés.

# Catalogue de mauvaises odeurs
Aprés une recherche bibliographique et revue de la littérature, nous avons pu identidfier un catalogue de 21 odeurs de code et d'architecture dans les applications qui utilisent les microservices

# Collection des projets open source

Nous avons considéré 5 projets GitHub qui sont conçus à base de microservices.

**1.Train ticket** [https://github.com/FudanSELab/train-ticket]: C’est un système de réservation de billets de train, et un projet conçu à base de microservices. Il contient 41 microservices. 

**2.SiteWhere** [ https://github.com/sitewhere/sitewhere ] : C’une plate-forme d’activation d’applications IoT qui est conçue avec l’architecture microservice. 

**3.Boutique en ligne** [ https://github.com/GoogleCloudPlatform/microservices-demo ] : C’est une application de commerce électronique en ligne qui est basée sur les microservices.  

**4.Vehicle tracking** [ https://github.com/mohamed-abdo/vehicle-tracking-microservices ]  : C’est un système de suivi de véhicules en ligne, conçu avec l’architecture microservices.  

**5.Tea store** [ https://github.com/DescartesResearch/TeaStore ] : C’est une application de microservices distribuée, elle émule une boutique en ligne de base pour le thé et les fournitures de thé générés automatiquement. 


# Analyse Designite

Pour identifier les mauvaises odeurs sur Designite, nous devons télécharger le projet que nous voulons analyser et exécuter la commande suivante sur l’invité de commande : 

  `java -jar DesigniteJava.jar -i <MonProjet> -o <CsvResults>` 
  
Le plus grand avantage de Designite est qu’il nous affiche les résultats en détails sur l’invité de commande et nous exporte les résultats sous forme de fichiers csv.

**1. Designite Train ticket:**

![Train ticket](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/train-ticket%20designite.png)

**2. Designite SiteWhere:**
![SiteWhere](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/DesigniteSiteWhere.png)

**3. Designite online Boutique:**
![Online boutique](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/DesigniteBoutique.png)

**4. Designite Vehicle tracking:**
![Vehicle tracking](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/DesigniteVehicle.png)

**5. Designite Tea store:**
![Tea store](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/DesigniteTeaStore.png)

Tous les résultats de l'analyse se trouve dans les liens suivants: 

[Designite Train ticket](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/DesigniteTrainticke)

[Designite TeaStore](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/DesigniteTeaStore)

[Designite OnlineBoutique](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/DesigniteOnlineBoutique)

[Designite SiteWhere](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/DesigniteSitewhere)

[Designite VehicleTracking](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/DesigniteVehicleTracking)


# Analyse MSANose

Cet outil peut détecter 11 mauvaises odeurs (de code et d’architecture).  

Pour l’utiliser, il suffit de télécharger le répertoire qui est accessible sur GitHub [GitHub - cloudhubs/msa-nose]. 

Ensuite, nous devons ajouter le fichier jar w4sj sur notre répertoire mvn local après avoir le télécharger sur notre machine en lançant la commande suivante sur le terminal : 

`mvn install:install-file -Dfile=<chemin-vers-le-fichier-jar> -DgroupId=com.sciss -DartifactId=ws4j -Dversion=1.0.1 -Dpackaging=jar`

Pour générer les setters et les getters MSANose utilise le plugin lombok, il suffit juste de le télécharger ou de l’intégrer à l'ide sur lequel nous travaillons.  

Pour commencer l’analyse de nos cinq projets, nous exécutons le projet MSANose sur notre IDE, pour notre cas nous avons choisi intellig.  

Pour l’analyse, il faut utiliser les points de terminaisons qui sont utilisées par MSANose. Pour se faire nous devons envoyer une requête HTTP POST à l'un de ces points de terminaison avec un corps JSON spécifique. Cela déclenchera l'analyse correspondante sur le code source de chaque projet. 

Nous avons utilisé l’invité de commande pour lancer les requêtes, voici à quoi ressemble la commande :  

`curl -X POST -H "Content-Type: application/json" -d '{ "pathToCompiledMicroservices": "/chemin/vers/le/projet/", "organizationPath": "", "outputPath": "" }' http://adresse-du-serveur/api/v1/rapport`

![SiteWhereMSANose](https://github.com/KenzaMohdeb/Microservice-smells/blob/main/R%C3%A9sultats%20MSANose/SitewhereCommandeMSA.png)

La requête retournera un rapport d'analyse sous format Json avec des informations sur les odeurs détectées et leurs temps d'exécution. 

Tous les résultats de l'analyse se trouve dans le lien suivant: [https://github.com/KenzaMohdeb/Microservice-smells/tree/main/R%C3%A9sultats%20MSANose](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/R%C3%A9sultats%20MSANose)




# Analyse MicroFreshener

Pour utiliser l’outil, nous devons d’abord télécharger le référentiel sur GitHub, nous pouvons le faire à l’aide de la commande suivante : 

`git clone https://github.com/di-unipi-socc/microFreshener.git`  

La prochaine étape est d’exécuter le serveur, pour le faire nous devons lancer la commande suivante :  

`python manage.py runserver`

Le serveur sera opérationnel et en écoute à l'adresse suivante : http://127.0.0.1:8000/ 

![serveur](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/Capture%20d'%C3%A9cran%202023-11-25%20135554.png)

Ensuite, nous devons exécuter le client qui est une application web Angular à travers la commande suivante:

`ng serve`

Puis ouvrir notre navigateur sur l’adresse : http://localhost:4200 

![client](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/Capture%20d'%C3%A9cran%202023-11-25%20174850.png)

Afin de pouvoir analyser les applications avec l’outil MicroFreshener, nous devons générer un fichier microTosca qui décrit leur architecture en utilisant l’outil microMiner [GitHub - di-unipi-socc/microMiner ]. 

Pour se faire, nous pouvons tout simplement lancer la commande suivante dans un environnement Unix : 

`sudo python -m microMiner generate strategy source target [test] [time] [name]`

voici un exemple de fichier résultant: [https://github.com/KenzaMohdeb/Microservice-smells/blob/main/R%C3%A9sultats%20MicroFreshener/BoutiqueOline.yml](https://github.com/KenzaMohdeb/Microservice-smells/blob/main/R%C3%A9sultats%20MicroFreshener/BoutiqueOline.yml)

**Exigences:** python 3.8 et privilèges sudo.

Voici un aperçu de l'analyse avec MicroFreshener: 
![analyse](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/Online%20boutique.png)

Les étoiles sont des instances de l'odeur "Wobbly service interaction" et les enveloppes sont des instances de l'odeur "endpoints smell". 

Par exemple, si on clique sur l'étoile au niveau du noeud "orders", nous aurons la description de l'odeur et des solutions de refactoring. 
![orders](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/Capture%20d'%C3%A9cran%202023-11-25%20142513.png)

Et si on clique sur l'enveloppe au niveau du noeud "Shipping", nous aurons aussi la description de l'odeur et des solutions de refactoring, et nous pouvons appliquer et enregister le refactoring appliqué.
![shipping](https://github.com/KenzaMohdeb/Microservice-smells/blob/Images/Capture%20d'%C3%A9cran%202023-11-25%20142609.png)

Toutes les captures d'écrans se trouve dans le lien suivant: [https://github.com/KenzaMohdeb/Microservice-smells/tree/main/R%C3%A9sultats%20MicroFreshener](https://github.com/KenzaMohdeb/Microservice-smells/tree/main/R%C3%A9sultats%20MicroFreshener)




