# Hari 6: Class, Inheritance, dan Access Modifier di TypeScript

## Tujuan
- Memahami konsep class di TypeScript
- Mengenal inheritance (pewarisan)
- Menggunakan access modifier (public, private, protected)

---

## 1. Class di TypeScript

Class adalah cetakan untuk membuat object.

```typescript
class Pegawai {
  nama: string;
  umur: number;

  constructor(nama: string, umur: number) {
    this.nama = nama;
    this.umur = umur;
  }

  sapa(): void {
    console.log(`Halo, saya ${this.nama}, umur ${this.umur} tahun.`);
  }
}

let p1 = new Pegawai("Andi", 30);
p1.sapa(); // Output: Halo, saya Andi, umur 30 tahun.
```

---

## 2. Inheritance (Pewarisan)

Class bisa mewarisi properti dan method dari class lain dengan kata kunci `extends`.

```typescript
class Manager extends Pegawai {
  divisi: string;

  constructor(nama: string, umur: number, divisi: string) {
    super(nama, umur); // memanggil constructor class induk
    this.divisi = divisi;
  }

  infoManager(): void {
    console.log(`${this.nama} adalah manager divisi ${this.divisi}`);
  }
}

let m1 = new Manager("Budi", 35, "IT");
m1.sapa(); // dari class Pegawai
m1.infoManager(); // dari class Manager
```

---

## 3. Access Modifier

- **public**: Bisa diakses dari mana saja (default)
- **private**: Hanya bisa diakses dari dalam class itu sendiri
- **protected**: Bisa diakses dari class itu sendiri & turunannya

```typescript
class Produk {
  public nama: string;
  private harga: number;
  protected stok: number;

  constructor(nama: string, harga: number, stok: number) {
    this.nama = nama;
    this.harga = harga;
    this.stok = stok;
  }

  tampilHarga(): void {
    console.log(`Harga produk: ${this.harga}`);
  }
}

class Buku extends Produk {
  penulis: string;

  constructor(nama: string, harga: number, stok: number, penulis: string) {
    super(nama, harga, stok);
    this.penulis = penulis;
  }

  infoStok(): void {
    console.log(`Stok buku: ${this.stok}`); // boleh, karena protected
  }
}

let buku1 = new Buku("Belajar TS", 50000, 10, "Rina");
buku1.tampilHarga();
// buku1.harga; // error: private property
buku1.infoStok();
// buku1.stok; // error: protected property
```

---

## 4. Tugas

1. Buat file `class.ts`
2. Buat class `Mahasiswa` dengan properti `nama`, `nim`, dan method `perkenalan()`
3. Buat class `MahasiswaBaru` (extends `Mahasiswa`), tambah properti `tahunMasuk`
4. Implementasikan access modifier pada properti/method sesuai kebutuhan
5. Buat minimal 1 object dari masing-masing class, panggil semua methodnya

---

## Contoh Kode

```typescript
class Mahasiswa {
  protected nama: string;
  protected nim: string;

  constructor(nama: string, nim: string) {
    this.nama = nama;
    this.nim = nim;
  }

  perkenalan(): void {
    console.log(`Halo, saya ${this.nama} dengan NIM ${this.nim}.`);
  }
}

class MahasiswaBaru extends Mahasiswa {
  public tahunMasuk: number;

  constructor(nama: string, nim: string, tahunMasuk: number) {
    super(nama, nim);
    this.tahunMasuk = tahunMasuk;
  }

  info(): void {
    console.log(`${this.nama} masuk tahun ${this.tahunMasuk}`);
  }
}

let mhs = new MahasiswaBaru("Dewi", "123456", 2025);
mhs.perkenalan();
mhs.info();
```

---

**Lanjutkan ke Hari 7: Module & Export/Import di TypeScript.**
