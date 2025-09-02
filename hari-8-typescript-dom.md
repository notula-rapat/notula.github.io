# Hari 8: Manipulasi DOM & Web dengan TypeScript

## Tujuan
- Memahami cara menggunakan TypeScript untuk memanipulasi halaman web (DOM)
- Membuat interaksi sederhana antara user dan halaman web

---

## 1. Persiapan Project Sederhana

- Buat folder `web-ts/`
- Di dalamnya, buat file:
  - `index.html`
  - `main.ts`
- Pastikan kamu sudah meng-compile `main.ts` menjadi `main.js` dengan perintah `tsc main.ts`

---

## 2. Struktur Dasar HTML

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Belajar DOM dengan TypeScript</title>
</head>
<body>
  <h1 id="judul">Halo!</h1>
  <input type="text" id="inputNama" placeholder="Masukkan nama">
  <button id="btnGanti">Ganti Judul</button>
  <script src="main.js"></script>
</body>
</html>
```

---

## 3. Mengakses dan Memanipulasi DOM dengan TypeScript

```typescript
// main.ts
const judul = document.getElementById("judul") as HTMLHeadingElement;
const inputNama = document.getElementById("inputNama") as HTMLInputElement;
const btnGanti = document.getElementById("btnGanti") as HTMLButtonElement;

btnGanti.addEventListener("click", function() {
  judul.textContent = "Halo, " + inputNama.value + "!";
});
```
- Gunakan `as HTMLHeadingElement`, `as HTMLInputElement`, dst agar TypeScript tahu tipe elemennya.

---

## 4. Menangani Event

- Event umum: `click`, `change`, `input`, `submit`, dst
- Contoh event lain:
```typescript
inputNama.addEventListener("input", () => {
  if (inputNama.value.length > 10) {
    inputNama.style.borderColor = "red";
  } else {
    inputNama.style.borderColor = "";
  }
});
```

---

## 5. Validasi Sederhana

```typescript
btnGanti.addEventListener("click", () => {
  if (inputNama.value.trim() === "") {
    alert("Nama tidak boleh kosong!");
  } else {
    judul.textContent = "Halo, " + inputNama.value + "!";
  }
});
```

---

## 6. Tugas

1. Buat project seperti contoh di atas.
2. Tambahkan 1 tombol untuk mereset judul ke "Halo!".
3. Tambahkan validasi jika nama lebih dari 20 karakter, tampilkan alert.

---

## Contoh Kode Lengkap

```typescript
const judul = document.getElementById("judul") as HTMLHeadingElement;
const inputNama = document.getElementById("inputNama") as HTMLInputElement;
const btnGanti = document.getElementById("btnGanti") as HTMLButtonElement;

// Tambahkan tombol reset di HTML dan akses di sini jika sudah
const btnReset = document.createElement("button");
btnReset.textContent = "Reset Judul";
document.body.appendChild(btnReset);

btnGanti.addEventListener("click", () => {
  if (inputNama.value.trim() === "") {
    alert("Nama tidak boleh kosong!");
  } else if (inputNama.value.length > 20) {
    alert("Nama terlalu panjang (maks 20 karakter)!");
  } else {
    judul.textContent = "Halo, " + inputNama.value + "!";
  }
});

btnReset.addEventListener("click", () => {
  judul.textContent = "Halo!";
  inputNama.value = "";
});
```

---

**Lanjutkan ke Hari 9: Event Handling & Membuat Form dengan Validasi di TypeScript.**
