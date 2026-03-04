## acat-game

Automatically build https://github.com/CSCI-526/main-assignment-a-cat-a-mouse-and-a-house via github actions.

**Live game:** https://dw61.github.io/acat-game/latest

## Usage

As a collaborator, go to https://github.com/dw61/acat-game/actions/workflows/webgl-pages.yml and click **Run workflow** from the main branch.

The github action will automatically fetch the current main branch commit from the upstream game repo. It will update `/acat-game/latest` and create a versioned snapshot at `/acat-game/<upstream-short-commit-SHA>`, e.g. https://dw61.github.io/acat-game/4904297

