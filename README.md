# PullDex

Kortopslags-værktøj til Pokémon-pack-opening streams. Slår kort op via det gratis
[pokemontcg.io](https://pokemontcg.io) API og giver kopiér-klare felter (navn, billede-URL,
foreslået sjældenhed, Cardmarket/TCGplayer-pris, og en færdig linje til Poglys Hit Archive-liste).

Ren statisk side — ingen build, ingen server, ingen database. `index.html` er det hele.

## Sådan lægger du den på GitHub (privat) + Render

### 1. Opret et privat GitHub-repo
1. Gå til [github.com/new](https://github.com/new)
2. Repository name: `pulldex` (eller hvad du vil)
3. Vælg **Private**
4. Opret repoet UDEN readme/gitignore (vi har allerede filerne lokalt)

### 2. Push koden op
Kør i denne mappe (`C:\Users\Horam\Desktop\PullDex`):

```bash
git init
git add .
git commit -m "Initial PullDex"
git branch -M main
git remote add origin https://github.com/DIT-BRUGERNAVN/pulldex.git
git push -u origin main
```

(Erstat `DIT-BRUGERNAVN/pulldex` med det repo du lige oprettede.)

### 3. Deploy på Render
1. Gå til [dashboard.render.com](https://dashboard.render.com) og log ind
2. **New +** → **Static Site**
3. Connect til GitHub, giv Render adgang til det private repo, vælg `pulldex`
4. Render læser automatisk `render.yaml` i repoet — build command og publish path er allerede sat
5. Klik **Create Static Site** — du får en URL som `https://pulldex.onrender.com` du kan dele med dine venner

Fra nu af: hver gang du `git push`, redeployer Render automatisk.

## Workflow under stream

Alle med linket kan søge kort samtidig fra hver deres browser. Fordi Pogly selv er
et samarbejds-værktøj, kan I alle sammen have Pogly-projektet åbent på samme tid —
den der finder det rigtige kort, indsætter bare navn/billede/pris/sjældenhed (eller
Hit Archive-linjen) direkte i widgetens delte controls-panel, og det opdateres live
for alle med det samme. Ingen ekstra infrastruktur nødvendig ud over selve siden her.
