# GitHub + Render Deployment Guide

## 1. Upload to GitHub

1. Unzip this project folder.
2. Open GitHub and create a new repository.
3. Do not add a README from GitHub because this project already includes one.
4. Open the new repository.
5. Click **Add file → Upload files**.
6. Upload the contents of this folder:
   - index.html
   - package.json
   - package-lock.json
   - render.yaml
   - README.md
   - CUSTOMISE.md
   - .gitignore
   - src folder
7. Click **Commit changes**.

Your GitHub repository must show this structure:

```text
index.html
package.json
package-lock.json
render.yaml
README.md
CUSTOMISE.md
.gitignore
src/
  main.jsx
  styles.css
  config/
    mission.js
  assets/
    rajasthan-satellite-base.jpeg
```

Do not upload `node_modules`. Render will install dependencies automatically.

## 2. Deploy on Render

1. Go to Render.
2. Click **New → Static Site**.
3. Connect your GitHub account.
4. Select this repository.
5. Use these settings:

```text
Build Command: npm install && npm run build
Publish Directory: dist
```

6. Add this environment variable:

```text
NODE_VERSION = 22.12.0
```

7. Click **Create Static Site**.
8. Wait for build to finish.

## 3. If build fails

Use **Manual Deploy → Clear build cache & deploy** after checking:

```text
index.html exists at root
package.json exists at root
src/main.jsx exists
src/config/mission.js exists
src/assets/rajasthan-satellite-base.jpeg exists
Publish Directory is dist
Node version is 22.12.0
```

## 4. Customisation

Edit:

```text
src/config/mission.js
src/styles.css
```

After editing on GitHub, click **Commit changes**. Render will redeploy automatically.
