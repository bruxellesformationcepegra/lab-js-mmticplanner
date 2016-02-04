# Planning du pôle Management & MultimediaTIC

## Pitch

**! Attention, ce projet fait appel à une API interne à Bruxelles Formation, elle n'est accessible que depuis le réseau de Bruxelles Formation !**

Le pôle Management & MultimediaTIC possède un outil de planification de ses formations et de ses salles de cours. 

Une petite API permet d'accéder à quelques données, que vous allez exploiter avec jQuery AJAX.

## Tâches

### Page index

Sur cette page, vous devrez afficher toutes les formations en cours et à venir dans une liste déroulante.

Les données sont accessibles via http://mmtic.brufor.be/api/trainingcalendar

Lors du choix d'une formation dans la liste déroulante, vous devrez afficher dans une table toutes les réservations existantes pour la formation choisie via http://mmtic.brufor.be/api/booking/bytraining?id=*ID_FORMATION_CHOISIE* 

Affichez dans la table la **date** et le **local** de chaque réservation.

### Page calendrier

Sur cette page, vous devrez afficher toutes les réservations entre un intervalle de date. Je vous conseille d'utiliser un plugin de calendrier tel que Datepicker de jQuery UI pour sélectionner les dates.

Vous pouvez récupérez les données via http://mmtic.brufor.be/api/booking/get?startDate=*DATE_DEBUT*&enddate=*DATE_FIN* et les afficher sous forme de table, avec pour chaque réservation la **date**, le **diminutif de la formation**, le **local** et le **commentaire** éventuel.

Les réservations ne seront pas triées par date. Si vous souhaitez les trier, il vous faudra utiliser la méthode `Array.sort()` et une manière de comparer les dates. Le plus simple étant d'utiliser moment.js (http://momentjs.com/)

## Comment je sais quelles données récupérer ?!?

Les données sont toutes renvoyées en JSON. 

*OK, mais comment connaître leur format ?*

Jouez à Sherlock Holmes ! Utilisez la console Firebug, un `console.log()`, `console.table()` ou POSTMAN (extension Chrome). 

## Points importants

Veillez à:

    -vérifier si vous **recevez des données** et à afficher un message si vous ne recevez rien
    -vérifier si un **message d'erreur** vous est renvoyé, et si oui, l'afficher
    -vérifier si les données (comme les dates) sont **présentes** et **valides** et à afficher une erreur si ce n'est pas le cas; par exemple si la date de fin est plus petite que la date de début
    -afficher des indicateurs de **chargement** et à **bloquer** l'interface pendant que la requête est en cours
    
**Happy coding**