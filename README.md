Fonctionnement de l'application
Ajout de véhicules et de clients :

1-L'utilisateur peut ajouter des voitures et des camions dans le parc automobile, en spécifiant leurs attributs.
De même, les clients peuvent être ajoutés en précisant leurs informations personnelles (nom, prénom, numéro de permis, etc.).
Lister les véhicules disponibles :

2-L'application affiche les véhicules disponibles en vérifiant leur statut. Les véhicules loués sont exclus de cette liste.

3-Louer un véhicule :

Pour louer un véhicule, l'utilisateur fournit le numéro de permis du client et l'immatriculation du véhicule.
Le système vérifie que le véhicule est disponible et qu'il peut être loué. Si le véhicule est louable et disponible, le statut du véhicule est mis à jour, et le véhicule est ajouté aux locations en cours du client.
Retourner un véhicule :

4-Pour retourner un véhicule, l'utilisateur fournit à nouveau le numéro de permis du client et l'immatriculation du véhicule.
Le système vérifie si le client a bien loué ce véhicule. Si oui, le véhicule est marqué comme disponible, et il est retiré des locations en cours du client.
                         
                          
                          RAPPORT


1. Encapsulation
Dans la classe client, les informations privées telles que nom, prenom, numerodepermisdeconduire, numerodetelephone, et locationencours ne sont pas accessibles directement en dehors de la classe. Des méthodes getter (ex., getNom(), getPrenom()) permettent un accès contrôlé aux informations nécessaires sans exposer directement les attributs, protégeant ainsi l'intégrité des données.

2. Héritage
L'héritage est appliqué en créant une structure de classes dérivée pour représenter des types de véhicules spécifiques.Dans le code, la classe abstraite Vehicule sert de classe mère, et Voiture et Camion en héritent. La classe Vehicule définit des attributs et des méthodes communs pour tous les véhicules, comme immatriculation, marque, modele, statut, et calculerPrixLocation(). Les classes Voiture et Camion héritent de Vehicule et étendent ses fonctionnalités, telles que les attributs nombredeplace et typedecarburant pour Voiture ou capacitedechargement et nombreessieux pour Camion.

3. Polymorphisme
Le polymorphisme est mis en œuvre à travers l'utilisation de méthodes abstraites et d'interfaces. La méthode abstraite calculerPrixLocation() dans Vehicule est redéfinie dans Voiture et Camion. De plus, l'interface Louable oblige les classes Voiture et Camion à implémenter les méthodes louer() et retourner(). En utilisant le polymorphisme, le programme peut interagir avec des objets de type Louable de manière générique, ce qui rend le code plus flexible.



4. Gestion des Exceptions
 Les exceptions personnalisées ClientNonAutoriseException et VehiculeIndisponibleException  signalent des erreurs spécifiques de . Par exemple, dans la méthode louer() de Voiture, une VehiculeIndisponibleException est levée si la voiture n'est pas disponible pour la location. De même, dans la méthode louerVehicule(client client, Vehicule vehicule), une VehiculeIndisponibleException est levée si le véhicule n’est pas disponible ou non louable.

