# Comptallie — plugin Claude.ai, suite Conciergerie

Ce repo est l'**emballage public** du plugin Claude.ai pour la **suite
commerciale conciergerie / location courte durée** de Comptallie (repo privé
`Comptallie_MCP`). Même principe que `comptallie-immobilier-plugin` : un
repo par suite, cloisonné (cf. `Comptallie_MCP/CLAUDE.md` section 5/6bis).

**Deux agents disponibles (2026-09-01)** : `configuration` (`/configuration`
— informations de base sur la structure cliente) et `menage` (`/menage` —
détection des fenêtres de ménage entre deux réservations à partir des
calendriers iCal, brouillons de message à la prestataire, relance et alerte
propriétaire si besoin). Cf. `Comptallie_MCP/CLAUDE.md` section 6quinquies
pour le détail complet, y compris les limites assumées pour cette
itération (agent Ménage autonome pour ses propres données, brouillons
Gmail uniquement — jamais d'envoi automatique).

Il ne contient **aucune logique métier** : uniquement
`.claude-plugin/marketplace.json` et `adapters/claude_plugin/`
(`plugin.json`, `skills/<agent>/SKILL.md`, `.mcp.json` pointant vers le
serveur MCP distant déjà en ligne — le même que celui de la suite
immobilier, jamais un second serveur dupliqué).

## Structure

```
.claude-plugin/marketplace.json     ← déclare ce plugin
adapters/claude_plugin/
  .claude-plugin/plugin.json        ← métadonnées du plugin
  .mcp.json                         ← pointe vers le serveur MCP distant (Railway)
  skills/
    comptallie/SKILL.md             ← message d'accueil, liste les commandes disponibles
    configuration/SKILL.md          ← agent Configuration (/configuration)
    menage/SKILL.md                 ← agent Ménage (/menage)
```

Quand un nouvel agent conciergerie sera ajouté : créer son
`skills/<agent>/SKILL.md`, mettre à jour `comptallie/SKILL.md` pour le
lister, bumper `plugin.json`, et ajouter son id à l'entrée `CONCIERGERIE`
de `core/catalog/suites.py` (repo privé).
