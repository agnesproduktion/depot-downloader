# 🚀 depot-downloader

A simple **Steam Depot Downloader** written in JavaScript for Node.js and Bun.  
Download game files directly from Steam depots using a **manifest file** and a **decryption key**.

---

## 📦 Installation

### Using npm:
```sh
npm install -g depot-downloader
````

This installs the CLI globally so you can run `depot-downloader` anywhere.

---

## ⚙️ CLI Usage

Once installed globally, run:

```sh
depot-downloader --manifest <path-to-manifest> --key <decryption-key>
```

### Optional flags:

| Flag                  | Description            | Default    |
| --------------------- | ---------------------- | ---------- |
| `--output <dir>`      | Output directory       | `./output` |
| `--max-servers <num>` | Max parallel downloads | `2`        |

---

## 🧩 Library Usage (Programmatic)

You can also use it directly in your JavaScript or Bun project:

```js
import { Downloader } from 'depot-downloader'

const downloader = new Downloader({
    outputDirectory: './output',
    maxServers: 2,
});

downloader.on('progress', console.log)
downloader.on('finish', console.log)
downloader.on('error', console.error)

await downloader.downloadDepot({
    manifestFile: './Path/To/File.manifest',
    decryptionKey: 'YOUR_DEPOT_KEY_IN_HEX',
})
```

---

## 📊 Events

| Event      | Description                          |
| ---------- | ------------------------------------ |
| `progress` | Called whenever progress updates     |
| `finish`   | Called when all files are downloaded |
| `error`    | Called if something goes wrong       |

---

## ❤️ Credits

This project includes code adapted from:

* [DoctorMcKay/node-steam-user](https://github.com/DoctorMcKay/node-steam-user) (MIT License)

---