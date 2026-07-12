---
name: em-stop-slop
description: "Retire les tics d'écriture IA d'un texte français. À utiliser lors de la rédaction, l'édition ou la relecture de prose (pages, articles, posts, emails, livrables) pour éliminer les formules prévisibles avant livraison. Complément de polissage des skills de rédaction (em-seo-page, social-week, docx-builder)."
metadata:
  trigger: "Rédaction ou relecture de prose française, polissage de copy avant publication"
  author_original: "Hardik Pandya (https://hvpandya.com)"
  adaptation: "E-Motion / So'6 Rallye — adaptation française"
  upstream: "https://github.com/So6Rallye/stop-slop (fork de hardikpandya/stop-slop)"
  license: MIT
---

# em-stop-slop

Élimine les tics d'écriture IA d'un texte français. Adaptation française de `stop-slop` (Hardik Pandya, MIT). Voir la section Licence.

## Quand l'utiliser

Après avoir rédigé ou avant de livrer un texte destiné à un lecteur humain : page web, article, post social, email, livrable client. S'applique au **corps de la prose**, en dernière passe, une fois le contenu et sa structure fixés.

## Périmètre et garde-fous (à lire en premier)

Ce skill polit la prose. Il ne touche **jamais** :

- **Les titres H2/H3 formulés en question** (« Comment surveiller les prix concurrents ? », « Pourquoi... ? »). C'est une exigence SEO/GEO pour matcher les requêtes réelles. La règle anti-début-en-mot-interrogatif ne s'applique **pas** aux titres.
- **Le mot-clé SEO cible** : ne pas supprimer les occurrences nécessaires à la densité (1-2 %). Couper les répétitions superflues, garder le mot-clé.
- **Les sources, liens et statistiques sourcées** : jamais retirés ni affaiblis.
- **Les blocs techniques** : JSON-LD, code, mentions légales, citations littérales, noms propres, marques.

**Ordre dans un pipeline SEO** : générer le contenu SEO/GEO d'abord, polir avec ce skill ensuite, en préservant les contraintes ci-dessus. Le ton affirmatif GEO (« 0 peut-être/il semblerait ») et l'interdiction du tiret cadratin (`audit:tirets` Rivalyse) **convergent** avec ce skill et se renforcent.

## Principes (8)

1. **Couper le remplissage.** Supprimer les ouvertures de raclement de gorge, les béquilles d'emphase et les adverbes vides. Voir `references/phrases-fr.md`.
2. **Casser les structures formulaiques.** Éviter les contrastes binaires, le listing négatif, la fragmentation dramatique, les mises en place rhétoriques, la fausse agentivité. Voir `references/structures-fr.md`.
3. **Voix active.** Chaque phrase a un sujet humain qui agit. Pas de passive. Pas d'objet inanimé qui accomplit une action humaine (« la décision émerge »).
4. **Être précis.** Pas de déclarative vague (« les raisons sont structurelles »). Nommer la chose précise. Pas d'extrêmes paresseux (« tout », « toujours », « jamais ») qui font un travail vague.
5. **Mettre le lecteur dans la pièce.** Pas de voix de narrateur distant. « Vous » vaut mieux que « les gens ». Le concret bat l'abstrait.
6. **Varier le rythme.** Mélanger les longueurs de phrase. Deux items valent mieux que trois. Finir les paragraphes différemment. Aucun tiret cadratin.
7. **Faire confiance au lecteur.** Énoncer les faits directement. Couper les adoucissements, justifications et prises par la main.
8. **Couper les phrases à citer.** Si une ligne sonne comme une punchline à encadrer, la réécrire simplement.

## Vérifications rapides

Avant de livrer :

- Des adverbes vides ? Les supprimer.
- De la voix passive ? Trouver l'acteur, le mettre sujet.
- Un objet inanimé qui fait une action humaine (« la décision émerge ») ? Nommer la personne.
- Dans le **corps** (pas les titres), une phrase en fausse question interrogative ? Restructurer.
- Un raclement de gorge (« Voici ce qu'il faut... », « Ce qu'il faut retenir... ») ? Aller au fait.
- Un contraste « non pas X, mais Y » ? Énoncer Y directement.
- Trois phrases de suite de même longueur ? En casser une.
- Un paragraphe qui finit sur une punchline ? Varier.
- Un tiret cadratin quelque part ? Le retirer (virgule ou deux-points).
- Une déclarative vague (« les enjeux sont importants ») ? Nommer l'enjeu précis.
- Un narrateur distant (« personne n'a conçu cela ») ? Mettre le lecteur dans la scène.
- Un méta-commentaire (« dans cet article, nous allons... ») ? Supprimer.

## Score (5 dimensions)

Noter chaque dimension de 1 à 10 :

| Dimension | Question |
|-----------|----------|
| Franchise | Des affirmations, ou des annonces ? |
| Rythme | Varié, ou métronomique ? |
| Confiance | Respecte l'intelligence du lecteur ? |
| Authenticité | Sonne humain ? |
| Densité | Reste-t-il quelque chose à couper ? |

Sous **35/50** : réviser. Ce score est un indicateur, pas un couperet automatique : ne jamais sacrifier une contrainte SEO/GEO (mot-clé, source, titre-question) pour gagner un point.

## Références

- `references/phrases-fr.md` — mots et formules à supprimer
- `references/structures-fr.md` — structures à éviter
- `references/examples-fr.md` — transformations avant / après

## Licence

MIT. Adaptation française du projet `stop-slop` de Hardik Pandya (https://hvpandya.com).
Copyright (c) 2025 Hardik Pandya. Le texte complet de la licence est dans `LICENSE`.
Fork : https://github.com/So6Rallye/stop-slop.
