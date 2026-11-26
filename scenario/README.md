# Scénario

Cette section présente le scénario de l’interactivité du projet.


<!-- Pour chaque étape/scène : une image avec du texte descriptif et une explication de la transition -->

<!--
Éléments du scénarimage
Séquence visuelle
Chaque scène ou séquence du scénarimage doit être clairement illustrée, montrant les éléments visuels qui seront projetés ou affichés. Cette séquence visuelle peut inclure des captures d'écran, des croquis ou des rendus 3D, en fonction des besoins du projet.

Points d'interaction
Le scénarimage dans un cadre interactif inclut les moments où l'utilisateur interagit avec l'installation. Ces points d’interaction doivent être représentés graphiquement pour indiquer comment et quand l’utilisateur influencera la progression du récit ou des effets visuels et sonores.

Évolution du récit
Comme pour le scénario narratif, le scénarimage doit montrer la progression de l’histoire ou de l’expérience au fil des interactions. Il permet de visualiser comment l’installation évolue en fonction des actions de l'utilisateur, avec des embranchements possibles selon ses choix.

Retour visuel et sensoriel
Le scénarimage doit inclure des annotations ou des visuels montrant les réponses visuelles, sonores ou tactiles à chaque interaction. Cela peut inclure des changements d’éclairage, des transitions vidéo, ou des effets sonores qui réagissent aux actions de l’utilisateur.
-->


## Scène 1 : Lancement

**Ce que l’interacteur voit :**
- L'interacteur sera accueilli par quatre stèles colorées avec 5 boutons sur chacune des stèles. (Bouton sur le dessus ayant des couleurs différentes <span class="rouge">S</span>,<span class="orange">A</span>,<span class="jaune">B</span>,<span class="vert">C</span>,<span class="bleu">D</span>). Chaque stèle comporte aussi trois boutons de navigation (gauche, centre, droite).
- Un projecteur éclaire le mur blanc devant lui et affiche le menu du jeu.
- Avant le lancement, seul le bouton vert est allumé : c'est le seul avec lequel il peut interagir.

**Ce que l’interacteur entend :**
- Une musique entraînante qui attire les passants vers l'installation.

### Tableau des automatisations
| Déclenchement | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- |
| Aucun joueur n'est présent (écran d'attente) | Le menu du jeu est projeté, seul le bouton vert est allumé | Musique entraînante en boucle | Le jeu attend qu'un joueur appuie sur le bouton vert |
| Bouton de lancement | Change de scène vers le choix des catégories | Bruit de lancement | Lance la partie ; les amis peuvent rejoindre le joueur |

### Tableau des actions
| Verbe d’action | Condition / contexte | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- | -- |
| Appuyer | Sur le bouton vert, avant le début de la partie | Transition vers la scène 2 | Bruit de lancement | Démarre la partie |


## Scène 2 : Gameplay

### Choix des catégories

**Ce que l’interacteur voit :**
- Une série de catégories à l'écran (À confirmer : liste des catégories)
- La catégorie actuellement sélectionnée est mise en évidence

**Ce que l’interacteur entend :**
- Une musique entraînante
- Un son de défilement et un son de confirmation du choix

#### Tableau des automatisations
| Déclenchement | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- |
| Catégorie confirmée | Transition vers l'écran de vote avec la première image | Bruit de confirmation | Lance la première manche de vote |

#### Tableau des actions
| Verbe d’action | Condition / contexte | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- | -- |
| Appuyer sur le bouton gauche | Pendant le choix des catégories | Défile vers la catégorie précédente | Son de défilement | Change la catégorie sélectionnée |
| Appuyer sur le bouton droit | Pendant le choix des catégories | Défile vers la catégorie suivante | Son de défilement | Change la catégorie sélectionnée |
| Appuyer sur le bouton central | Une catégorie est sélectionnée | La catégorie est confirmée | Bruit de confirmation | Valide le choix collectif et passe à la phase de vote |

### Vote sur l'image

**Ce que l’interacteur voit :**
- Un tableau avec 5 lignes (<span class="rouge">S</span>,<span class="orange">A</span>,<span class="jaune">B</span>,<span class="vert">C</span>,<span class="bleu">D</span>)
- Une image à catégoriser
- Un timer pour déterminer le temps restant sur la manche de vote
- Les quatre stèles représentées à l'écran, chacune aux couleurs des boutons de la stèle physique du joueur
- Le nombre de vies restantes (3 au départ)

