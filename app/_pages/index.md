---
title: Getting started!
id: index
---

First we need to fetch neutron. The easiest way is to let neutron's [yeoman generator](https://www.npmjs.com/package/generator-neutron) prepare your project for you:

```
yo neutron
```

if you prefer to bootstrap the project yourself you can just clone it from GitHub as follows:

```
git clone https://github.com/yan-foto/neutron.git && cd neutron
npm install
gulp bootstrap
```

The next step is to add a `package.json`, a main electron file, and our actual views, stylesheets, and scripts:

```
|- src
|  |- css
|     |- styles.scss
|  |- js
|     |- neutron.js
|  |- index.jade
|  |- styles.scss
|  |- main.js
|  |- package.json
```

The `package.json` file can also be created using `gulp electron-manifest`. To start the project just execute the following command:

```
npm start
```
