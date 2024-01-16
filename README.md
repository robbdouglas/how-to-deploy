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

10. go to your repo  and click on the settings button right next to "about"! then click on the checkbox "Use your GitHub Pages website" and apply your settings

___

# How to deploy a React Vite project with Render

1. go to the [Render](https://render.com/) website and create an account

2. log in

3. click "new" and choose "static site"

4. choose your repo

5. enter a name, a branch (main), a ".", and "/dist" to publish directory

6. click on "Create Static Site" and wait until your site is deployed

7. if you just see a white website when clicking your deployed url, then

- add the following line to your index.html head:

```html
    <base href="/">
```

- edit the following line in your package.json:

```json
    "build": "vite build",
```

to 

```json
    "build": "vite build --base=./",
```

8. to make sure that you will always see the latest version of your website, go to the Render website, navigate to your repo and change the blue "Manual Deploy" button to "Deploy latest commit"