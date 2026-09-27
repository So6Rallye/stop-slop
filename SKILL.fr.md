---
name: em-stop-slop
description: "Retire les tics d'écriture IA d'un texte français. À utiliser lors de la rédaction, l'édition ou la relecture de prose (pages, articles, posts, emails, livrables), quand un texte « sonne IA », robotique ou générique, ou avant toute livraison à un lecteur humain. Complément de polissage des skills de rédaction (em-seo-page, social-week, docx-builder)."
metadata:
  trigger: "Rédaction ou relecture de prose française, polissage de copy avant publication"
  author_original: "Hardik Pandya (https://hvpandya.com)"
  adaptation: "E-Motion / So'6 Rallye, adaptation française, refonte 2026-09-27 (Wikipedia Signs of AI writing + étude Rigouts Terryn & de Lhoneux 2024)"
  upstream: "https://github.com/So6Rallye/stop-slop (fork de hardikpandya/stop-slop)"
  license: MIT
---

# em-stop-slop

Élimine les tics d'écriture IA d'un texte français, en dernière passe, une fois le fond et la structure fixés.

## Le vrai problème

Un modèle de langue tend vers la formulation la plus probable. Il remplace le détail précis et rare par une formule générique et flatteuse : « inventeur du premier attelage ferroviaire » devient « titan révolutionnaire de l'industrie ». Le texte devient à la fois plus flou et plus emphatique.

