# Menjalankan KuRangkai dengan Gemini

## Lokal
1. Pasang Node.js 20 atau lebih baru.
2. Salin `.env.example` menjadi `.env`.
3. Buat API key di [Google AI Studio](https://aistudio.google.com/app/apikey), lalu isi `GEMINI_API_KEY` di `.env`. Jangan bagikan atau commit berkas `.env`.
4. Jalankan `npm start`, lalu buka http://localhost:3000.

## Alamat publik gratis lewat Render
1. Buat repository GitHub untuk aplikasi. Unggah isi folder ini saja; `.gitignore` mengecualikan `.env`.
2. Di Render, pilih **New → Web Service** dan hubungkan repository tersebut.
3. Isi **Root Directory** dengan `work/materi-ai` jika folder ini berada di dalam repo; jika isi folder ini menjadi root repo, biarkan kosong.
4. Isi **Build Command** `npm install` dan **Start Command** `npm start`.
5. Di **Environment**, tambahkan `GEMINI_API_KEY` dengan API key Anda sebagai secret. Jangan unggah `.env` ke GitHub.
6. Pilih Free untuk mencoba. Setelah deploy, Render memberi alamat `*.onrender.com`. Layanan gratis dapat tidur setelah 15 menit tanpa trafik dan perlu sekitar satu menit untuk aktif kembali.

Nama subdomain tepatnya bergantung pada ketersediaan. Domain sendiri dapat ditambahkan nanti melalui pengaturan Custom Domains Render; nama domain biasanya perlu dibeli terpisah.

Server mengirim teks/PDF ke Gemini API untuk membuat hasil. Kunci API hanya dibaca oleh server dan tidak dikirim ke browser. PDF diproses langsung oleh Gemini; batas lokal aplikasi 15 MB. Request API memakai `store: false`.
