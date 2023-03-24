# Les Échos Graphiques

Bienvenue sur le compte GitHub du service infographie des Échos, qui regroupe tous les formats interactifs publiés depuis septembre 2020.

Tu y trouveras également les [modèles](#📄-modèles) et [recettes](#🧑‍🍳-recettes) pour la création d’embeds ou de grands-formats interactifs avec [Svelte](https://svelte.dev), ainsi que les [formats récurrents](#🌳-formats-récurrents) se répétant d’année en année.

Enfin, il existe une collection de [composants d’interface](#🏗️-composants-dinterface) utiles (titraille, boutons, tooltip, slider, etc.).

```
ooooo                              oooooooooooo           oooo
`888'                              `888'     `8           `888
 888          .ooooo.   .oooo.o     888          .ooooo.   888 .oo.    .ooooo.   .oooo.o
 888         d88' `88b d88(  "8     888oooo8    d88' `"Y8  888P"Y88b  d88' `88b d88(  "8
 888         888ooo888 `"Y88b.      888    "    888        888   888  888   888 `"Y88b.
 888       o 888    .o o.  )88b     888       o 888   .o8  888   888  888   888 o.  )88b
o888ooooood8 `Y8bod8P' 8""888P'    o888ooooood8 `Y8bod8P' o888o o888o `Y8bod8P' 8""888P'
```

---

*Note : une version récente de [Node.js](https://nodejs.org) (>= 16) doit être installée.*

## 📄 Modèles

- [Embed vierge](https://github.com/EchosGraphiques/embed-template)

	```bash
	git clone https://github.com/EchosGraphiques/embed-template mon-super-embed
	cd mon-super-embed
	npm install
	```

- [Grand-format en scrollytelling](https://github.com/EchosGraphiques/grand-format-scrollytelling-template)

	```bash
	git clone https://github.com/EchosGraphiques/grand-format-scrollytelling-template mon-super-grand-format
	cd mon-super-grand-format
	npm install
	```

## 🧑‍🍳 Recettes

### 🗺️ Cartes

- [Carte de France, choroplèthe par département](https://github.com/EchosGraphiques/recette-carte-france-choroplethe)
	- Au choix : France métropolitaine avec ou sans Outre-mer
	- Au choix : catégories (données discrètes) ou classes (données continues)
- [Carte de France, avec cercles proportionnels](https://github.com/EchosGraphiques/recette-carte-france-cercles)
	- Au choix : France métropolitaine avec ou sans Outre-mer
	- Au choix : par département ou sur une sélection de communes
- Carte de l’UE, choroplèthe par pays
	- Au choix : catégories (données discrètes) ou classes (données continues)
- Carte des États-Unis, choroplèthe par état
	- Au choix : catégories (données discrètes) ou classes (données continues)
- [Globe interactif avec cercles proportionnels par pays](https://github.com/EchosGraphiques/recette-globe)

### 📈 Autres embeds 
- [Courbe(s) interactive(s)](https://github.com/EchosGraphiques/recette-courbes)
- Tableau simple
- [Quiz](https://github.com/EchosGraphiques/recette-quiz)

### 🖥️ Pleine page
- Tableau personnalisable et triable

## 🌳 Formats récurrents

- [Classement des meilleurs cabinets de recrutement](https://github.com/EchosGraphiques/grand-format-cabinets-recrutement)

- [Classement des champions de la croissance](https://github.com/EchosGraphiques/grand-format-champions-croissance)

- [Classement des meilleures écoles de commerce et d’ingénieurs](https://github.com/EchosGraphiques/embed-startxchange)

## 🏗️ Composants d’interface

Pour une documentation complète des composants d’interface disponibles (titraille, boutons, tooltip, slider, etc.), voir [@EchosGraphiques/ui-components](https://github.com/EchosGraphiques/ui-components).

## Commandes utiles

### Manipulation de médias

*[ImageMagick](https://imagemagick.org/), [cwebp](https://developers.google.com/speed/webp?hl=fr) et [ffmpeg](https://ffmpeg.org/) doivent être installés.*

- Harmoniser des extensions (ex : .JPG => .jpg) \
	`for f in *.JPG; do mv -- "$f" "${f%.JPG}.jpg"; done`

- Redimensionner des images en lot \
	`mogrify -resize 512 *.jpg`

- Convertir des images en WEBP \
	`for f in *.jpg; do cwebp -q 80 "$f" -o "${f%.jpg}.webp"; done`

- Couper une vidéo \
	`ffmpeg -i input_video.mp4 -ss [start_time] -t [duration] output_video.mp4`

- Accélérer/ralentir une vidéo \
	`ffmpeg -i input_video.mp4 -filter:v "setpts=0.5*PTS" output_video.mp4` \
	*Ici, 0.5 signifie que la vitesse de la vidéo est multipliée par 2 ; un nombre supérieur à 1 a pour effet de ralentir la vidéo, avec un risque de saccade.*

### Cartographie

*[MapShaper](https://github.com/mbloch/mapshaper) doit être installé (`npm i -g mapshaper`).*

- Simplifier un fichier GeoJSON \
	`mapshaper input.geojson -simplify 25% -o output.geojson`