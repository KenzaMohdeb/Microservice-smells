# Analyse des mauvaises pratiques dans les logiciels à base de microservices

Le contexte de ce projet s'agit de faire une recherche approfondie sur les logiciels à base des microservices afin de detecter les mauvaises odeurs au niveau du code et de l'architecture et à la fin de la recherche, sortir avec un catalogue de mauvaises pratiques. Ensuite, faire une étude de cas sur quelques projets logiciels qui utilisent les microservices, dans laquelle nous utilisons des outils qui aident à analyses les projets étudiés.

# Catalogue de mauvises odeurs
Aprés une rechrche bibliographique et revue de la littérature, nous avons pu identidfier un catalogue de 21 odeurs de code et d'architecture dans les applications qui utilisent les microservices

# Collection des données

Nous avons considéré 5 projets GitHub qui sont conçus à base de microservices.

1.Train ticket [https://github.com/FudanSELab/train-ticket]: C’est un système de réservation de billets de train, et un projet conçu à base de microservices. Il contient 41 microservices. 

2.SiteWhere [ https://github.com/sitewhere/sitewhere ] : C’une plate-forme d’activation d’applications IoT qui est conçue avec l’architecture microservice. 

3.Boutique en ligne [ https://github.com/GoogleCloudPlatform/microservices-demo ] : C’est une application de commerce électronique en ligne qui est basée sur les microservices.  

4.Vihicle tracking [GitHub - mohamed-abdo/vehicle-tracking-microservices: a vehicle tracking system (microservices complaint architecture) ] : C’est un système de suivi de véhicules en ligne, conçu avec l’architecture microservices.  

5.Tea store [ https://github.com/DescartesResearch/TeaStore ] : C’est une application de microservices distribuée, elle émule une boutique en ligne de base pour le thé et les fournitures de thé générés automatiquement. 


# Analyse Designite

Pour identifier les mauvaises odeurs sur Designite, nous devons télécharger le projet que nous voulons analyser et exécuter la commande suivante sur l’invité de commande : 

  java -jar DesigniteJava.jar -i <MonProjet> -o <CsvResults> 
  
L’avantage de Designite est qu’il nous affiche les résultats en détails sur l’invité de commande et nous exporte les résultats sous forme de fichiers csv. 



# Analyse MSANose

# Analyse MicroFreshener
