# 🔥 Nuxt-Fire
<p align="center"><img align="center" height="300px" src="https://nuxt-fire-demo.firebaseapp.com/logo_text.png"/></p>

> Easily intergrate Firebase into your Nuxt 2 project.

## Demo

[Demo](https://nuxt-fire-demo.firebaseapp.com/)

## Requirements

Make sure you have Nuxt and Firebase installed in your project.

```json
"dependencies": {
  "nuxt": "^2.3.1",
  "firebase": "^5.5.8"
}
```

## Install

```bash
npm i nuxt-fire
```

## Quick Setup

Add the below code to **nuxt.config.js**.

```js
modules: [
    [
      'nuxt-fire',
      {
        config: {
          apiKey: '<apiKey>',
          authDomain: '<authDomain>',
          databaseURL: '<databaseURL>',
          projectId: '<projectId>',
          storageBucket: '<storageBucket>',
          messagingSenderId: '<messagingSenderId>'
        }
      }
    ]
  ],
```

## Options

#### useOnly

By default, all supported Firebase products are loaded. If you only wish to load certain products (recommended!), add this `useOnly` option.

- type: `Array<string>`
- default: `null`
- accepted: `['auth','firestore','functions','storage','realtimeDb']`

#### config

Your firebase config snippet. You can retrieve this information from your Firebase project's overview page:

`https://console.firebase.google.com/project/your-project-id/overview`

```js
{
  apiKey: '<apiKey>',
  authDomain: '<authDomain>',
  databaseURL: '<databaseURL>',
  projectId: '<projectId>',
  storageBucket: '<storageBucket>',
  messagingSenderId: '<messagingSenderId>'
}
```

Only applies when `NODE_ENV === 'production'` .

#### devConfig

Same es `config`, but applies when `NODE_ENV === 'development'`.

## Usage

You can access the various Firebase products with **\$foo** in almost any context using `app.$foo` or `this.$foo`, including store actions. Make sure to replace the _foo_ with a shortcut from the table below.

Firebase products supported by nuxt-fire so far:

| Firebase Product  | Shortcut      |
| ----------------- | ------------- |
| Authentication    | \$fireAuth    |
| RealTime Database | \$fireDb      |
| Firestore         | \$fireStore   |
| Storage           | \$fireStorage |
| Functions         | \$fireFunc    |

See [Firebase's official docs](https://firebase.google.com/docs/) for more usage information.

### Examples

Check out the [GitHub Repo](https://github.com/lupas/nuxt-fire-demo) of our [Demo](https://nuxt-fire-demo.firebaseapp.com/) for example code.
