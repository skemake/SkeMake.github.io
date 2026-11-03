---
# Visas inte på startsidan, länkas från introtexten i stället.
hidden: true
---
# Skapa dokumentation

Den här guiden förklara hur man föreslår förändringar i SkeMakes dokumentation. Den kräver ingen kunskap i programmering, och de enkla ändringarna görs direkt på GitHub.

## Förutsättningar
 - GitHub-konto


## Forka repot
SkeMakes GitHub Pages finns på [SkeMake](https://github.com/skemake/SkeMake.github.io). Skapa en egen fork (en egen kopia) av det till din egen GitHub-användare [Working with forks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo).

## Gör dina ändringar
### Enkla förändringar
För enkla förändringar kan man editera direkt i github's websida. 

### Mer avancerade förändringar
För att lägga till sidor, bilder eller liknande behöver man checka ut sin fork lokalt. 
Dokumentationen skrivs i GitHubs [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

### Förhandsgranska lokalt
Repot innehåller en container med samma Jekyll-version som GitHub Pages använder. Med [Docker](https://docs.docker.com/get-docker/) installerat kör du:

```sh
docker compose -f .devcontainer/compose.yaml up
```

Öppna sedan <http://localhost:4000>. Sidan laddas om automatiskt när du sparar en fil. Använder du VS Code kan du i stället öppna repot i en [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers), då startar servern av sig själv.

QR-koderna längst ner på sidorna skapas bara vid publicering och syns inte lokalt.

## Publicera
För att publicera dina ändringar skapar du en [pull request](https://github.blog/developer-skills/github/beginners-guide-to-github-creating-a-pull-request/). SkeMake granskar då dina förslag, och när dom är godkända så publiceras det automatiskt.


