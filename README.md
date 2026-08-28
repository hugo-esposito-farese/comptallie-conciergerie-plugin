# Comptallie — plugin Claude.ai, suite Conciergerie

Ce repo est l'**emballage public** du plugin Claude.ai pour la **suite
commerciale conciergerie / location courte durée** de Comptallie (repo privé
`Comptallie_MCP`). Même principe que `comptallie-immobilier-plugin` : un
repo par suite, cloisonné (cf. `Comptallie_MCP/CLAUDE.md` section 5/6bis).

**État actuel : squelette uniquement.** Aucun agent conciergerie n'est
encore construit ni validé (cf. `Comptallie_MCP/CLAUDE.md` section 1) — ce
repo ne contient qu'un seul skill d'accueil honnête (`comptallie`), qui ne
liste aucune commande d'agent. Pas d'entrée `CONCIERGERIE` dans
`core/catalog/suites.py` côté repo privé non plus, prématuré tant qu'aucun
agent n'existe.

Il ne contient **aucune logique métier** : uniquement
`.claude-plugin/marketplace.json` et `adapters/claude_plugin/`
(`plugin.json`, `skills/comptallie/SKILL.md`, `.mcp.json` pointant vers le
serveur MCP distant déjà en ligne — le même que celui de la suite
immobilier, jamais un second serveur dupliqué).

## Structure

```
.claude-plugin/marketplace.json     ← déclare ce plugin
adapters/claude_plugin/
  .claude-plugin/plugin.json        ← métadonnées du plugin
  .mcp.json                         ← pointe vers le serveur MCP distant (Railway)
  skills/
    comptallie/SKILL.md             ← message d'accueil honnête, aucun agent listé
```

Quand un premier agent conciergerie sera validé : ajouter son
`skills/<agent>/SKILL.md`, mettre à jour `comptallie/SKILL.md` pour le
lister, bumper `plugin.json`, et ajouter l'entrée `CONCIERGERIE`
correspondante dans `core/catalog/suites.py` (repo privé).
