# Hari 2: Memahami Tipe Data Dasar di TypeScript

## Tujuan
- Memahami tipe data dasar di TypeScript
- Menulis variabel dengan tipe data yang benar
- Menghindari error umum terkait tipe data

---

## 1. Tipe Data Dasar

### a. Number
```typescript
let umur: number = 25;
let harga: number = 10000.5;
```

### b. String
```typescript
let nama: string = "Andi";
let alamat: string = 'Jakarta';
```

### c. Boolean
```typescript
let sudahBayar: boolean = true;
let aktif: boolean = false;
```

### d. Array
```typescript
let angka: number[] = [1, 2, 3, 4];
let namaSiswa: string[] = ["Andi", "Budi", "Cici"];
```

### e. Tuple
> Array dengan jumlah dan tipe data tetap
```typescript
let biodata: [string, number];
biodata = ["Andi", 20]; // string di index 0, number di index 1
```

### f. Enum
> Untuk membuat sekumpulan nilai tetap
```typescript
enum Status {
  Aktif,
  TidakAktif,
  Cuti
}
let statusPegawai: Status = Status.Aktif;
```

---

## 2. Deklarasi Variabel: let, const, var

- **let**: variabel yang nilainya bisa diubah
- **const**: variabel konstan, tidak bisa diubah setelah diisi
- **var**: mirip let, tapi sebaiknya hindari (scope berbeda)

```typescript
let umur: number = 25;
umur = 26; // boleh

const pi: number = 3.14;
// pi = 3.15; // error!

var nama: string = "Andi";
```

---

## 3. Inference & Any

- **Type inference**: TypeScript bisa menebak tipe data jika sudah jelas
```typescript
let kota = "Bandung"; // otomatis string
// kota = 123; // error
```

- **Any**: tipe data bebas (hindari kecuali terpaksa)
```typescript
let random: any = "Halo";
random = 123;
random = true;
```

---

## 4. Praktik & Tugas

1. Buat file bernama `tipedata.ts`
2. Deklarasikan variabel dengan semua tipe data di atas (number, string, boolean, array, tuple, enum)
3. Coba ubah nilai variabel dan compile dengan `tsc tipedata.ts`
4. Perhatikan error jika tipe tidak cocok

---

## Contoh Kode

```typescript
let nama: string = "Dewi";
let umur: number = 22;
let aktif: boolean = true;
let hobi: string[] = ["membaca", "berenang"];
let posisi: [string, number] = ["Bekasi", 5];

enum Kelas { A, B, C }
let kelasSaya: Kelas = Kelas.B;

console.log(nama, umur, aktif, hobi, posisi, kelasSaya);
```

---

**Lanjutkan ke Hari 3: Fungsi, Parameter, dan Return Type di TypeScript.**
