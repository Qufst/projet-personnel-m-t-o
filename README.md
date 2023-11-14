# Météo Montpellier

## Objectif:

Le but de ce site est d'afficher la météo à montpellier pour les 5 prochains jours en utilisant les informations du site https://open-meteo.com/en/docs/meteofrance-api.

## Outils et méthodologie:

- Github: la première étape est de créer la base du futur site grâce à github.

- Quarto: L'outils qu'est quarto est très prartique car on peut consigner plusieurs langages de programmations dans le document et avoir un rendu de la forme que l'on souhaite, ici on a privilégié le html. 
En premier lieu il faut importer les données qu'on souhaite utiliser du site météo. Dans ce projet j'ai décié d'importer deux types de données, les données du jour actuelle, notamment la température heure par heure, les précipitations, le vent et autres... Le deuxième type de données concerne le 5 prochains jours car c'est le but de ce projet. De la même façon j'importe différentes données. 
 Je vous invite à regarder mon code pour plus de détails : https://github.com/Qufst/projet-personnel-m-t-o/blob/main/tableaumeteopy.qmd .

 - Json: Dans les données que j'importe, je récupère des codes wmo concernant des images météo. Ainsi j'ai décidé de chercher sur des sites libres de droit des images svg concernant les différents types de météo. Afin de relier les codes wmo aux images que j'ai choisis de leurs associer, j'ai créé le fichier .json suivant : https://github.com/Qufst/projet-personnel-m-t-o/blob/main/dessins_meteo.json .

 - Html: Je souhaitais représenter les différentes données traitées dans le fichier python dans un tableau. Dans le fichier Quarto, à la suite du code python, je crées une cellule html. Je commence la cellule avec la ligne: html_code = f""" <table id="myTable1"> pour commencer ce que je vais écrire dans le tableau et je referme le tableau avec la commande : </table> """ .

 - Css: pour chaque rendu html il est nécessaire de créer un fichier css qui contiendra les finitions voulues de la page html. Il suffit d'ajouter le code suivant afin de relier le fichier css à notre projet quarto:
<head>
    <link rel="stylesheet" href="style.css">
</head> 

- Yml: Le déploiement du site se faite grâce à un fichier .yml.

## Détails

- Dans les données concernant la météo des 5 prochains jours, on se rend compte que le vent moyen n'apparait pas, donc il a fallut récupérer le vent heure par heure et en faire la moyenne.

- Afin de rendre le tableau plus joli j'ai donné des couleurs différentes à plusieurs intervalles de température grâce aux codages RGBA des couleurs. Plus la température est élevée plus la case du tableau sera rouge, et inversément moins la température sera élevée plus la case sera proche du vert foncé.

- De la même façcon j'ai placé un dégradé de couleur pour la vitesse du vent.

## Site Web

Le site web est disponible à l'adresse suivante:
https://qufst.github.io/projet-personnel-mto/