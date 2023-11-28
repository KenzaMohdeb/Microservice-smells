# Analyse des mauvaises pratiques dans les logiciels à base de microservices

Le contexte de ce projet s'agit de faire une recherche approfondie sur les logiciels à base des microservices afin de detecter les mauvaises odeurs au niveau du code et de l'architecture et à la fin de la recherche, sortir avec un catalogue de mauvaises pratiques. Ensuite, faire une étude de cas sur quelques projets logiciels qui utilisent les microservices, dans laquelle nous utilisons des outils qui aident à analyses les projets étudiés.

# Catalogue de mauvaises odeurs
Aprés une recherche bibliographique et revue de la littérature, nous avons pu identidfier un catalogue de 21 odeurs de code et d'architecture dans les applications qui utilisent les microservices

# Collection des données

Nous avons considéré 5 projets GitHub qui sont conçus à base de microservices.

**1.Train ticket** [https://github.com/FudanSELab/train-ticket]: C’est un système de réservation de billets de train, et un projet conçu à base de microservices. Il contient 41 microservices. 

**2.SiteWhere** [ https://github.com/sitewhere/sitewhere ] : C’une plate-forme d’activation d’applications IoT qui est conçue avec l’architecture microservice. 

**3.Boutique en ligne** [ https://github.com/GoogleCloudPlatform/microservices-demo ] : C’est une application de commerce électronique en ligne qui est basée sur les microservices.  

**4.Vehicle tracking** [GitHub - mohamed-abdo/vehicle-tracking-microservices ] : C’est un système de suivi de véhicules en ligne, conçu avec l’architecture microservices.  

**5.Tea store** [ https://github.com/DescartesResearch/TeaStore ] : C’est une application de microservices distribuée, elle émule une boutique en ligne de base pour le thé et les fournitures de thé générés automatiquement. 


# Analyse Designite

Pour identifier les mauvaises odeurs sur Designite, nous devons télécharger le projet que nous voulons analyser et exécuter la commande suivante sur l’invité de commande : 

  `java -jar DesigniteJava.jar -i <MonProjet> -o <CsvResults>` 
  
Le plus grand avantage de Designite est qu’il nous affiche les résultats en détails sur l’invité de commande et nous exporte les résultats sous forme de fichiers csv.

**1. Designite Train ticket:**

**2. Designite SiteWhere:**

**3. Designite online Boutique:**

**4. Designite Vehicle tracking:**

**5. Designite Tea store:**


Tous les résultats de l'analyse se trouve dans le lien suivant: 



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

La requête retournera un rapport d'analyse sous format Json avec des informations sur les odeurs détectées et leurs temps d'exécution. 

Tous les résultats de l'analyse se trouve dans le lien suivant: 




# Analyse MicroFreshener

Pour utiliser l’outil, nous devons d’abord télécharger le référentiel sur GitHub, nous pouvons le faire à l’aide de la commande suivante : 

`git clone https://github.com/di-unipi-socc/microFreshener.git`  

La prochaine étape est d’exécuter le serveur, pour le faire nous devons lancer la commande suivante :  

`python manage.py runserver`

Le serveur sera opérationnel et en écoute à l'adresse suivante : http://127.0.0.1:8000/ 

Ensuite, nous devons exécuter le client qui est une application web Angular à travers la commande suivante:

`ng serve`

Puis ouvrir notre navigateur sur l’adresse : http://localhost:4200 

Afin de pouvoir analyser les applications avec l’outil MicroFreshener, nous devons générer un fichier microTosca qui décrit leur architecture en utilisant l’outil microMiner [GitHub - di-unipi-socc/microMiner]. 

Pour se faire, nous pouvons tout simplement lancer la commande suivante dans un environnement Unix : 

`sudo python -m microMiner generate strategy source target [test] [time] [name]`

**Exigences:** python 3.8 et privilèges sudo.



Les résultats se trouvent dans le lien suivant: 

