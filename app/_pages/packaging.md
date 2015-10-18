---
title: Packaging your app
id: packaging
---

[electron-packager](https://github.com/maxogden/electron-packager) has been integrated to package your app by executing either of the following commands:

```
npm run packager
gulp package
```

The options for `electron-packager` module are defined in `neutron.rc` and the possible values are define in the [official docs](https://github.com/maxogden/electron-packager#opts). The default values are as follows:

```js
"packager": {
  "dir": "dist",
  "out": "packages",
  "name": "neutron",
  "platform": "all",
  "arch": "all",
  "version": "0.30.4",
  "overwrite": true
}
```

Such configuration packages the app under `dist` directory for all platforms (Linux, Max, Win) and architectures (ia32, x64) and writes the output under `packages` directory. 
