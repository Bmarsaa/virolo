# Virolo

Appli web gratuite qui crée des balades moto sur petites routes sinueuses (boucles ou trajets de A à B), puis les découpe en points GPS à suivre dans Waze.

**Utiliser l'appli :** https://bmarsaa.github.io/virolo/

## Ce qu'elle fait

- **Boucle ou trajet de A à B**, à partir d'une adresse, de votre position ou d'un point sur la carte.
- **Longueur en kilomètres ou en temps de roulage**, et **direction de départ** (Nord, Est, Sud, Ouest).
- **3 niveaux de virages** : plusieurs variantes sont calculées, puis classées selon la quantité de virages. Le tracé est coloré, de la ligne droite (bleu) aux lacets (rouge).
- **Passer par** un col, un village ou un point de vue. Les cols et points de vue s'affichent sur la carte.
- **Modifier le tracé à la main** : faire glisser un point, en ajouter ou en supprimer.
- **Profil d'altitude** : dénivelé positif et altitude maximale.
- **Carburant** : alerte si un tronçon sans station dépasse l'autonomie de la moto.
- **Pause café** suggérée vers le milieu du parcours.
- **Heure de retour** estimée, pauses comprises.
- **Options** : éviter autoroutes, péages, ferries et grandes villes ; goudron seulement ou chemins acceptés.
- **Mes balades** : enregistrement dans le navigateur.
- **Partage** par lien ou QR code.
- **Export** : points GPS pour Waze, fichier GPX, lien Google Maps.

## Pourquoi des points GPS pour Waze ?

Waze n'importe pas de trajet complet : il n'accepte ni fichier GPX, ni liste de points de passage. Virolo place donc des points sur les routes choisies. Vous les ajoutez comme arrêts dans Waze, ou vous les ouvrez un par un.

Le bouton **« Optimiser les points pour Waze »** compare le tracé au trajet le plus rapide entre deux points. Il n'ajoute un point que là où Waze couperait par une autre route.

## Installer sur le téléphone

Ouvrez l'adresse de l'appli dans Chrome (Android) ou Safari (iPhone), puis choisissez « Ajouter à l'écran d'accueil ».

## Fonctionnement

Une seule page HTML, sans serveur ni clé API. Elle s'appuie sur des services gratuits basés sur OpenStreetMap :

| Service | Rôle |
|---|---|
| [Valhalla](https://valhalla1.openstreetmap.de) (FOSSGIS) | Itinéraires moto et altitudes |
| [Nominatim](https://nominatim.openstreetmap.org) | Recherche d'adresses |
| [Overpass](https://overpass-api.de) | Cols, points de vue, stations-service, cafés, villes |
| OpenStreetMap France / Esri | Fonds de carte |

Ces services publics peuvent être lents ou saturés par moments. L'appli continue alors sans les informations manquantes.

Données cartographiques © contributeurs OpenStreetMap.
