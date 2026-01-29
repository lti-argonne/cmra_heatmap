# cmra_heatmap

Prototype de visualisation cartographique des points de découverte des molettes d’Argonne, sous forme de **carte de densité (heatmap)** et de **courbes d’iso-densité**, à partir des coordonnées géographiques issues du Corpus des décors à la molette sur les sigillées d’Argonne (**CMRA**).

Cette application constitue un outil exploratoire destiné à l’analyse spatiale et à la discussion scientifique, et ne se substitue pas aux outils de recherche internes du Corpus.

---

## Principe général

L’application repose sur un document HTML autonome s’appuyant sur la bibliothèque **Leaflet** et des extensions JavaScript associées.  
Elle permet :

- l’affichage d’un fond cartographique (tuiles raster issues du projet *Digital Atlas of the Roman Empire – DARE*, miroir technique) ;
- la visualisation des **points de découverte** sous forme de heatmap ;
- le calcul dynamique de **grilles de densité** et de **courbes d’iso-densité** à partir des points ;
- l’activation ou la désactivation de couches contextuelles (villes antiques, rivières, routes, lacs) ;
- l’export de la carte courante en image PNG haute définition, incluant échelle et cartouches.

L’ensemble des calculs est effectué côté client, sans serveur applicatif.

---

## Structure technique

- **HTML / JavaScript**
  - Leaflet (affichage cartographique)
  - leaflet-heat (heatmap)
  - d3-contour (iso-densité)
  - html2canvas (export PNG)

- **Données**
  - un fichier CSV léger contenant les coordonnées géographiques des points de découverte ;
  - des couches vectorielles (rivières, routes, villes, lacs) chargées sous forme de scripts JavaScript (variables globales), destinées à être ultérieurement converties en GeoJSON strict.

---

## Points de découverte

Les points correspondent aux sites de découverte des molettes d’Argonne inventoriées dans le **CMRA**  
(*Corpus des décors à la molette sur les sigillées d’Argonne*).

Structure du fichier CSV :  

numéro de molette | numéro de site | LAT | LON  

Chaque point est actuellement pondéré de manière uniforme (valeur = 1).  
La carte ne représente ni la fréquence réelle des molettes par site ni leur chronologie.

---

## Usage et statut du dépôt

Ce dépôt est destiné à un **usage expérimental et interne** par les chercheurs et collaborateurs du projet **CMRA** :

- exploration spatiale,
- mise au point d’outils de visualisation,
- préparation de figures pour discussion ou publication.

Il s’agit d’un prototype évolutif, sans garantie de stabilité à long terme, et susceptible d’évoluer vers une intégration plus large dans l’écosystème numérique du projet CMRA.

---

## Crédits

- Données : **CMRA** —  
  P. Van Ossel (éd.), L. Bakker (éd.), P. Ciezar (coll.)
- Fond cartographique : *Digital Atlas of the Roman Empire* (J. Ahlfeldt, projet DARE – miroir technique)
- Développement : P. Ciezar
