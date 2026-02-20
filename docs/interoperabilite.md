# INTEROPERABILITE
***20/02/2026 / Thomas***

## WEBSERVICES

Avantage de l’utilisation des Web Services :

- Mise à disposition globale et contrôlée des données spatiales
- Un temps de chargement « côté client » performant
- Une interopérabilité entre les outils SIG

### WMS

Une URL renvoie une image.

```
https://data.geopf.fr/wms-r/wms?
SERVICE=WMS&
VERSION=1.3.0&
REQUEST=GetMap&
BBOX=-328617.5056973813334%2C4708315.165103063919%2C373275.0382083536824%2C6122175.265506482683&CRS=EPSG%3A3857&
WIDTH=418&
HEIGHT=843&
LAYERS=BDTOPO-DIFF-HYDROGRAPHIE&
STYLES=&
FORMAT=image%2Fpng&
DPI=96&
MAP_RESOLUTION=96&
FORMAT_OPTIONS=dpi%3A96&
TRANSPARENT=TRUE
```

### WMTS

Une URL renvoie une imagette de taille fixe 256 par 256 pixels.

```
https://data.geopf.fr/wmts?
SERVICE=WMTS&
REQUEST=GetTile&
VERSION=1.0.0&
LAYER=GEOGRAPHICALGRIDSYSTEMS.EDUGEO.TOULOUSE1948&
STYLE=normal&
FORMAT=image%2Fpng&
TILEMATRIXSET=PM_6_16&
TILEMATRIX=12&
TILEROW=1498&
TILECOL=2063
```

### WFS



### TMS

Page puis colonne puis ligne puis image.

```
https://tile.openstreetmap.org/
8/
128/
86.png
```

## Le Catalogage / Métadonnées

Axe de qualité de notre discipline !

La notion de diffusion de donnée a été confirmée par la possibilité de partager des données de qualité.

- Des données de qualité => exhaustives, propres et géométriquement correctes
- Des données documentées => fiches de métadonnées suivant des normes de rédaction (ISO 19115 / 19139, INSPIRE, DCAT)
- Des données diffusables => catalogue de données / métadonnées, Catalogue Service Web CSW
- Des données réutilisables => accessibles, ouvertes

## Extract Transform Load

Un outils fiable => le traitement automatisé

![](https://supports.idgeo.fr/cpgeom/2025-2027/A2-Interoperabilite/res/interop_etl.png)

- Extact : le processus d'extraction doit convertir les données dans un format adapté à une transformation ultérieure
- Transform : Nettoyage, Filtrage, Enrichissement, Division, (spliting), Regroupement.
- Load : Les données transformées peuvent être chargé dans la base cible.

### Spatial ETL

L’ETL Spatial, aussi connu sous l’appellation GTL (« Geographic Transformation and Load »), propose les mêmes fonctionnalités que l’ETL, appliquées à la manipulation des données géographiques.

L’ETL spatial permet :
- De synchroniser des bases entre-elles,
- De traduire des jeux de données géographiques d’un format vers un autre (OGR / GDAL),
- De restructurer complètement le modèle de données et l’adapter au modèle cible, à l’aide d’unités de traitement (transformers chez FME) qui modifient la structure, les attributs et la géométrie des entités.

### Transformations géospatiales communes

- Reprojection : possibilité de convertir des données spatiales entre un système de coordonnées et un autre.
- Transformations spatiales : possibilité de modéliser des interactions spatiales et de calculer des prédicats spatiaux.
- Transformations topologiques : possibilité de créer des relations topologiques entre des ensembles de données disparates.
- Re-symbolisation : la possibilité de modifier les caractéristiques cartographiques d'une entité, comme la couleur ou le style de trait.
- Géocodage : possibilité de convertir des attributs de données tabulaires en données spatiales.

![](https://supports.idgeo.fr/cpgeom/2025-2027/A2-Interoperabilite/res/ETL_traitement_img_Sat_drawio_1.png)

