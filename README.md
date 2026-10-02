# my_salesforce_poc

Salesforce **DevOps Center POC** config repository.

## Topology
| Role | Org |
|------|-----|
| DevOps Center Hub | Developer Edition org |
| Development Environment | Sandbox / Developer Edition (persistent) |
| Release Environment | Developer Edition org |
| Pipeline | `Dry_run` |

## Structure
```
force-app/main/default/   # Salesforce metadata source (classes, objects, tabs, ...)
config/                   # scratch org / project config
sfdx-project.json         # SFDX project definition
```

## Branches
DevOps Center creates feature branches off the pipeline base branch per Work Item.
Do not commit directly to the base branch — let DevOps Center manage branch creation.

## Notes
- Source tracking is not available on sandboxes; use explicit `--metadata`/manifest with SF CLI.
- Metadata deploys do not move data-driven config records (separate data step required).
