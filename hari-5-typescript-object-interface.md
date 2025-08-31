# Hari 5: Object & Interface di TypeScript

## Tujuan
- Memahami cara membuat dan menggunakan object di TypeScript
- Mengenal dan menerapkan interface untuk struktur data yang konsisten

---

## 1. Object di TypeScript

Objek adalah kumpulan properti yang memiliki nama (key) dan nilai (value).

```typescript
let pegawai = {
  nama: "Andi",
  umur: 30,
  aktif: true
};

console.log(pegawai.nama); // Output: Andi
```

---

## 2. Interface: Struktur Data yang Konsisten

Interface digunakan untuk mendefinisikan "bentuk" dari sebuah object.

```typescript
interface Pegawai {
  nama: string;
  umur: number;
  aktif: boolean;
}

let pegawai1: Pegawai = {
  nama: "Budi",
  umur: 28,
  aktif: false
};
```
- Objek `pegawai1` wajib mengikuti struktur dan tipe pada interface `Pegawai`.

---

## 3. Optional Property pada Interface

Gunakan tanda tanya (?) untuk properti yang boleh diisi atau tidak.

```typescript
interface Mahasiswa {
  nama: string;
  jurusan?: string; // opsional
}

let mhs1: Mahasiswa = { nama: "Cici" };
let mhs2: Mahasiswa = { nama: "Dewi", jurusan: "Teknik Informatika" };
```

---

## 4. Array of Object dengan Interface

```typescript
interface Produk {
  nama: string;
  harga: number;
}
let daftarProduk: Produk[] = [
  { nama: "Buku", harga: 12000 },
  { nama: "Pulpen", harga: 3000 },
];
```

---

## 5. Interface pada Parameter Fungsi

```typescript
interface User {
  username: string;
  email: string;
}

function cetakUser(user: User): void {
  console.log(`User: ${user.username}, Email: ${user.email}`);
}

cetakUser({ username: "andi123", email: "andi@mail.com" });
```

---

## 6. Tugas

1. Buat file bernama `object-interface.ts`
2. Buat interface untuk `Siswa` dengan properti `nama`, `umur`, dan `nilai?`.
3. Buat array data siswa dan fungsi untuk menampilkan semua data siswa.
4. Compile dan jalankan hasilnya.

---

## Contoh Kode

```typescript
interface Siswa {
  nama: string;
  umur: number;
  nilai?: number;
}

let siswaList: Siswa[] = [
  { nama: "Rina", umur: 17, nilai: 95 },
  { nama: "Bima", umur: 16 }
];

function tampilkanSiswa(list: Siswa[]): void {
  for (let s of list) {
    console.log(`${s.nama} (${s.umur} tahun)`, s.nilai ? `Nilai: ${s.nilai}` : "");
  }
}

tampilkanSiswa(siswaList);
```

---

**Lanjutkan ke Hari 6: Class, Inheritance, dan Access Modifier di TypeScript.**
