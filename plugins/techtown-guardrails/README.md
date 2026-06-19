# techtown-guardrails

Plugin Claude Code de garde-fous pour les projets TechTown.

## Hooks

| Hook | Event | Effet |
|------|-------|-------|
| `block-secrets.sh` | `PreToolUse` `Write\|Edit` | **Bloque** l'écriture/édition de `.env` (réel), `*service-account*.json`, `*credentials*.json`, `*-sa.json`. Autorise `*.example`, `*.sample`, `*.template`, `*.dist`. |
| `terraform-fmt.sh` | `PostToolUse` `Write\|Edit` | Applique `terraform fmt` après édition d'un `.tf`/`.tfvars`. No-op silencieux sinon ou si `terraform` absent. Ne bloque jamais. |

## Dépendances

- `jq` (parsing du payload hook sur stdin)
- `terraform` (optionnel — le hook fmt est no-op s'il est absent)

## Installation (via la marketplace TechTown)

```
/plugin marketplace add techtown-fr/skills
/plugin install techtown-guardrails@techtown
```

## Déploiement org (managed)

Pour l'imposer à toute l'org via les managed settings (console admin) :

```json
{
  "extraKnownMarketplaces": {
    "techtown": { "source": { "source": "github", "repo": "techtown-fr/skills" } }
  },
  "enabledPlugins": { "techtown-guardrails@techtown": true }
}
```

Un plugin force-activé via `enabledPlugins` managé voit ses hooks chargés même sous `allowManagedHooksOnly` (canal officiel de distribution de hooks vettés).
