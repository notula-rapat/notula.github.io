# Hari 9: Event Handling & Membuat Form dengan Validasi di TypeScript

## Tujuan
- Memahami cara menangani berbagai event pada web dengan TypeScript
- Membuat form input sederhana dengan validasi

---

## 1. Contoh Struktur HTML Form

```html
<!-- index.html -->
<form id="formUser">
  <label for="nama">Nama:</label>
  <input type="text" id="nama" name="nama" required>
  <br>
  <label for="umur">Umur:</label>
  <input type="number" id="umur" name="umur" required>
  <br>
  <button type="submit">Kirim</button>
</form>
<div id="hasil"></div>
<script src="main.js"></script>
```

---

## 2. Menangani Event Submit pada Form

```typescript
// main.ts
const form = document.getElementById("formUser") as HTMLFormElement;
const inputNama = document.getElementById("nama") as HTMLInputElement;
const inputUmur = document.getElementById("umur") as HTMLInputElement;
const hasil = document.getElementById("hasil") as HTMLDivElement;

form.addEventListener("submit", (event) => {
  event.preventDefault(); // mencegah form reload halaman

  // Validasi manual
  if (inputNama.value.trim() === "") {
    alert("Nama wajib diisi!");
    return;
  }
  if (parseInt(inputUmur.value) < 1) {
    alert("Umur harus lebih dari 0!");
    return;
  }

  hasil.innerHTML = `Halo, ${inputNama.value}! Umur kamu: ${inputUmur.value} tahun.`;
});
```

---

## 3. Event Lain yang Sering Dipakai

- `input` → saat user mengetik di input.
- `change` → saat nilai input berubah dan kehilangan fokus.
- `focus` / `blur` → saat input mendapat/kehilangan fokus.

```typescript
inputNama.addEventListener("focus", () => {
  inputNama.style.backgroundColor = "#e0f7fa";
});
inputNama.addEventListener("blur", () => {
  inputNama.style.backgroundColor = "";
});
```

---

## 4. Validasi Lebih Lanjut

- Cek panjang karakter, karakter khusus, dsb.
- Tampilkan error di elemen HTML, bukan hanya `alert`.

```typescript
const errorNama = document.createElement("div");
errorNama.style.color = "red";
form.insertBefore(errorNama, inputNama.nextSibling);

inputNama.addEventListener("input", () => {
  if (inputNama.value.length < 3) {
    errorNama.textContent = "Nama minimal 3 karakter.";
  } else {
    errorNama.textContent = "";
  }
});
```

---

## 5. Tugas

1. Buat form input nama dan umur seperti contoh di atas.
2. Tambahkan validasi:
   - Nama minimal 3 karakter, umur minimal 1 dan maksimal 120.
   - Tampilkan pesan error di bawah input, bukan pakai alert.
3. Setelah submit sukses, tampilkan pesan hasil di bawah form.

---

## Contoh Kode Lengkap

```typescript
const form = document.getElementById("formUser") as HTMLFormElement;
const inputNama = document.getElementById("nama") as HTMLInputElement;
const inputUmur = document.getElementById("umur") as HTMLInputElement;
const hasil = document.getElementById("hasil") as HTMLDivElement;

const errorNama = document.createElement("div");
const errorUmur = document.createElement("div");
errorNama.style.color = "red";
errorUmur.style.color = "red";
inputNama.after(errorNama);
inputUmur.after(errorUmur);

form.addEventListener("submit", (event) => {
  event.preventDefault();

  let valid = true;
  if (inputNama.value.trim().length < 3) {
    errorNama.textContent = "Nama minimal 3 karakter.";
    valid = false;
  } else {
    errorNama.textContent = "";
  }
  const umurValue = Number(inputUmur.value);
  if (umurValue < 1 || umurValue > 120) {
    errorUmur.textContent = "Umur harus antara 1 - 120.";
    valid = false;
  } else {
    errorUmur.textContent = "";
  }

  if (!valid) return;

  hasil.innerHTML = `Selamat datang, <b>${inputNama.value}</b>! Umur kamu: <b>${inputUmur.value}</b> tahun.`;
  form.reset();
});
```

---

**Lanjutkan ke Hari 10: Manipulasi Array & Object (map, filter, reduce, dll) di TypeScript.**
