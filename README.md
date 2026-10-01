# Biddynamic Scraper - Node.js Komiku Mirror Scraper

> **GitHub Repository Title**
>
> ```text
> Biddynamic Scraper - Node.js Komiku Mirror Scraper
> ```
>
> **Repository Name**
>
> ```text
> biddynamic-scraper
> ```
>
> **GitHub Repository Description**
>
> ```text
> Node.js scraper for Biddynamic (Komiku mirror). Get latest manga, search results, manga details, chapter lists, chapter images, navigation, and image downloads in JSON format.
> ```

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-16%2B-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js">
  <img src="https://img.shields.io/badge/Axios-HTTP%20Client-5A29E4?style=for-the-badge&logo=axios&logoColor=white" alt="Axios">
  <img src="https://img.shields.io/badge/Cheerio-HTML%20Parser-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="Cheerio">
  <img src="https://img.shields.io/badge/Creator-SCRIPETEREN-181717?style=for-the-badge&logo=github&logoColor=white" alt="Creator">
</p>

<p align="center">
  <b>Node.js scraper untuk Biddynamic / Komiku Mirror.</b><br>
  Mengambil manga terbaru, hasil pencarian, detail manga, daftar chapter, gambar halaman chapter, navigasi chapter, dan download gambar chapter dalam format JSON.
</p>

---

## ✨ Fitur

- Mengambil manga terbaru dari halaman utama Biddynamic
- Mencari manga berdasarkan judul atau keyword
- Mengambil URL detail manga
- Mengambil poster atau cover manga
- Mengambil sinopsis manga
- Mengambil metadata manga seperti status, author, type, dan data lain yang tersedia
- Mengambil genre manga
- Mengambil daftar chapter manga
- Mengambil nomor chapter dari URL
- Mengambil label atau nama chapter
- Mengambil tanggal chapter jika tersedia
- Mengambil seluruh gambar halaman dari sebuah chapter
- Mengambil jumlah gambar halaman chapter
- Mengambil URL chapter sebelumnya
- Mengambil URL chapter berikutnya
- Mendownload gambar chapter ke folder lokal
- Penamaan file gambar otomatis menggunakan format `001`, `002`, `003`, dan seterusnya
- Mendukung URL lengkap dan path URL
- Output JSON yang mudah digunakan untuk bot, API, website, atau aplikasi Node.js

---

## 🛠️ Teknologi

Project ini dibangun menggunakan:

