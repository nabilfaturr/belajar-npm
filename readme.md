# NPM

## Apa itu NPM dan apa kegunaanya?

NPM (Node Package Manager) adalah sebuah tools yang berdiri diatas NodeJS dan berfungsi untuk melakukan management project NodeJS.

Saat kita membuat aplikasi biasanya kita membuat nya dalam bentuk **project**

Sederhananya, project ini berisikan directory / folder yang berisikan program / dependency (library) yang kita butuhkan untuk membuat project kita. seperti : Express, Zod, bcrypt, dll.

Melakukan manajemen dependency secara manual bukanlah hal bijak, karna akan sangat sulit dan complicated sekali ketika dependency tersebut mengeluarkan updated version. thats why dibuat NPM untuk solve problem tersebut.

NPM bisa digunakan untuk download dependency, update, dan upgrade dependency secara otomatis tanpa harus melakukan nya secara manual

## File package.json

`package.json` adalah sebuah file json yang menyimpan semua konfigurasi project kita

ada banyak project configuration yang bisa kita tune di package.json. untuk lebih lengkap nya bisa cek di : 

[package.json | npm Docs](https://docs.npmjs.com/cli/v10/configuring-npm/package-json)

## NPM merubah behaviour Nodejs

ketika di root folder kita terdapat file `package.json`, maka sebelum kita meng-eksekusi node nya, package.json akan di baca terlebih dahulu.

karna hal inilah NPM punya privilege untuk merubah behaviour dari Nodejs kita

## Script

NPM memiliki fitur bernama script, dimana kita bisa menyediakan perintah script yang nanti bisa digunakan untuk menjalankan perintah lainnya.

Fitur ini tidak hanya untuk NPM command saja, tetapi juga bisa untuk Terminal command juga. namun perlu diingat, ketika kita menjalankan perintah NPM, NPM akan menjalankan perintah tersebut bukan di shell yang sama, melaikan NPM akan membuat subshell baru, dan ketika perintah NPM nya selesai, subshell ini akan dihapus.

Penggunaan script ini biasanya digunakan untuk mem-permudah ketika kita menjalankan perintah yang panjang

Untuk menggunakan fitur script, kita bisa tambahkan di package.json

Untuk menjalankan script kita bisa gunakan command `npm run namascript`

```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "run": "node index.js",
    "nge-test": "cd ../../ && pwd"
  },
```

## Special script

docs : 

[scripts | npm Docs](https://docs.npmjs.com/cli/v10/using-npm/scripts)

ada beberapa script special yang ketika script ini digunakan kita bisa langsung me-manggil nya tanpa menggunakan `run`.

Contoh special script : start, stop, test, restart, uninstall, version, dll.

selain itu, terdapat script special untuk script diatas, kita bisa gunakan prefix pre dan post

- pre : dijalankan sebelum special script
- post : dijalankan sesudah special script

misal ketika kita menjalankan `npm start`, maka kita akan menjalankan script prestart, start, poststart

scripts :

```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "prestart": "echo \"menjalankan script prestart\"",
    "start": "node index.js",
    "poststart": "echo \"menjalankan script poststart\""
  },
```

hasil : 

![Untitled](NPM%20e88e4096587a48c58be4a3df12d5ad82/Untitled.png)

package.json, package-lock, node_modules

special script dan prefix

export module 

kenapa ada integrity di package kita?

semantic versioning

dependency 

npm update

dev dependency and production dependency

install dependency tanpa development

.npmignore