# 🚀 Proyek Otomasi Tes API: Manajemen User

Sebuah proyek demonstrasi untuk mengotomatiskan pengujian API (CRUD) menggunakan Postman, Newman, dan diintegrasikan dengan pipeline CI/CD menggunakan GitHub Actions.

## 🎯 Deskripsi Singkat

Proyek ini mensimulasikan alur kerja seorang QA Automation Engineer dalam menguji fungsionalitas inti dari sebuah API. Tujuannya adalah untuk memastikan bahwa semua operasi **CRUD (Create, Read, Update, Delete)** untuk manajemen data pengguna berjalan sesuai harapan. Rangkaian tes ini dijalankan secara otomatis setiap kali ada perubahan pada repositori untuk memastikan kualitas kode tetap terjaga.

---

## 🛠️ Teknologi yang Digunakan

- **Pengujian API:** Postman
- **CLI Runner:** Newman
- **Runtime:** Node.js
- **CI/CD:** GitHub Actions
- **Version Control:** Git & GitHub

---

## 🔬 Fitur & Skenario yang Diuji

Koleksi Postman ini mencakup pengujian untuk 4 endpoint utama dengan skenario positif dan negatif:

1.  **CREATE User (`POST /api/users`)**

    - ✅ Memastikan user baru berhasil dibuat dengan data yang valid (Assertions: Status Code 201, Body Respons berisi nama yang dikirim).

2.  **READ User (`GET /api/users/{{userId}}`)**

    - ✅ Memastikan data user bisa diambil dengan benar (Assertions: Status Code 200).
    - ❌ Memastikan sistem memberikan respons 404 jika user ID tidak ditemukan.

3.  **UPDATE User (`PUT /api/users/{{userId}}`)**

    - ✅ Memastikan data user berhasil diubah (Assertions: Status Code 200, Body Respons berisi data yang sudah di-update).

4.  **DELETE User (`DELETE /api/users/{{userId}}`)**
    - ✅ Memastikan user berhasil dihapus (Assertions: Status Code 204).

---

## ⚙️ Cara Menjalankan Proyek Secara Lokal

1.  **Prasyarat:** Pastikan Anda sudah menginstal [Node.js](https://nodejs.org/) dan [Git](https://git-scm.com/).
2.  **Clone Repositori:**
    ```bash
    git clone [https://github.com/pawpaaaww/my-api-test-pipeline.git](https://github.com/pawpaaaww/my-api-test-pipeline.git)
    cd my-api-test-pipeline
    ```
3.  **Install Newman:**
    ```bash
    npm install -g newman
    ```
4.  **Jalankan Tes:**
    ```bash
    newman run "APITest.postman_collection.json"
    ```

---

## 📈 Contoh Hasil Laporan Newman

Berikut adalah contoh output ketika tes dijalankan melalui Newman di terminal:
newman

USER - MANAGEMENT

→ https://reqres.in/api/users(https://reqres.in/api/users)
GET https://reqres.in/api/users [200 OK, 2.46kB, 567ms]
✓ Status code is 200

→ https://reqres.in/api/users(https://reqres.in/api/users)
POST https://reqres.in/api/users [201 Created, 1.42kB, 395ms]
✓ Status code is 201
✓ Response body should contain the correct name

→ https://reqres.in/api/users/{{userId}}(https://reqres.in/api/users/{{userId}})
PUT https://reqres.in/api/users/441 [200 OK, 1.46kB, 442ms]
✓ Status code is 200
✓ Job title should be updated

→ https://reqres.in/api/users/{{userId}}(https://reqres.in/api/users/{{userId}})
DELETE https://reqres.in/api/users/441 [204 No Content, 1.27kB, 408ms]
✓ Status should be 204

┌─────────────────────────┬────────────────────┬────────────────────┐
│ │ executed │ failed │
├─────────────────────────┼────────────────────┼────────────────────┤
│ iterations │ 1 │ 0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│ requests │ 4 │ 0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│ test-scripts │ 4 │ 0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│ prerequest-scripts │ 0 │ 0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│ assertions │ 6 │ 0 │
├─────────────────────────┴────────────────────┴────────────────────┤
│ total run duration: 1903ms │
├───────────────────────────────────────────────────────────────────┤
│ total data received: 1.22kB (approx) │
├───────────────────────────────────────────────────────────────────┤
│ average response time: 453ms [min: 395ms, max: 567ms, s.d.: 68ms] │
└───────────────────────────────────────────────────────────────────┘
