# Sources des deux slides sur l'IA

Document de travail, pas destiné à être projeté. Il donne, pour chaque
affirmation des slides « Développement logiciel : de la complétion à l'agent »
et « Mathématiques : conjecture automatique, preuve vérifiée », le chiffre exact
et le lien permettant de le vérifier.

Consulté le 9 septembre 2026.

## Slide 1 : développement logiciel

### Le banc de mesure

- **SWE-bench** (oct. 2023) : 2 294 tickets GitHub réels tirés de 12 dépôts
  Python. Le meilleur système de l'article, Claude 2, résout **1,96 %** des
  tickets.
  <https://arxiv.org/abs/2310.06770>
- **SWE-bench Verified** (août 2024) : sous-ensemble de **500 tickets** relus à
  la main. 93 développeurs Python ont trié les instances ; **68,3 %** des
  échantillons d'origine ont été écartés comme non exploitables. GPT-4o y
  obtient **33,2 %**, contre 16 % sur le SWE-bench d'origine.
  <https://openai.com/index/introducing-swe-bench-verified/>
  <https://www.swebench.com/verified.html>

### Les mesures, retirées du slide mais conservées ici

Le slide ne porte plus aucun pourcentage : il ne reste que les jauges, et la
hauteur des marches suit linéairement la part déléguée qu'elles affichent. Le
tableau ci-dessous garde les mesures publiées, à sortir seulement si la question
est posée.

| Marche | Valeur exacte | Système, date | Source |
|---|---|---|---|
| 2023 : « 2 % » | 1,96 % (SWE-bench, 2 294 tickets) | Claude 2, oct. 2023 | <https://arxiv.org/abs/2310.06770> |
| 2024 : « 49 % » | 49,0 % (SWE-bench Verified) | Claude 3.5 Sonnet, oct. 2024 | <https://www.anthropic.com/research/swe-bench-sonnet> |
| 2025 : « 81 % » | 80,9 % | Claude Opus 4.5, 24 nov. 2025 | <https://www.anthropic.com/claude-opus-4-5-system-card> |
| 2026 : « 96 % » | 96,0 % | Claude Opus 5, juill. 2026 | <https://leaderboard.steel.dev/leaderboards/swe-bench-verified/> |

Le chiffre 2026 vient d'un classement agrégé, pas d'une publication primaire :
c'est le point le plus faible de la série. Le même classement donne 97,0 %
pour une reprise Vals.ai en septembre 2026.

Point de comparaison entre 2024 et 2025 si la question vient : GPT-5.1-Codex-Max
77,9 %, Claude Sonnet 4.5 77,2 %, Gemini 3 Pro 76,2 % (nov. 2025).

### « 1 correctif sur 5 accepté à tort »

- **SWE-ABS** (arXiv, 28 févr. 2026) : en renforçant les jeux de tests de façon
  adversariale, **19,71 %** des correctifs qui passaient sont rejetés. Un
  correctif « résolu » sur cinq parmi les 30 meilleurs agents est
  sémantiquement faux. Le meilleur score du classement passe de **78,80 % à
  62,20 %**.
  <https://arxiv.org/abs/2603.00520> (PDF : <https://arxiv.org/pdf/2603.00520>)

C'est l'argument à sortir si quelqu'un objecte que les scores sont trop beaux.
À noter aussi : OpenAI a cessé de publier ses scores sur Verified début 2026 et
renvoie vers SWE-bench Pro, la version Verified étant jugée saturée.

### Ce qui n'est pas sourcé

Le slide de gauche est désormais **entièrement qualitatif**. La jauge
« conduite par le développeur / conduite par la machine », les « niveaux 0 à 4 »
et la hauteur des marches sont une lecture personnelle, pas une mesure. De même,
« agents concurrents sur un même dépôt » décrit une pratique, sans chiffre
d'adoption à l'appui.

C'est un choix assumé : les mesures existent (tableau ci-dessus) mais les
afficher rendait le slide illisible, et le repère 2026 reposait sur un classement
agrégé plutôt que sur une publication primaire.

