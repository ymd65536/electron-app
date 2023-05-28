# yarn でelectronアプリを構築する

## SetUp

```sh
yarn init
```

package.jsonは以下のとおり

```json
{
  "name": "electron-app",
  "version": "1.0.0",
  "description": "Hello World!",
  "main": "main.js",
  "author": "Kento Yamada",
  "license": "MIT",
  "devDependencies": {
    "electron": "^24.4.0"
  },
  "scripts": {
    "start": "electron ."
  }
}
```

## Build

```sh
yarn add --dev electron
```

```sh
yarn add --dev @electron-forge/cli
```

```sh
npx electron-forge import
```

```sh
yarn make
```

`yarn make`まで実行すると以下の`package.json`が完成する。

`package.json`

```json
{
  "name": "electron-app",
  "version": "1.0.0",
  "description": "Hello World!",
  "main": "main.js",
  "author": "Kento Yamada",
  "license": "MIT",
  "devDependencies": {
    "@electron-forge/cli": "^6.1.1",
    "@electron-forge/maker-deb": "^6.1.1",
    "@electron-forge/maker-rpm": "^6.1.1",
    "@electron-forge/maker-squirrel": "^6.1.1",
    "@electron-forge/maker-zip": "^6.1.1",
    "electron": "^24.4.0"
  },
  "scripts": {
    "start": "electron-forge start",
    "package": "electron-forge package",
    "make": "electron-forge make"
  },
  "dependencies": {
    "electron-squirrel-startup": "^1.0.0"
  }
}
```

`@electron-forge/cli` をインストールすると生成される`forge.config.js`

```js
module.exports = {
  packagerConfig: {},
  rebuildConfig: {},
  makers: [
    {
      name: '@electron-forge/maker-squirrel',
      config: {},
    },
    {
      name: '@electron-forge/maker-zip',
      platforms: ['darwin'],
    },
    {
      name: '@electron-forge/maker-deb',
      config: {},
    },
    {
      name: '@electron-forge/maker-rpm',
      config: {},
    },
  ],
};
```
