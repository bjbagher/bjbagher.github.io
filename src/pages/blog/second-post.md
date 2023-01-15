---
layout: "../../layouts/BlogPost.astro"
title: "Run Prettier on Github Actions"
description: "Run Prettier on Github Actions"
pubDate: "Jan 12 2023"
heroImage: "/assets/gh_actions.png"
---

## How to run

1. Add the following job to your workflow

```yaml
jobs:
  run-prettier:
    runs-on: macos-latest

    steps:
      - uses: actions/checkout@v3
        with:
          token: ${{ secrets.GH_TOKEN }}
          ref: ${{ github.head_ref }}
      - run: |
          npx prettier --write .
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add . 
          git commit -m "Automatic Changes"  || echo "no changes"
          git push || echo "no changes"
```

2. Make sure to have the following permissions

```yaml
permissions:
packages: write
contents: write
deployments: write
pull-requests: write
issues: write
pages: write
id-token: write
repository-projects: write
```

**_Checkout the [source code](https://github.com/bjbagher/bjbagher.github.io) of this website for a more detailed example._**
