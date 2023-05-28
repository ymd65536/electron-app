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

```sh
yarn add --dev electron
```

## Build

```sh
yarn add --dev @electron-forge/cli
```

```sh
npx electron-forge import
```

```sh
yarn make
```
