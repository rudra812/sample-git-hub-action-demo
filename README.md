# sample-git-hub-action-demo

# search for github actions marketplace

• actions/checkout@v4 — download repository code
• actions/setup-node@v4 — set up Node.js
• actions/cache@v4 — cache dependencies
• actions/upload-artifact@v4 — save build files or test reports


name: "first workflow"
on: push
jobs:
  first-job:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v4
        with:
          node-version: 24
          cache: npm

      - name: install dependency
        run: npm ci

      - name: make react build
        run: npm run build