## Slide 2 : mathématiques et preuve formelle

### Piste « Production » (modèles de langage)

- **2022, réponses sans démonstration.** Minerva (Google, juin 2022) résout
  environ **50 %** du jeu MATH, contre environ 7 % pour l'état de l'art
  précédent. Ce sont des réponses numériques courtes, sans démonstration ni
  vérification.
  <https://arxiv.org/abs/2206.14858>
- **2024, argent à l'Olympiade.** AlphaProof et AlphaGeometry 2 totalisent
  **28 points sur 42** à l'OIM 2024, soit **4 problèmes sur 6** (P1, P2, P6 pour
  AlphaProof, P4 pour AlphaGeometry 2), à un point du seuil de la médaille d'or.
  Les énoncés ont été **traduits en Lean par des experts** : c'est la limite de
  ce résultat.
  <https://deepmind.google/blog/ai-solves-imo-problems-at-silver-medal-level/>
  Article de référence : *Olympiad-level formal mathematical reasoning with
  reinforcement learning*, Nature, 2025.
  <https://www.nature.com/articles/s41586-025-09833-y>
- **2025, or à l'Olympiade.** Gemini Deep Think obtient **35 points sur 42**,
  soit **5 problèmes sur 6**, **de bout en bout en langage naturel** à partir
  des énoncés officiels, dans les **4 h 30** du concours. Copies corrigées et
  certifiées par les organisateurs de l'OIM. Annonce du 21 juillet 2025.
  <https://deepmind.google/blog/advanced-version-of-gemini-with-deep-think-officially-achieves-gold-medal-standard-at-the-international-mathematical-olympiad/>
- **2026, problèmes de recherche.** FrontierMath Open Problems (Epoch AI,
  lancé le 31 juillet 2026) : **50 problèmes de recherche non résolus**, dont
  **3** traités à ce jour.
  <https://epoch.ai/frontiermath>

Pour situer la difficulté : à la sortie de FrontierMath (2024), l'état de l'art
était sous **2 %** sur l'ensemble ; GPT-5 atteint environ **25 %** en 2025. Une
correction de juin 2026 a touché **42 %** des problèmes, et les modèles évalués
sur les deux versions marquent environ **12 points** de plus sur la version
corrigée : les comparaisons avant/après cette date sont à manier avec
précaution.
<https://epoch.ai/benchmarks>

### Piste « Vérification » (assistants de preuve)

- **2022, Liquid Tensor Experiment.** Défi posé par Peter Scholze en décembre
  2020, clos le **14 juillet 2022** : le théorème principal des espaces
  vectoriels liquides de Clausen et Scholze est formellement vérifié en Lean.
  Projet mené par Johan Commelin, avec Adam Topaz et d'autres, et le soutien
  mathématique de Scholze.
  <https://leanprover-community.github.io/blog/posts/lte-final/>
- **2024, AlphaProof écrit du Lean.** AlphaProof est un agent d'apprentissage
  par renforcement qui démontre dans l'environnement formel de Lean : un modèle
  propose l'étape suivante, Lean la vérifie. La sortie est un terme de preuve,
  pas un texte à relire.
  <https://www.nature.com/articles/s41586-025-09833-y>
- **2025, mathlib.** Bibliothèque commune de Lean 4. Statistiques officielles au
  moment de la rédaction : **287 620 théorèmes**, **136 798 définitions**,
  **772 contributeurs**. La barre des **2 millions de lignes** est franchie
  courant 2025. Recompilation en intégration continue à chaque contribution.
  <https://leanprover-community.github.io/mathlib_stats.html>
  <https://lean-lang.org/use-cases/mathlib/>
  <https://github.com/leanprover-community/mathlib4>
