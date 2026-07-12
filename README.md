# Stop Slop

A skill for removing AI tells from prose.

<img width="3840" height="2160" alt="G-Yg4RVbIAAhVxW" src="https://github.com/user-attachments/assets/902afc15-1f40-4a9d-af24-8cd67afb8ebf" />

## What this is

AI writing has patterns. Predictable phrases, structures, rhythms. This skill teaches Claude (or any LLM) to catch and remove them.

## Skill Structure

```
stop-slop/
├── SKILL.md              # Core instructions
├── references/
│   ├── phrases.md        # Phrases to remove
│   ├── structures.md     # Structural patterns to avoid
│   └── examples.md       # Before/after transformations
├── README.md
└── LICENSE
```

## Quick start

**Claude Code:** Add this folder as a skill.

**Claude Projects:** Upload `SKILL.md` and reference files to project knowledge.

**Custom instructions:** Copy core rules from `SKILL.md`.

**API calls:** Include `SKILL.md` in your system prompt. Reference files load on demand.

## What it catches

**Banned phrases** - Throat-clearing openers, emphasis crutches, business jargon, all adverbs, vague declaratives, meta-commentary. See `references/phrases.md`.

**Structural clichés** - Binary contrasts, negative listings, dramatic fragmentation, rhetorical setups, false agency, narrator-from-a-distance voice, passive voice. See `references/structures.md`.

**Sentence-level rules** - No Wh- sentence starters, no em dashes, no staccato fragmentation, no lazy extremes, active voice required.

## Scoring

Rate 1-10 on each dimension:

| Dimension | Question |
|-----------|----------|
| Directness | Statements or announcements? |
| Rhythm | Varied or metronomic? |
| Trust | Respects reader intelligence? |
| Authenticity | Sounds human? |
| Density | Anything cuttable? |

Below 35/50: revise.

## Adaptation française (E-Motion / So'6 Rallye)

Ce fork ajoute une adaptation française du skill, à côté des fichiers anglais d'origine (conservés intacts pour suivre l'amont) :

```
SKILL.fr.md                    # version française (déployée sous le nom em-stop-slop)
references/phrases-fr.md       # tics d'écriture IA en français (avec sources)
references/structures-fr.md    # structures à éviter, adaptées au français
references/examples-fr.md      # transformations avant/après en français
```

Les tics français ne sont pas une traduction littérale de la liste anglaise : ils ciblent les formules réellement surutilisées par l'IA en français, corroborées par des sources francophones (voir la section Sources de `references/phrases-fr.md`). L'adaptation ajoute aussi des garde-fous pour un usage dans un pipeline SEO/GEO (ne pas toucher aux titres-questions, au mot-clé cible ni aux sources).

## Author

Original : [Hardik Pandya](https://hvpandya.com)
Adaptation française : E-Motion / So'6 Rallye

## License

MIT. Use freely, share widely.
