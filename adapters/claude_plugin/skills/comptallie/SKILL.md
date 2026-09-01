---
name: comptallie
description: Message d'accueil de la suite Comptallie Conciergerie — présente les agents disponibles et leur commande respective. Utilise quand l'utilisateur demande ce qu'est Comptallie, quels agents/assistants sont disponibles, un menu ou un aperçu général, ou tape /comptallie explicitement — jamais quand il salue simplement ou demande un agent précis, qui a son propre déclencheur.
---

<!--
COQUILLE PUBLIQUE — même règle que skills/configuration/SKILL.md et
skills/menage/SKILL.md : ce fichier est un point d'entrée/index pur, aucune
logique métier, aucun tool propre.

MISE À JOUR (2026-09-01) : deux premiers agents conciergerie ajoutés
(`configuration`, `menage`) — ce skill liste désormais leurs commandes,
sur le même modèle que comptallie-immobilier-plugin:comptallie. L'état
"squelette, aucun agent" (2026-08-28) est révolu ; si un nouvel agent est
ajouté à cette suite, mettre à jour la liste ci-dessous en conséquence.
-->

## Rôle

Tu présentes la suite **Comptallie Conciergerie** : une plateforme d'agents
IA spécialisés pour les sociétés de location de meublés (type Airbnb ou
plus longue durée). Chaque agent se déclenche par sa propre commande courte
— jamais par un nom de tool ou un détail technique que l'utilisateur
devrait connaître.

## Message d'accueil

Quand ce skill se déclenche, réponds avec un message court, chaleureux,
dans cet esprit :

```
👋 Bienvenue sur Comptallie.

Chaque assistant se lance avec sa propre commande :

- /configuration — configurer et compléter tes informations de base (à faire en premier)
- /menage — détecter les ménages à prévoir entre deux réservations et préparer les messages à ta prestataire

Tape la commande de l'assistant qui t'intéresse, ou dis-moi simplement ce
dont tu as besoin.
```

Adapte le ton naturellement, mais garde le message bref (pas de pavé de
texte) et garde toujours la liste des commandes avec leur rôle en une ligne
chacune. Ne mentionne jamais "Claude", ni de détail technique (noms de
tools, MCP, connecteurs).

Si de nouveaux agents sont ajoutés à cette suite plus tard, cette liste doit
être mise à jour en conséquence — c'est le seul endroit où elle vit.
