## acat-game

Automated WebGL build and versioned deployment pipeline for [CSCI-526/main-assignment-a-cat-a-mouse-and-a-house](https://github.com/CSCI-526/main-assignment-a-cat-a-mouse-and-a-house) via GitHub Actions.

**Live game:** https://dw61.github.io/acat-game/latest/

Each deployment is also archived at `https://dw61.github.io/acat-game/builds/<commit-sha>/`, and the commit SHA + build timestamp are shown in the bottom-right corner of the game page.

## Usage

### Trigger a build

As a maintainer or collaborator, go to [Actions → WebGL versioned Pages → Run workflow](https://github.com/dw61/acat-game/actions/workflows/webgl-pages.yml) and click **Run workflow**. The workflow will:

1. Check out the latest `main` from the upstream game repo
2. Free disk space if needed (skipped automatically if ≥ 35 GB is available)
3. Build the project for WebGL using Unity
4. Inject the commit SHA and build date into the page
5. Publish to GitHub Pages under `/latest/` and `/builds/<sha>/`

Builds also trigger automatically on every push to `main` in this repo.

### Required secrets

The following secrets must be set in **Settings → Secrets and variables → Actions**:

| Secret | Description |
|---|---|
| `PAT_CLASSIC` | Personal access token (classic) with `repo` scope to read the upstream private repo |
| `UNITY_SERIAL` | Unity license serial number |
| `UNITY_EMAIL` | Unity account email |
| `UNITY_PASSWORD` | Unity account password |

### Branch protection

All branches are locked. Only the repository admin can push. Collaborators can only trigger the workflow manually via the Actions tab.