Les tics listés dans les références sont des **symptômes**. Remplacer un mot signalé par un synonyme, ou un tiret cadratin par un autre tiret, cache le symptôme et garde le problème. Corriger une phrase, c'est corriger ce qu'elle fait (gonfler, attribuer dans le vide, contredire une idée que personne n'a eue), puis dire la chose précise, simplement.

Le but est un texte juste et précis, pas un texte qui trompe un détecteur.

## Garde-fous (priment sur tout le reste)

**Ne jamais inventer.** Retirer de l'emphase ne donne pas le droit d'ajouter un fait, un chiffre, une fréquence, une date ou une fonctionnalité absents du texte d'origine. Si la phrase précise demande un fait qu'on n'a pas : écrire la version sobre sans ce fait, et lister le fait manquant dans le compte rendu (« à demander : … »).

**Édition minimale.** Couper le tic et garder le reste de la phrase mot pour mot. Réécrire seulement si la phrase ne tient plus debout une fois le tic retiré. Ne jamais fusionner deux phrases qui portent chacune un fait (date, chiffre, cause, condition) : chacune garde sa phrase. Ne pas ajouter de qualificatif absent de l'original (« automatiquement », « toujours », « rapidement ») : c'est un fait de plus.

**Garder tout le fond.** Chaque fait, chiffre, nom, date, lien et affirmation reste. Les nuances de quantité aussi : « la plupart des clients » ne devient pas « les clients ». Une phrase de pur remplissage se supprime ; une phrase qui portait un fait garde le fait.

**Ne jamais toucher :** citations d'une personne ou d'une source, titres d'œuvres, textes juridiques et mentions légales, code, JSON-LD, noms propres et marques.

**Garder la voix de l'auteur :** la personne grammaticale (je, nous, vous : ne pas passer de l'un à l'autre), le registre, le format (Markdown, HTML, JSX, texte brut) et les limites de longueur (title ~60 caractères, meta description ~155, libellés de bouton).

**Contraintes SEO/GEO :**

- Un titre H2/H3 formulé en question (« Comment surveiller les prix concurrents ? ») reste une question : il répond à une requête réelle.
- Le mot-clé cible garde ses occurrences nécessaires (densité 1-2 %). Couper les répétitions superflues seulement.
- Une phrase visible reprise dans le JSON-LD (réponse FAQPage, description) doit rester identique à sa copie : Google demande que le balisage corresponde au texte affiché. Si on la réécrit, reporter la même phrase dans le JSON-LD et le signaler dans le compte rendu (« JSON-LD synchronisé : … ») ; si on ne peut pas toucher au JSON-LD, laisser la phrase visible telle quelle.
- Une source, un lien ou une statistique sourcée n'est jamais retiré ni affaibli. Si le texte attribue une analyse à une source nommée (« selon X, … »), vérifier que la source le dit vraiment ; sinon retirer l'attribution ou signaler le doute.
- Le ton affirmatif GEO (zéro « peut-être / il semblerait ») est un choix de style GEO, pas une règle anti-IA : il s'applique aux pages SEO, pas aux emails ni aux livrables.

**Information manquante :** si le texte dit qu'une chose est inconnue, garder cette honnêteté. La dire une fois, concrètement, avec ce que le lecteur doit faire (« Les tarifs Entreprise ne sont pas encore publiés : demandez un devis. »). Supprimer toute supposition sur ce que l'information « serait probablement ».

## Ce qui n'est pas un tic (ne pas corriger)

Ces tournures sont plus fréquentes chez les humains que chez l'IA, ou ne prouvent rien. Les laisser :

- les phrases simples en « est », « a », « il y a » ;
- les mots simples (utiliser, écrire, essayer, avant) ;
- les affirmations nettes et vraies : « le seul », « le premier », « l'un des meilleurs » ;
- les nuances et intensifs ordinaires : « très », « peut-être », « souvent », « a tendance à », « la plupart » ;
- l'incertitude réelle de l'auteur : date prévisionnelle, estimation, diagnostic prudent. On peut retirer un doublon (« devrait probablement » devient « devrait »), jamais la changer en certitude (« aura lieu ») ;
- une tournure un peu lourde isolée : « afin de », « le fait que », « à la suite de » ;
- un connecteur isolé au milieu d'une phrase (« cependant », « ainsi ») ;
- une grammaire parfaite, un registre soutenu, un mélange de registres, une affirmation sans source.

Une phrase propre reste telle quelle. Un seul signe isolé ne prouve rien : c'est l'accumulation qui trahit l'IA.

## Déroulé

1. **Lire les références** avant la première réécriture de la session.
2. **Repérer.** Passer le texte au crible des cinq références, phrase par phrase. Noter chaque signe trouvé et sa catégorie.
3. **Réécrire** chaque phrase signalée en respectant les garde-fous. Puis relire le texte entier pour les signes de jugement (règle de trois, rythme, fin en résumé, importance gonflée).
4. **Relire contre l'original** : même faits, mêmes chiffres, mêmes nuances, même personne grammaticale, rien d'ajouté. Après chaque phrase corrigée, relire son paragraphe entier : un connecteur (« en revanche », « ces deux », « autre chose ») peut avoir perdu son référent. Chercher le caractère « — » par une recherche dans le texte, pas à l'œil. Repasser le crible : viser zéro signe, hors ceux gardés exprès.
5. **Rendre compte** dans ce format, dans cet ordre :
   - le texte réécrit (ou la confirmation que les fichiers sont modifiés) ;
   - « Signes : N avant, M après », avec le détail par catégorie ;
   - **Contrôle de sens** (obligatoire) : un tableau à trois colonnes, une ligne par phrase porteuse d'un fait (date, chiffre, cause, condition, promesse) qui a été modifiée : phrase d'origine | phrase réécrite | même affirmation (oui / non). Toute ligne « non » se corrige avant de livrer. Si aucune phrase porteuse d'un fait n'a été modifiée, écrire « Contrôle de sens : aucune phrase factuelle modifiée » ;
   - 2 ou 3 exemples avant/après représentatifs ;
   - « Gardé exprès : … » (citations, noms propres, mot-clé SEO, mot employé au sens propre) ;
   - « À demander : … » pour chaque fait qui manquait (omettre la ligne si rien ne manque).

   Le compte rendu est lu par un humain : il suit les mêmes règles que le texte (zéro tiret cadratin, pas de formule de chat).

## Priorités

Chaque règle des références porte un niveau de preuve :

- **[établi]** : documenté par Wikipedia *Signs of AI writing* (anglais, 2026) ou par l'étude annotée sur le français (Rigouts Terryn & de Lhoneux, 2024) ;
- **[probable]** : observé par plusieurs sources francophones sans étude derrière ;
- **[maison]** : choix de style E-Motion, sans preuve qu'il s'agisse d'un tic IA.

Les textes relus ici sont surtout écrits par Claude. Son tic le plus documenté est le **tiret cadratin** : c'est le seul modèle actuel qui en met plus que les rédacteurs professionnels. Zéro tiret cadratin, et pas de remplacement par « - » ou « – » : réécrire la phrase (virgule, deux-points, point-virgule, parenthèses, point ; « · » dans une interface).

## Vérifications rapides

- Un fait, un chiffre ou une fréquence absent de l'original ? Le retirer.
- Une nuance (« la plupart », « souvent », « encore ») effacée ? La remettre.
- Un « devrait », « probablement », « prévu sous réserve » devenu une certitude ? Le remettre.
- Une citation modifiée ? La restaurer.
- Un tiret cadratin, ou un « - » qui le remplace ? Réécrire la phrase.
- Une queue en participe (« …, témoignant de / renforçant / garantissant ») ? La couper.
- « se positionne comme », « s'impose comme », « dispose de » ? Mettre « est » ou « a » si la phrase porte un fait ; la supprimer si elle n'était que de l'emphase.
- « Non seulement… mais aussi », « pas X, mais Y » ? Énoncer Y seul.
- « selon les experts », « de nombreux médias » sans nom ? Nommer ou couper.
- Une supposition sur une information manquante ? La couper, dire l'inconnu une fois.
- Une fin en « En somme », « En conclusion » ? Finir sur le dernier fait nouveau.
- « N'hésitez pas à », « J'espère que » ? Supprimer ou dire l'action directement.
- Des puces à étiquette en gras suivie de deux-points, des majuscules à chaque mot d'un titre ? Voir `formatting-fr.md`.
- Trois phrases de suite de même longueur, une punchline en fin de paragraphe ? Varier.

## Score (5 dimensions)

Noter chaque dimension de 1 à 10 :

| Dimension | Question |
|-----------|----------|
| Franchise | Des affirmations, ou des annonces ? |
| Rythme | Varié, ou métronomique ? |
| Confiance | Respecte l'intelligence du lecteur ? |
| Précision | Des faits précis, ou des formules génériques ? |
| Densité | Reste-t-il quelque chose à couper ? |

Sous **35/50** : réviser. Le score est un indicateur, pas un couperet : ne jamais sacrifier un garde-fou pour gagner un point.

## Références

- `references/signes-fr.md` : signes de contenu et restes de conversation (importance gonflée, attributions floues, suppositions)
- `references/phrases-fr.md` : mots et formules
- `references/structures-fr.md` : constructions de phrase
- `references/formatting-fr.md` : mise en forme, titres, typographie
- `references/examples-fr.md` : transformations avant / après
- `references/sources-fr.md` : sources et niveaux de preuve

## Licence

MIT. Adaptation française du projet `stop-slop` de Hardik Pandya (https://hvpandya.com).
Copyright (c) 2025 Hardik Pandya. Le texte complet de la licence est dans `LICENSE`.
Fork : https://github.com/So6Rallye/stop-slop.
