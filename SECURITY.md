# Politique de sécurité

Cette politique s'applique **par défaut à tous les dépôts publics du compte
`mister-guiiug`**. Un dépôt qui publie son propre `SECURITY.md` la remplace :
c'est le cas de [`dev-pwa-config`](https://github.com/mister-guiiug/dev-pwa-config/blob/main/SECURITY.md),
socle commun d'une vingtaine d'applications, dont le périmètre demande d'être
décrit à part.

## Signaler une vulnérabilité

**N'ouvrez pas d'issue publique.** Utilisez l'onglet **Security** du dépôt
concerné, bouton **Report a vulnerability** : GitHub ouvre un fil privé avec le
mainteneur. Si l'onglet n'est pas disponible sur ce dépôt, écrivez au
mainteneur via son profil.

Merci d'y indiquer :

- le dépôt et la version ou le commit concernés ;
- ce qu'un attaquant obtient concrètement — pas seulement ce qui est anormal ;
- de quoi reproduire : un dépôt minimal vaut mieux qu'une description.

Un accusé de réception sous **72 heures**, un premier diagnostic sous une
semaine. Ces dépôts sont maintenus par une seule personne : ce sont des
engagements de bonne foi, pas un contrat de support.

## Versions suivies

Sauf mention contraire dans le dépôt, seule la **dernière version publiée**
reçoit des correctifs. Les applications web sont déployées en continu : la
version en ligne est la seule suivie.

## Périmètre

Entrent dans le périmètre : le code publié, les workflows GitHub Actions et les
actions composites du dépôt, et ce qu'il déploie.

N'entrent pas dans le périmètre :

- les vulnérabilités de dépendances tierces sans chemin d'exploitation par le
  dépôt — signalez-les en amont, et ouvrez ici une issue publique ordinaire ;
- l'ingénierie sociale et les attaques sur l'infrastructure de GitHub ;
- les rapports produits par un scanner sans démonstration d'impact.

## Deux limites connues, écrites pour ne pas être redécouvertes

- **Clickjacking sur GitHub Pages.** La directive CSP `frame-ancestors` n'a
  d'effet que dans un en-tête HTTP, et GitHub Pages n'en pose aucun. Les
  applications qui y sont déployées n'ont pas de protection effective. Le
  greffon CSP du socle refuse d'ailleurs cette directive plutôt que d'en donner
  l'illusion.
- **Clés publiques par conception.** Les clés `anon` Supabase et les
  `VITE_FIREBASE_*` sont copiées dans le bundle : elles sont publiques par
  construction. Ce qui protège la donnée est la RLS côté Supabase, et App Check
  plus les règles côté Firebase — jamais leur discrétion.