**Ce que l’interacteur entend :**
- Une musique entraînante
- Le son de choix de classe lorsque le vote est enregistré

#### Tableau des automatisations
| Déclenchement | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- |
| Début de la manche | Une image apparaît et le timer démarre | Son de début de manche (À confirmer) | Les votes sont ouverts |
| Un joueur vote | Sa stèle à l'écran passe au vert avec un crochet vert ; le bouton appuyé est le seul qui reste allumé sur sa stèle | Bruit de choix de classe | Son vote est enregistré |
| Un joueur ne vote pas avant la fin du temps | Sa stèle à l'écran devient rouge avec une croix rouge | Son d'erreur (À confirmer) | Aucun vote n'est enregistré pour ce joueur |
| Fin du temps et votes enregistrés | Les notes de chaque joueur sont affichées à l'écran | Son de révélation (À confirmer) | Le jeu analyse les votes |

#### Tableau des actions
| Verbe d’action | Condition / contexte | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- | -- |
| Appuyer sur un bouton de classe (<span class="rouge">S</span>,<span class="orange">A</span>,<span class="jaune">B</span>,<span class="vert">C</span>,<span class="bleu">D</span>) | Pendant le temps de vote | Le bouton appuyé reste seul allumé ; la stèle du joueur passe au vert à l'écran | Bruit de choix de classe | Enregistre le vote du joueur |

### Validation du classement

**Ce que l’interacteur voit :**
- Les votes de chaque joueur affichés à l'écran
- Selon le résultat : l'image qui se place dans la bonne ligne du tableau, ou l'image qui disparaît et une vie qui se perd

**Ce que l’interacteur entend :**
- Un son de validation si l'image est classée
- Un son d'échec si une vie est perdue

#### Tableau des automatisations
| Déclenchement | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- |
| Une majorité de joueurs donne la même réponse | L'image est intégrée à la tier list, dans la ligne de la couleur choisie | Son de validation (À confirmer) | Passage à l'image suivante |
| Tous les joueurs donnent une réponse différente | L'image est supprimée et une vie est retirée (3 au total) | Son d'échec (À confirmer) | Passage à l'image suivante |
| Égalité des votes | L'écran devient plus rouge, les animations s'accélèrent, un chronomètre de 15 secondes apparaît | La musique devient plus stressante | Les joueurs peuvent changer leur vote pour trouver un accord |
| Accord trouvé pendant les 15 secondes | L'image est intégrée à la tier list ; retour à l'ambiance normale | Son de validation (À confirmer) | Passage à l'image suivante |
| Fin des 15 secondes sans accord | L'image est supprimée et une vie est retirée | Son d'échec (À confirmer) | Passage à l'image suivante |
| Les 3 vies sont épuisées | Transition vers la scène finale | Son de fin de partie (À confirmer) | La tier list est enregistrée définitivement |

#### Tableau des actions
| Verbe d’action | Condition / contexte | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- | -- |
| Appuyer sur un bouton de classe | Pendant le chronomètre de 15 secondes (égalité) | Le bouton appuyé reste allumé, la stèle à l'écran est mise à jour | Bruit de choix de classe | Modifie le vote du joueur |


## Scène 3 : Final

**Ce que l’interacteur voit :**
- Ils voient la tier list avec toutes les images qu'ils ont classées
- Un bouton pour lancer une nouvelle partie

**Ce que l’interacteur entend :**
- Une musique entraînante
- Un effet sonore lorsque le joueur principal lance une nouvelle partie

### Tableau des automatisations
| Déclenchement | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- |
| Début de la scène finale | La tier list finale est affichée, le bouton vert s'allume | Musique entraînante | La tier list est enregistrée |
| Bouton de nouvelle partie | Retour au menu (À confirmer : ou directement au choix des catégories) | Bruit de lancement | Réinitialise les vies et la tier list |

### Tableau des actions
| Verbe d’action | Condition / contexte | Effet visuel | Effet sonore | Effet interactif |
| -- | -- | -- | -- | -- |
| Appuyer | Sur le bouton vert, à la fin de la partie | Transition vers une nouvelle partie | Bruit de lancement | Relance une partie |