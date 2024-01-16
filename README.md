# How to deploy a React project to GitHub Pages

1. create repo on GitHub
2. create react app
3. install gh-pages:

```bash
npm install gh-pages --save-dev
```

4. go to package.json and add the following lines of code as a property:

```json
  "homepage": "https://github.com/{username}/{repo-name}.git",
```

this is the link to your repo (you can copy it from the address bar on GitHub)

5. stay in the package.json file and add the following lines of code to the scripts property:

```json
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist",
```

note: dist when using vite, build when using create-react-app

6. terminal: 

```bash
$ git remote add origin https://github.com/{username}/{repo-name}.git
```

skip this step if you already have a remote repo

7. go to vite.config.js and add the following lines of code:

```js
base: '/how-to-deploy',
```

8. terminal:

```bash
npm run deploy
```

9. go to GitHub repo and refresh the page. now you should see 2 branches