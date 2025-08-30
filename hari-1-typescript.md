# Hari 1: Pengenalan TypeScript untuk Web Development

## Apa itu TypeScript?

- **TypeScript** adalah bahasa pemrograman open-source yang merupakan _superset_ dari JavaScript.
- TypeScript menambahkan fitur **static typing** dan berbagai fitur OOP (Object Oriented Programming) pada JavaScript.
- Kode TypeScript dikompilasi (_transpile_) menjadi JavaScript agar bisa dijalankan di browser/web.

## Kenapa Menggunakan TypeScript?
- Membantu menemukan bug lebih awal (saat proses coding, bukan setelah dijalankan di browser).
- Kode lebih mudah dibaca dan dirawat, terutama untuk project besar.
- Mendukung fitur modern JavaScript + fitur tambahan (interface, tipe data custom, dsb).

---

## Instalasi TypeScript dan Node.js

### 1. Install Node.js
- Download dari https://nodejs.org/
- Pastikan sudah terinstall dengan mengetik di terminal:
  ```bash
  node -v
  npm -v
  ```

### 2. Install TypeScript
- Setelah Node.js terpasang, install TypeScript secara global:
  ```bash
  npm install -g typescript
  ```
- Cek versi TypeScript:
  ```bash
  tsc -v
  ```

---

## Menulis Program TypeScript Pertama

### 1. Buat file baru bernama `hello.ts`:

```typescript
let username: string = "Dunia";
console.log("Hello, " + username + "!");
```

### 2. Compile TypeScript ke JavaScript:
```bash
tsc hello.ts
```
- Akan menghasilkan file `hello.js`.

### 3. Jalankan file JavaScript-nya:
```bash
node hello.js
```
- Output: `Hello, Dunia!`

---

## Penjelasan Kode

- `let username: string = "Dunia";`  
  Mendefinisikan variabel `username` bertipe string, dan memberi nilai awal "Dunia".
- `console.log("Hello, " + username + "!");`  
  Menampilkan pesan pada console.

---

## Tugas Hari Ini

1. Install Node.js dan TypeScript.
2. Coba buat file `hello.ts` dan jalankan sesuai langkah-langkah di atas.
3. Ubah variabel `username` menjadi nama kamu sendiri dan ulangi compile + run.

---

**Lanjutkan ke Hari 2: Memahami Tipe Data Dasar di TypeScript.**
