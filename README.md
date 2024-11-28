# MERN FUNDAMENTAL#1

## Gambaran Umum

Proyek ini terdiri dari dua komponen utama:

1. **Frontend**: Aplikasi React untuk antarmuka pengguna.

2. **Backend**: Aplikasi Node.js dan Express untuk menangani logika sisi server dan berinteraksi dengan basis data.

---

## Struktur Proyek

---

## Petunjuk Penyiapan

### 1. Buat Folder Proyek
Jalankan perintah berikut di terminal Anda untuk menyiapkan struktur proyek:
```bash
mkdir mern-fundamental
cd mern-fundamental
npx create-react-app client

### 2. Buat Proyek React (Klien)
npx create-react-app client

### 3. Buat Proyek Node/Express (Server)
mkdir server
cd server
npm init -y

---

## Penyiapan Backend (Server)

### 1. Instal Express
cd server
npm install express

### 2. Buat File index.js
Buat file bernama index.js di folder server dan tambahkan kode berikut:

const express = require('express');
const app = express(); const cors = require('cors');

app.use(cors());

app.get('/', (req, res) => {
res.send('Halo dari server kami!');
});

app.listen(8080, () => {
console.log('server mendengarkan pada port 8080');
});

### 3. Jalankan Server
Jalankan perintah berikut di direktori server:

node index.js

---

## Pengaturan Frontend (Klien)

### 1. Instal Axios
Di direktori klien, jalankan:

npm install axios

### 2. Perbarui Berkas App.js
Ganti konten bawaan App.js dengan:

import axios from 'axios';
import './App.css';

const apiCall = () => {
axios.get('http://localhost:8080').then((data) => {
console.log(data);
});
};

function App() {
return (
<div className="App">
<header className="App-header">
<button onClick={apiCall}>Make API Call</button>
</header>
</div>
);
}

export default App;

### 3. Jalankan Aplikasi React
Jalankan perintah berikut di direktori klien:

npm start

---

## Konfigurasi CORS
Untuk menghindari kesalahan CORS, kami menggunakan paket cors di backend kami. Instal dengan menjalankan:

cd server
npm install cors

Perbarui berkas index.js untuk menyertakan:

const cors = require('cors');

app.use(cors());

---

## Menguji Aplikasi
Jalankan server:

cd server
node index.js

Jalankan aplikasi React:

cd client
npm start

Buka aplikasi React di peramban Anda, klik tombol Make API Call, dan periksa konsol untuk respons dari server.
