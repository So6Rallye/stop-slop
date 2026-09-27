# Sources et niveaux de preuve

Chaque règle du skill porte un niveau de preuve. Il dit ce qui est démontré et ce qui relève de nos préférences.

## [établi]

**Wikipedia, *Signs of AI writing*** (WikiProject AI Cleanup), révision du 26 septembre 2026.
https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing

Guide de terrain tiré de vrais articles Wikipedia, avec études citées. Limites : porte sur l'**anglais** et sur des textes **encyclopédiques**. Il se veut descriptif (des observations, pas des règles) et précise qu'un mot surutilisé par l'IA ne rend pas suspects ses synonymes. Nos équivalents français de ses listes de mots sont donc des pistes.

Points repris : la perte de précision comme cause de fond ; les signes de contenu, de langue, de mise en forme et de conversation ; les signes d'écriture humaine ; les faux indices ; le tiret cadratin comme tic propre à Claude (étude de juillet 2026) ; le classement par époque des modèles.

**Rigouts Terryn, A. & de Lhoneux, M. (2024).** *Exploratory Study on the Impact of English Bias of Generative Large Language Models in Dutch and French.* HumEval @ LREC-COLING 2024, p. 12-27.
https://aclanthology.org/2024.humeval-1.2/

Seule étude annotée trouvée sur le français. Articles de presse générés par GPT-4 (et deux autres modèles), annotés par des traducteurs professionnels. Limites : exploratoire, petit corpus, un seul genre (presse), modèles de 2024.

Points repris : 16 % des anomalies viennent clairement de l'anglais (calques) ; connecteurs entre parties « trop évidents, peu naturels » (en somme, en conclusion, en conséquence) ; adjectifs dramatiques pour une situation banale ; incohérences dans un même texte (guillemets « » et " " mélangés, deux orthographes d'un mot).

## [probable]

Sources francophones sans étude derrière, convergentes entre elles :

- Daria décrypte l'IA, « Les tics de langage de ChatGPT » : https://dariadecrypteia.substack.com/p/les-tics-de-langage-de-chatgpt
- Optimia, « Repérer un texte écrit par l'IA » : https://optimia.substack.com/p/reperer-un-texte-ecrit-par-lia-et
- Projet Voltaire, détecter un texte ChatGPT/IA : https://www.projet-voltaire.fr/ressources/detecter-texte-chatgpt-ia-generative/
- Blog du Modérateur, mots les plus utilisés par ChatGPT : https://www.blogdumoderateur.com/chatgpt-mots-utilises-chatbot/
- gpthuman.ai (FR), mots courants de l'IA : https://gpthuman.ai/fr/mots-courants-de-lia-a-eviter-si-vous-voulez-contourner-les-detecteurs-dia/
- Intelligence-artificielle.com, signes d'un texte ChatGPT : https://intelligence-artificielle.com/textes-generes-par-chatgpt-les-signes-qui-ne-trompent-pas/

Attention : ces sources se contredisent parfois avec Wikipedia. Projet Voltaire cite le « style plat » et l'« absence d'opinion » comme indices, que Wikipedia classe parmi les faux indices. En cas de conflit, suivre Wikipedia.

## [maison]

Choix de style E-Motion, sans preuve qu'il s'agisse de tics IA :

- zéro tiret cadratin (plus strict que Wikipedia, qui tolère un ou deux tirets dans un long texte) ;
- voix passive limitée à celle qui cache un acteur utile ;
- extrêmes paresseux (« tout », « jamais » par réflexe) ;
- ton affirmatif GEO (zéro « peut-être ») sur les pages SEO ;
- typographie française (guillemets « », espaces insécables).

## Base d'origine

`stop-slop` de Hardik Pandya (MIT), adaptée en français : fausse agentivité, narrateur distant, fragmentation dramatique, mises en place rhétoriques, score en 5 dimensions. Ces règles n'ont pas de source externe ; elles restent parce qu'elles visent des effets repérés dans nos propres textes.

## Maintenance

Wikipedia met sa page à jour à chaque génération de modèles (dernière révision lue : 2026-09-26). Relire les sections « High density of AI vocabulary », « Ineffective indicators » et « Historical indicators » à chaque grande sortie de modèle, et déplacer les règles devenues anciennes en priorité basse.
