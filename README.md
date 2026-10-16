# Let’s Drive It

Jeu de golf vu du dessus, dans le navigateur, pour joueurs qui connaissent le jeu. Il sert aussi à réviser les règles de golf (carte verte).

## Jouer

Ouvrir la page publiée par GitHub Pages, ou ouvrir `index.html` dans un navigateur récent.

- Formules : trou unique, 3, 9 ou 18 trous, défi du jour.
- Coup : choix du club et de la cible, swing à la souris ou au doigt (barre Espace au clavier), dispersion selon le lie, le vent et la pente.
- Putting avec lecture de pente et vitesse de green (stimp).
- Règles simulées : hors limites, balle perdue, balle provisoire, zones à pénalité jaunes et rouges, balle injouable, obstructions et terrain en réparation, balle enfoncée, score maximum, règle locale E-5 en option.
- Practice : 8 cibles de 50 à 260 m, tapis, fairway, rough ou bunker, vent activable. Tous les clubs se testent.
- Distances affichées = moyenne de vos 3 derniers coups pleins par club, practice compris. Un club jamais mesuré affiche « ? m ».
- Clubs déconseillés signalés et pénalisés (driver en bunker, bois dans le rough…).
- Météo réelle : avec votre accord, le vent et la pluie de votre position (Open-Meteo) s’appliquent au parcours.
- Course de voiturettes : un tour de chemin qui serpente autour de trois trous générés, contre l’IA (3 niveaux). Le rough freine, bunker ou eau = hors course. Flèches ou ZQSD au clavier, boutons à l’écran sur téléphone. Records dans le profil.
- Pétolf : la pétanque au putter sur un fairway, trois balles de golf chacun et un cochonnet, contre l’IA (3 niveaux, parties en 7 ou 13 points). Règles de la pétanque : cochonnet entre 6 et 10 m, le joueur qui ne tient pas le point rejoue, balles et cochonnet morts hors du fairway, points comptés à la fin de chaque mène.
- Sons : impacts selon le club (driver, bois et hybrides, fers, wedges, bunker), balle au trou, plouf, réactions du public, musique au club-house. Coupure dans l’en-tête ou réglage fin dans le menu.
- Quiz de 30 questions sur les règles, y compris celles que le jeu ne simule pas.
- Profil (sac, statistiques, parties) enregistrable en `.json` et réimportable.

## Multijoueur

Voiturettes et Pétolf se jouent aussi en duel en ligne (2 joueurs, chacun sur son écran) : l’un crée un duel et donne le code, l’autre le saisit. Même technique que le salon de golf.


2 à 4 joueurs en stroke play, tour par tour selon la règle 6.4 (honneur, puis le joueur le plus loin du trou).

1. L'hôte ouvre l'onglet Partie et clique sur « Créer un salon ».
2. Les autres saisissent le code du salon sur la même page.
3. L'hôte lance la partie. Il doit garder sa page ouverte : il relaie les échanges.

La connexion utilise WebRTC via [PeerJS](https://peerjs.com/) et son serveur public de mise en relation. Sur certains réseaux d'entreprise ou d'école, la connexion directe peut échouer faute de serveur relais (TURN).

Tous les joueurs doivent utiliser la même version de la page : le parcours est généré à partir d'une graine commune.

## Sons

Fichiers dans `sons/`, fournis comme libres de droits. Musique du club-house : « Whiskey on the Mississippi ». Vérifier la licence exacte de chaque fichier avant toute diffusion commerciale.

## Avertissement

Les fiches de règles et le quiz sont des résumés rédigés pour le jeu, d'après les Règles de golf R&A / USGA (édition 2023). Ils ne remplacent pas le texte officiel diffusé par la ffgolf.

## Technique

Un seul fichier `index.html`, sans étape de construction. Les textures et illustrations sont embarquées. Dépendances chargées depuis un CDN : polices Google Fonts, PeerJS 1.5.4 (seulement en multijoueur). Météo : API publique Open-Meteo, appelée avec une position arrondie à 0,01°.
