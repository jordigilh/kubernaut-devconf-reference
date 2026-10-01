# Kubernaut public CFP reference deck

This is a standalone, browser-based reference copy of the DevConf.US slides for
use in a future KubeCon + CloudNativeCon Europe CFP. It is deliberately separate
from the working presentation directory.

The bundle contains only the allowlisted final slides and their rendering
dependencies. The explicitly marked `DRAFT` slide and working/archive material
are not included.

## Publish with GitHub Pages

Use a **separate public repository** for this folder. Do not make the working
presentation directory public: it contains source files, presentation exports,
and archived material that is not part of the public reference deck.

From this folder:

```bash
git init -b main
git add .
git commit -m "Publish public DevConf reference deck"
gh repo create <owner>/kubernaut-devconf-reference --public --source . --remote origin --push
```

Then enable **Settings → Pages → Deploy from a branch → `main` → `/ (root)`**.
The CFP link will be:

```text
https://<owner>.github.io/kubernaut-devconf-reference/
```

The site is static and needs no build service. Reviewers can use the arrow keys,
thumbnail strip, touch gestures, or the full-screen button. A specific slide can
be linked with a fragment such as `#slide=13`.

## Rebuild the bundle

From the presentation workspace, run:

```bash
python3 scripts/build_public_deck.py
```

The builder copies only the allowlisted slides/assets and fails if a selected
slide contains `Red Hat confidential`. Before publishing, still obtain the
required author/company approval for the contents and links.
