# Let’s Drive It

Jeu de golf vu du dessus, dans le navigateur, pour joueurs qui connaissent le jeu. Il sert aussi à réviser les règles de golf (carte verte).

## Jouer

Ouvrir la page publiée par GitHub Pages, ou ouvrir `index.html` dans un navigateur récent.

- Formules : trou unique, 3, 9 ou 18 trous, défi du jour.
- Coup : choix du club et de la cible, swing à la souris ou au doigt (barre Espace au clavier), dispersion selon le lie, le vent et la pente.
- Putting avec lecture de pente et vitesse de green (stimp).
- Règles simulées : hors limites, balle perdue, balle provisoire, zones à pénalité jaunes et rouges, balle injouable, obstructions et terrain en réparation, balle enfoncée, score maximum, règle locale E-5 en option.
- Distances affichées = moyenne de vos 3 derniers coups pleins par club (estimation prudente tant qu’un club n’est pas mesuré).
- Clubs déconseillés signalés et pénalisés (driver en bunker, bois dans le rough…).
- Météo réelle : avec votre accord, le vent et la pluie de votre position (Open-Meteo) s’appliquent au parcours.
- Quiz de 30 questions sur les règles, y compris celles que le jeu ne simule pas.
- Profil (sac, statistiques, parties) enregistrable en `.json` et réimportable.

## Multijoueur

2 à 4 joueurs en stroke play, tour par tour selon la règle 6.4 (honneur, puis le joueur le plus loin du trou).

1. L'hôte ouvre l'onglet Partie et clique sur « Créer un salon ».
2. Les autres saisissent le code du salon sur la même page.
3. L'hôte lance la partie. Il doit garder sa page ouverte : il relaie les échanges.

La connexion utilise WebRTC via [PeerJS](https://peerjs.com/) et son serveur public de mise en relation. Sur certains réseaux d'entreprise ou d'école, la connexion directe peut échouer faute de serveur relais (TURN).

Tous les joueurs doivent utiliser la même version de la page : le parcours est généré à partir d'une graine commune.

## Avertissement

Les fiches de règles et le quiz sont des résumés rédigés pour le jeu, d'après les Règles de golf R&A / USGA (édition 2023). Ils ne remplacent pas le texte officiel diffusé par la ffgolf.

## Technique

Un seul fichier `index.html`, sans étape de construction. Les textures et illustrations sont embarquées. Dépendances chargées depuis un CDN : polices Google Fonts, PeerJS 1.5.4 (seulement en multijoueur). Météo : API publique Open-Meteo, appelée avec une position arrondie à 0,01°.