- **2026, preuve formelle exigée.** FrontierMath Erdős : **68 problèmes**
  posés ou étudiés par Erdős (65 énoncés distincts), **tous ouverts en août
  2026**, formulés en Lean. Le système doit produire une **preuve ou une
  réfutation complète**, validée par Comparator, qui vérifie que la preuve
  démontre bien l'énoncé exact avec les seuls axiomes autorisés.
  <https://epoch.ai/benchmarks/frontiermath-erdos>
  <https://epoch.ai/latest/announcing-frontiermath-erdos>
  <https://epoch.ai/files/frontiermath-erdos.pdf>

  **Le score de ce banc de mesure ne doit pas être cité.** Il figurait dans une
  version précédente du slide sous la forme « 3 % » ; il en a été retiré. Les
  raisons, si la question vient :

  - Le banc a été **annoncé le 1er septembre 2026**, huit jours avant la
    rédaction de ces notes.
  - Cinq systèmes évalués (GPT-6 Astra, GPT-5.6 Sol, GPT-5.5, Claude Fable 5.1,
    Claude Fable 5), **une seule tentative** par problème, sous plafond de
    **300 $ et 72 h**. Seul GPT-6 Astra marque, les quatre autres sont à zéro.
  - Les « 3 % » correspondent à **2 problèmes résolus sur 68** (les problèmes 74
    et 126). Sur un tel effectif, l'intervalle de confiance à 95 % (Wilson) va
    de **0,8 % à 10,1 %** : un facteur douze. Le chiffre ne distingue rien.
  - Le résultat dépend directement du budget : **hors protocole, avec un budget
    élargi, le même modèle résout 5 problèmes**, soit 7,4 %. Desserrer le
    plafond multiplie par 2,5 le nombre de problèmes résolus.
  - Epoch AI met elle-même en garde : la formalisation ajoute une charge propre,
    la contamination par les solutions publiées va croître avec le temps, et
    « les problèmes d'Erdős, ce n'est pas toute la mathématique ».
  - Enfin, les énoncés ont été retenus **parce qu'ils sont ouverts**. Un score
    bas est une propriété de la construction du banc, pas la mesure d'un
    plafond de capacité.

  Ce qui reste dicible : sur des énoncés réellement ouverts et formalisés, les
  systèmes actuels ne produisent presque rien. C'est une observation
  qualitative, à ne pas chiffrer.

  Repère indépendant plus solide, donné par le curateur du banc : avant celui-ci,
  seuls **3 à 5** problèmes d'Erdős de ce calibre avaient été résolus avec l'aide
  d'une IA.

### Ce qui porte l'idée que la preuve formelle reste le point dur

Trois éléments, indépendants du banc Erdős :

- En 2024, les énoncés de l'OIM ont dû être **traduits en Lean par des experts**
  avant qu'AlphaProof puisse travailler.
  <https://deepmind.google/blog/ai-solves-imo-problems-at-silver-medal-level/>
- En 2025, la médaille d'or a été obtenue **en langage naturel**, pas par la voie
  formelle : le meilleur résultat olympique vient précisément de l'abandon de la
  formalisation.
  <https://deepmind.google/blog/advanced-version-of-gemini-with-deep-think-officially-achieves-gold-medal-standard-at-the-international-mathematical-olympiad/>
- Epoch AI écrit que « la formalisation ajoute une charge supplémentaire pour les
  systèmes d'IA », au-delà de la résolution du problème mathématique.
  <https://epoch.ai/latest/announcing-frontiermath-erdos>

### Le noyau de Lean

Argument à garder en réserve : la confiance ne repose pas sur le modèle ni sur
son automatisation, mais sur un noyau de vérification réduit. Leo de Moura
(architecte en chef de la Lean FRO), Paris Lean Meetup du 23 avril 2026 :
Lean a « plusieurs noyaux indépendants », les preuves « peuvent être exportées
et vérifiées indépendamment », et « vous n'avez besoin de faire confiance qu'au
petit noyau ». Des réimplémentations existent en Rust et en Lean lui-même, ce
qui permet de les recouper.
<https://leodemoura.github.io/static/paris2026/>
<https://arena.lean-lang.org>

Une valeur de taille de noyau circule (de l'ordre de 6 000 lignes de C++, plus
700 pour les familles inductives) mais je ne l'ai pas confirmée sur une source
primaire : à ne pas citer telle quelle.