- [Node.js](https://nodejs.org/)
- [Axios](https://axios-http.com/)
- [Cheerio](https://cheerio.js.org/)
- Built-in module `fs`
- Built-in module `path`

---

## 📂 Struktur Project

```text
biddynamic-scraper/
├── biddynamic.js
├── package.json
├── package-lock.json
├── .gitignore
├── README.md
└── LICENSE
```

---

## ⚙️ Instalasi

Clone repository:

```bash
git clone [https://github.com/SCRIPETEREN/biddynamic-scraper.git](https://github.com/SCRIPETEREN/biddynamic-scraper.git)
```

Masuk ke folder repository:

```bash
cd biddynamic-scraper
```

Install semua dependency:

```bash
npm install
```

Jika belum membuat file `package.json`, install dependency secara manual:

```bash
npm install axios cheerio
```

Untuk melihat format penggunaan command:

```bash
node biddynamic.js help
```

---

## 📦 package.json

Buat file bernama `package.json` dengan isi berikut:

```json
{
  "name": "biddynamic-scraper",
  "version": "1.0.0",
  "description": "Node.js scraper untuk Biddynamic atau Komiku Mirror.",
  "main": "biddynamic.js",
  "scripts": {
    "start": "node biddynamic.js latest",
    "latest": "node biddynamic.js latest",
    "help": "node biddynamic.js help"
  },
  "keywords": [
    "biddynamic",
    "komiku",
    "komiku-mirror",
    "manga",
    "manhwa",
    "manhua",
    "scraper",
    "nodejs",
    "axios",
    "cheerio"
  ],
  "author": "SCRIPETEREN",
  "license": "MIT",
  "dependencies": {
    "axios": "^1.7.9",
    "cheerio": "^1.0.0"
  }
}
```

Setelah file dibuat, jalankan:

```bash
npm install
```

Menjalankan manga terbaru melalui NPM:

```bash
npm start
```

Atau:

```bash
npm run latest
```

---

## 🚀 Cara Penggunaan

Format dasar:

```bash
node biddynamic.js <command> <argument>
```

Daftar command yang tersedia:

```text
latest
search
detail
chapter
download
help
```

---

## 📋 Daftar Command

| Command | Fungsi | Contoh |
|---|---|---|
| `latest` | Mengambil manga terbaru dari homepage | `node biddynamic.js latest` |
| `search <query>` | Mencari manga berdasarkan keyword | `node biddynamic.js search "one piece"` |
| `detail <url>` | Mengambil detail manga dan semua chapter | `node biddynamic.js detail https://biddynamic.com/komik/contoh-manga/` |
| `chapter <url>` | Mengambil gambar halaman dari chapter | `node biddynamic.js chapter https://biddynamic.com/baca/contoh-manga/1/` |
| `download <url> [outDir]` | Download semua gambar chapter | `node biddynamic.js download https://biddynamic.com/baca/contoh-manga/1/` |
| `help` | Menampilkan petunjuk penggunaan | `node biddynamic.js help` |

---

## 🆕 Manga Terbaru

Untuk mengambil daftar manga terbaru dari halaman utama:

```bash
node biddynamic.js latest
```

Script akan mengambil data dari:

```text
[https://biddynamic.com/](https://biddynamic.com/)
```

Data yang diambil dari setiap manga:

- `title` — Judul manga
- `url` — URL detail manga
- `image` — URL cover atau poster manga
- `views` — Jumlah views apabila tersedia

Contoh output:

```json
{
  "author": "SCRIPETEREN",
  "status": true,
  "data": {
    "url": "[https://biddynamic.com/](https://biddynamic.com/)",
    "count": 10,
    "items": [
      {
        "title": "Contoh Manga",
        "url": "[https://biddynamic.com/komik/contoh-manga/](https://biddynamic.com/komik/contoh-manga/)",
        "image": "[https://biddynamic.com/wp-content/uploads/contoh-cover.jpg](https://biddynamic.com/wp-content/uploads/contoh-cover.jpg)",
        "views": "10K"
      }
    ]
  }
}
```

---

## 🔎 Search Manga

Gunakan command `search` untuk mencari manga, manhwa, atau manhua.

Format:

```bash
node biddynamic.js search "<query>"
```

Contoh:

```bash
node biddynamic.js search "one piece"
```

```bash
node biddynamic.js search "solo leveling"
```

```bash
node biddynamic.js search "lookism"
```

```bash
node biddynamic.js search "martial peak"
```

Script menggunakan endpoint pencarian berikut:

```text
[https://biddynamic.com/cari?q=](https://biddynamic.com/cari?q=)<query>
```

Contoh output:

```json
{
  "author": "SCRIPETEREN",
  "status": true,
  "data": {
    "query": "one piece",
    "url": "[https://biddynamic.com/cari?q=one%20piece](https://biddynamic.com/cari?q=one%20piece)",
    "count": 5,
    "items": [
      {
        "title": "One Piece",
        "url": "[https://biddynamic.com/komik/one-piece/](https://biddynamic.com/komik/one-piece/)",
        "image": "[https://biddynamic.com/wp-content/uploads/one-piece.jpg](https://biddynamic.com/wp-content/uploads/one-piece.jpg)",
        "views": "1M"
      }
    ]
  }
}
```

---

## 📚 Detail Manga

Gunakan command `detail` untuk mengambil data lengkap sebuah manga.

Format:

```bash
node biddynamic.js detail <url_komik>
```

Contoh dengan URL penuh:

```bash
node biddynamic.js detail [https://biddynamic.com/komik/contoh-manga/](https://biddynamic.com/komik/contoh-manga/)
```

Contoh menggunakan path URL:

```bash
node biddynamic.js detail /komik/contoh-manga/
```

Data yang dapat diperoleh:

- URL manga
- Judul manga
- Cover manga
- Sinopsis
- Metadata atau informasi manga
- Genre
- Jumlah chapter
- Daftar chapter
- URL chapter
- Nomor chapter
- Label chapter
- Tanggal chapter jika tersedia

Contoh output:

```json
{
  "author": "SCRIPETEREN",
  "status": true,
  "data": {
    "url": "[https://biddynamic.com/komik/contoh-manga/](https://biddynamic.com/komik/contoh-manga/)",
    "title": "Contoh Manga",
    "image": "[https://biddynamic.com/wp-content/uploads/contoh-cover.jpg](https://biddynamic.com/wp-content/uploads/contoh-cover.jpg)",
    "synopsis": "Sinopsis singkat manga.",
    "info": {
      "status": "Ongoing",
      "author": "Contoh Author",
      "type": "Manhwa"
    },
    "genres": [
      "Action",
      "Adventure",
      "Fantasy"
    ],
    "chapterCount": 100,
    "chapters": [
      {
        "url": "[https://biddynamic.com/baca/contoh-manga/100/](https://biddynamic.com/baca/contoh-manga/100/)",
        "chapter": "100",
        "label": "Chapter 100",
        "date": "1 hari lalu"
      }
    ]
  }
}
```

---

## 📖 Detail Chapter

Gunakan command `chapter` untuk mengambil seluruh gambar halaman dalam sebuah chapter.

Format:

```bash
node biddynamic.js chapter <url_chapter>
```

Contoh dengan URL penuh:

```bash
node biddynamic.js chapter [https://biddynamic.com/baca/contoh-manga/100/](https://biddynamic.com/baca/contoh-manga/100/)
```

Contoh menggunakan path URL:

```bash
node biddynamic.js chapter /baca/contoh-manga/100/
```

Data yang dapat diperoleh:

- URL chapter
- Judul chapter
- Jumlah gambar halaman
- Daftar gambar chapter
- Nomor urut gambar
- URL gambar
- URL chapter sebelumnya
- URL chapter selanjutnya

Contoh output:

```json
{
  "author": "SCRIPETEREN",
  "status": true,
  "data": {
    "url": "[https://biddynamic.com/baca/contoh-manga/100/](https://biddynamic.com/baca/contoh-manga/100/)",
    "title": "Contoh Manga Chapter 100",
    "imageCount": 20,
    "images": [
      {
        "index": 1,
        "url": "[https://cdn.example.com/contoh-manga/chapter-100/001.jpg](https://cdn.example.com/contoh-manga/chapter-100/001.jpg)"
      },
      {
        "index": 2,
        "url": "[https://cdn.example.com/contoh-manga/chapter-100/002.jpg](https://cdn.example.com/contoh-manga/chapter-100/002.jpg)"
      }
    ],
    "prevChapter": "[https://biddynamic.com/baca/contoh-manga/99/](https://biddynamic.com/baca/contoh-manga/99/)",
    "nextChapter": "[https://biddynamic.com/baca/contoh-manga/101/](https://biddynamic.com/baca/contoh-manga/101/)"
  }
}
```

---

## ⬇️ Download Chapter

Command `download` digunakan untuk mendownload seluruh gambar chapter ke perangkat atau server lokal.

Format:

```bash
node biddynamic.js download <url_chapter> [outDir]
```

Download dengan folder otomatis:

```bash
node biddynamic.js download [https://biddynamic.com/baca/contoh-manga/100/](https://biddynamic.com/baca/contoh-manga/100/)
```

Jika folder output tidak ditentukan, script otomatis membuat folder:

```text
komiku-dl/<timestamp>/
```

Contoh struktur hasil download:

```text
komiku-dl/
└── 1760000000000/
    ├── 001.jpg
    ├── 002.jpg
    ├── 003.jpg
    ├── 004.jpg
    └── 005.jpg
```

Download menggunakan folder custom:

```bash
node biddynamic.js download [https://biddynamic.com/baca/contoh-manga/100/](https://biddynamic.com/baca/contoh-manga/100/) ./downloads/contoh-manga-chapter-100
```

Contoh output JSON:

```json
{
  "author": "SCRIPETEREN",
  "status": true,
  "data": {
    "dir": "./downloads/contoh-manga-chapter-100",
    "total": 20,
    "downloaded": [
      {
        "index": 1,
        "url": "[https://cdn.example.com/contoh-manga/chapter-100/001.jpg](https://cdn.example.com/contoh-manga/chapter-100/001.jpg)",
        "path": "downloads/contoh-manga-chapter-100/001.jpg",
        "size": 135000
      }
    ]
  }
}
```

Progress download muncul pada terminal:

```text
[dl] 1/20
[dl] 2/20
[dl] 3/20
[dl] 20/20
```

Jika satu gambar gagal didownload, proses tetap berlanjut ke gambar berikutnya. Informasi error akan dicatat pada array `downloaded`.

Contoh data error download:

```json
{
  "index": 5,
  "url": "[https://cdn.example.com/contoh-manga/chapter-100/005.jpg](https://cdn.example.com/contoh-manga/chapter-100/005.jpg)",
  "error": "Request failed with status code 403"
}
```

---

## 🧩 Penggunaan Sebagai Module

Agar scraper dapat dipakai pada file Node.js lain, ubah bagian paling bawah file `biddynamic.js`.

Ganti:

```js
main()
```

Menjadi:

```js
if (require.main === module) {
  main()
}

module.exports = {
  latest,
  search,
  detail,
  chapter,
  downloadChapter
}
```

Buat file baru bernama `app.js`:

```js
const {
  latest,
  search,
  detail,
  chapter,
  downloadChapter
} = require("./biddynamic")

async function main() {
  try {
    const latestManga = await latest()

    console.log(JSON.stringify(latestManga, null, 2))

    const searchResult = await search("one piece")

    console.log(JSON.stringify(searchResult, null, 2))

    const mangaDetail = await detail("/komik/contoh-manga/")

    console.log(JSON.stringify(mangaDetail, null, 2))

    const chapterData = await chapter("/baca/contoh-manga/1/")

    console.log(JSON.stringify(chapterData, null, 2))
  } catch (error) {
    console.error(error.message)
  }
}

main()
```

Jalankan file:

```bash
node app.js
```

---

## 📝 Mengubah Author Response

Source code awal menggunakan author `xvlovers`.

Ubah function `output` dari:

```js
function output(data) {
  console.log(JSON.stringify({
    author: "xvlovers",
    status: true,
    data
  }, null, 2))
}
```

Menjadi:

```js
function output(data) {
  console.log(JSON.stringify({
    author: "SCRIPETEREN",
    status: true,
    data
  }, null, 2))
}
```

Ubah function `fail` dari:

```js
function fail(msg) {
  console.log(JSON.stringify({
    author: "xvlovers",
    status: false,
    message: msg
  }, null, 2))

  process.exit(1)
}
```

Menjadi:

```js
function fail(msg) {
  console.log(JSON.stringify({
    author: "SCRIPETEREN",
    status: false,
    message: msg
  }, null, 2))

  process.exit(1)
}
```

---

## 🛡️ Error Handling

Script memiliki penanganan error dasar untuk kondisi berikut:

- Query pencarian kosong
- URL manga kosong
- URL chapter kosong
- Request gagal
- Halaman tidak ditemukan
- HTTP status error
- Command tidak tersedia
- Gagal mendownload salah satu gambar
- Folder output belum tersedia

Contoh error ketika search tanpa query:

```bash
node biddynamic.js search
```

Output:

```json
{
  "author": "SCRIPETEREN",
  "status": false,
  "message": "Usage: node biddynamic.js search <query>"
}
```

Contoh error ketika URL manga tidak ditemukan:

```json
{
  "author": "SCRIPETEREN",
  "status": false,
  "message": "HTTP 404 - [https://biddynamic.com/komik/contoh-manga/](https://biddynamic.com/komik/contoh-manga/)"
}
```

Contoh error command tidak tersedia:

```json
{
  "author": "SCRIPETEREN",
  "status": false,
  "message": "Usage: node biddynamic.js <latest|search|detail|chapter|download> <arg>"
}
```

---

## 📄 .gitignore

Buat file `.gitignore` dengan isi berikut:

```gitignore
node_modules/
.env
komiku-dl/
downloads/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.DS_Store
```

Folder hasil download seperti `komiku-dl/` dan `downloads/` disarankan masuk `.gitignore` agar gambar hasil download tidak ikut di-push ke repository GitHub.

---

## ⚠️ Catatan Penting

- Struktur HTML website Biddynamic dapat berubah kapan saja.
- Jika selector HTML berubah, scraper mungkin perlu diperbarui.
- Jangan menjalankan request dalam jumlah besar dalam waktu singkat.
- Gunakan delay, cache, queue, dan rate limit jika scraper dipakai untuk bot atau aplikasi publik.
- Command `download` dapat menggunakan bandwidth serta storage dalam jumlah besar.
- Pastikan storage cukup sebelum mendownload chapter dengan banyak halaman.
- Jangan mengunggah ulang atau mendistribusikan gambar tanpa izin pemegang hak cipta.
- Gunakan project ini untuk pembelajaran web scraping, parsing HTML, riset, dan pengolahan metadata.
- Patuhi ketentuan website sumber, hukum, serta hak cipta yang berlaku.

---

## 📜 License

Project ini menggunakan lisensi MIT.

Buat file `LICENSE`:

```text
MIT License

Copyright (c) 2026 SCRIPETEREN

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal in the Software
without restriction, including without limitation the rights to use, copy,
modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 👨‍💻 Creator

```text
SCRIPETEREN
```

```text
[https://github.com/SCRIPETEREN](https://github.com/SCRIPETEREN)
```

<p align="center">
  Made with ❤️ by <a href="https://github.com/SCRIPETEREN">SCRIPETEREN</a>
</p>