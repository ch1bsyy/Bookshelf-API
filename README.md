# 📚 Bookshelf API
Bookshelf API adalah backend RESTful API untuk mengelola koleksi buku. API ini menyediakan fitur untuk menambahkan, membaca, mengedit, dan menghapus data buku dengan implementasi kode yang sesuai standar.

## 🌟 Fitur Utama

### 📌 Endpoints
__1. Menambahkan Buku__
- __Method:__ `POST`
- __Path:__ `/books`
- __Deskripsi:__ Menambahkan buku baru ke dalam koleksi.
- __Payload:__ <br>
{ <br>
  "name": "string", <br>
  "year": "number", <br>
  "author": "string", <br>
  "summary": "string", <br>
  "publisher": "string", <br>
  "pageCount": "number", <br>
  "readPage": "number", <br>
  "reading": "boolean" <br>
} <br>
- __Response:__ <br>
  - `201`: Buku berhasil ditambahkan.
  - `400`: Gagal menambahkan buku. Mohon isi nama buku.
  - `400`: Gagal menambahkan buku. readPage tidak boleh lebih besar dari pageCount.
  - `500`: Buku gagal ditambahkan. <br><br>

__2. Mendapatkan Semua Buku__
- __Method:__ `GET`
- __Path:__ `/books`
- __Deskripsi:__ Mengambil daftar seluruh buku yang tersedia.
- __Response:__ <br>
  - `200`: Daftar buku berhasil diambil. <br><br>

__3. Mendapatkan Buku Berdasarkan ID__
- __Method:__ `GET`
- __Path:__ `/books/{bookId}`
- __Deskripsi:__ Mengambil detail buku berdasarkan bookId.
- __Response:__
  - `200`: Detail buku berhasil diambil.
  - `404`: Buku tidak ditemukan. <br><br>

__4. Mengubah Buku Berdasarkan ID__
- __Method:__ `PUT`
- __Path:__ `/books/{bookId}`
- __Deskripsi:__ Mengubah detail buku berdasarkan bookId.
- __Payload:__ Sama seperti saat menambahkan buku.
- __Response:__
  - `200`: Buku berhasil diperbarui.
  - `400`: Gagal memperbarui buku. Mohon isi nama buku.
  - `400`: Gagal memperbarui buku. readPage tidak boleh lebih besar dari pageCount.
  - `404`: Gagal memperbarui buku. Id tidak ditemukan. <br><br>

__5. Menghapus Buku Berdasarkan ID__
- __Method:__ `DELETE`
- __Path:__ `/books/{bookId}`
- __Deskripsi:__ Menghapus buku berdasarkan bookId.
- __Response:__
  - `200`: Buku berhasil dihapus.
  - `404`: Buku gagal dihapus. Id tidak ditemukan.

## 📚 Struktur Data Buku
Setiap buku memiliki struktur data berikut: <br>
{ <br>
  "id": "string", <br>
  "name": "string", <br>
  "year": "number", <br>
  "author": "string", <br>
  "summary": "string", <br>
  "publisher": "string", <br>
  "pageCount": "number", <br>
  "readPage": "number", <br>
  "reading": "boolean", <br>
  "finished": "boolean", <br>
  "insertedAt": "string", <br>
  "updatedAt": "string" <br>
} <br> <br>
- `finished`: Otomatis bernilai `true` jika `readPage === pageCount`.
- `insertedAt` __dan__ `updatedAt`: Menyimpan waktu penambahan atau pembaruan data buku.

## ⚙️ Teknologi yang Digunakan
- __Hapi.js:__ Framework backend untuk membangun server API.
- __Nanoid:__ Digunakan untuk menghasilkan ID buku yang unik.
- __Nodemon:__ Untuk memonitor perubahan pada kode selama pengembangan.
- __ESLint:__ Menjaga kualitas dan konsistensi kode.
- __Postman:__ Alat pengujian endpoint API.

## 🛠️ Pengujian API
- __Postman Collection:__ Tersedia dalam proyek untuk mempermudah pengujian semua endpoint.
- __Postman Environment:__ Disediakan untuk mengelola variabel, seperti base URL, sehingga pengujian lebih efisien.

Terima kasih telah menggunakan __Bookshelf API!__ Jika Anda memiliki ide atau saran untuk pengembangan lebih lanjut, silakan buat __issue__ atau ajukan __pull request.__ 😊
