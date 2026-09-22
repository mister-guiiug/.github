# `.github` — ce qui vaut pour tous les dépôts du compte

Ce dépôt ne contient aucun code. GitHub y cherche les **fichiers communautaires
par défaut** du compte `mister-guiiug` : tout dépôt public qui n'a pas les
siens hérite de ceux-ci.

| Fichier                                                            | Ce qu'il devient                                                              |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| [`SECURITY.md`](./SECURITY.md)                                     | La politique de signalement affichée sur l'onglet *Security* de chaque dépôt  |
| [`.github/PULL_REQUEST_TEMPLATE.md`](./.github/PULL_REQUEST_TEMPLATE.md) | Le corps pré-rempli de toute nouvelle pull request                            |
| [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE)               | Les gabarits d'anomalie et d'évolution                                        |
| [`.github/FUNDING.yml`](./.github/FUNDING.yml)                      | Le bouton *Sponsor*                                                            |

Un dépôt qui publie sa propre version d'un de ces fichiers garde la sienne :
l'héritage ne s'applique qu'en son absence. C'est le cas de
[`dev-pwa-config`](https://github.com/mister-guiiug/dev-pwa-config), dont la
politique de sécurité et le gabarit de PR décrivent un socle consommé par une
vingtaine d'applications, ce qu'une version générique ne saurait dire.

## Pourquoi ce dépôt existe

Au relevé du 05/09/2026, **aucun dépôt du compte n'avait de politique de
sécurité** hormis le socle : vingt-trois dépôts publics n'offraient aucun canal
de signalement privé, et rien ne le disait. Les fichiers communautaires par
défaut règlent ce cas d'un seul endroit, sans rien copier dans chaque dépôt.

## Ce que ce dépôt ne contient PAS, et pourquoi

**Aucun préréglage Renovate.** Treize dépôts ont longtemps étendu
`github>mister-guiiug/.github//renovate/default.json` — un chemin dans un dépôt
qui n'existait pas. Renovate n'a donc jamais ouvert la moindre pull request, et
personne ne s'en est aperçu pendant des mois : **un préréglage cassé ne fait
pas de bruit, il ne fait rien.** Le préréglage vit désormais dans le socle,
à [`renovate/default.json`](https://github.com/mister-guiiug/dev-pwa-config/blob/main/renovate/default.json),
et tous les dépôts pointent là. En remettre un ici recréerait exactement
l'ambiguïté qui a coûté ces mois-là.

**Aucun `profile/README.md`.** Ce mécanisme n'existe que pour les
*organisations*. Pour un compte personnel comme celui-ci, GitHub affiche le
`README.md` du dépôt qui porte **le nom du compte** : le profil vit donc dans
[`mister-guiiug/mister-guiiug`](https://github.com/mister-guiiug/mister-guiiug).
Un fichier posé ici ne s'afficherait nulle part.

**Aucune licence par défaut.** Le `LICENSE` de ce dépôt ne couvre que lui :
GitHub n'hérite pas les licences, et un dépôt public sans la sienne est « tous
droits réservés » par défaut, quoi qu'il y ait ici. Cela se corrige dépôt par
dépôt.
