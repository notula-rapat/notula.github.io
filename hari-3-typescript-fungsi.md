# Hari 3: Fungsi, Parameter, dan Return Type di TypeScript

## Tujuan
- Memahami cara mendefinisikan dan memanggil fungsi di TypeScript
- Mengenal parameter, default value, dan tipe data parameter
- Mengenal return type pada fungsi

---

## 1. Dasar Fungsi di TypeScript

```typescript
function sapa(nama: string): void {
  console.log("Halo, " + nama);
}

sapa("Andi"); // Output: Halo, Andi
```
- `function` untuk mendeklarasikan fungsi.
- `(nama: string)` berarti parameter `nama` harus berupa string.
- `: void` artinya fungsi tidak mengembalikan nilai.

---

## 2. Fungsi dengan Return Value

```typescript
function tambah(a: number, b: number): number {
  return a + b;
}

let hasil = tambah(2, 3);
console.log(hasil); // Output: 5
```
- `: number` di belakang tanda kurung menunjukkan tipe data hasil return.

---

## 3. Parameter Optional & Default

```typescript
function sapaUser(nama: string, sapaan: string = "Halo"): void {
  console.log(sapaan + ", " + nama);
}

sapaUser("Budi"); // Output: Halo, Budi
sapaUser("Cici", "Selamat pagi"); // Output: Selamat pagi, Cici
```
- Parameter `sapaan` punya nilai default "Halo".

---

## 4. Fungsi dengan Parameter Optional

```typescript
function info(nama: string, umur?: number): string {
  if (umur) {
    return `${nama} berumur ${umur} tahun.`;
  } else {
    return `${nama} belum diketahui umurnya.`;
  }
}

console.log(info("Dewi")); // Dewi belum diketahui umurnya.
console.log(info("Dewi", 20)); // Dewi berumur 20 tahun.
```
- Parameter dengan tanda tanya (`umur?`) artinya boleh diisi atau tidak.

---

## 5. Arrow Function

```typescript
const kali = (a: number, b: number): number => {
  return a * b;
}

console.log(kali(2, 5)); // Output: 10
```
- Arrow function adalah bentuk singkat fungsi, banyak dipakai di project modern.

---

## 6. Tugas

1. Buat file baru bernama `fungsi.ts`
2. Buat minimal 3 fungsi:
   - Fungsi tanpa return value (void)
   - Fungsi dengan return value
   - Fungsi dengan parameter default / optional
3. Compile dan jalankan hasilnya.

---

## Contoh Kode

```typescript
function perkenalan(nama: string, asal: string = "Indonesia"): void {
  console.log(`Nama saya ${nama} dari ${asal}`);
}

const kurang = (a: number, b: number): number => {
  return a - b;
}

function cekGenap(angka: number): boolean {
  return angka % 2 === 0;
}

perkenalan("Rina", "Bandung");
console.log(kurang(10, 2));
console.log(cekGenap(7));
```

---

**Lanjutkan ke Hari 4: Struktur Kontrol (if, else, switch, for, while, do while) di TypeScript.**
