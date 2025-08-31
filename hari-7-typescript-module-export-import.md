# Hari 7: Module & Export/Import di TypeScript

## Tujuan
- Memahami konsep module di TypeScript
- Mampu membagi kode ke beberapa file dan menghubungkannya dengan `export` dan `import`

---

## 1. Apa itu Module?

Module adalah file terpisah yang berisi kode (variabel, fungsi, class, dsb) yang dapat digunakan di file lain dengan cara di-*import*.

---

## 2. Contoh Module Sederhana

### a. Membuat File Module

```typescript
// file: mathUtils.ts
export function tambah(a: number, b: number): number {
  return a + b;
}

export const PI = 3.14;
```

### b. Import di File Lain

```typescript
// file: app.ts
import { tambah, PI } from "./mathUtils";

console.log(tambah(2, 3)); // Output: 5
console.log("Nilai PI:", PI);
```

---

## 3. Export Default

```typescript
// file: sapa.ts
export default function sapa(nama: string): void {
  console.log(`Halo, ${nama}!`);
}
```

```typescript
// file: main.ts
import sapa from "./sapa";

sapa("Andi"); // Output: Halo, Andi!
```

---

## 4. Compile Project dengan Banyak File

- Gunakan `tsc --init` untuk membuat file `tsconfig.json` (sekali saja di root project).
- Compile semua file sekaligus:
  ```
  tsc
  ```
- Pastikan semua file `.ts` dalam folder yang sama atau atur di `tsconfig.json`.

---

## 5. Tips Penamaan & Struktur Folder

- Simpan file module di folder `src/` atau `modules/` agar rapi.
- Gunakan nama file/camelCase sesuai isi module.

```
src/
 |- mathUtils.ts
 |- sapa.ts
 |- main.ts
```

---

## 6. Tugas

1. Buat file `mathUtils.ts` yang berisi fungsi `tambah`, `kurang`, dan konstanta `PI`.
2. Buat file `app.ts`, import semua dari `mathUtils.ts` dan gunakan di dalam kode.
3. Compile dan jalankan hasilnya.
4. Buat satu module dengan `export default` dan import di file lain.

---

## Contoh Kode

```typescript
// mathUtils.ts
export function tambah(a: number, b: number): number {
  return a + b;
}
export function kurang(a: number, b: number): number {
  return a - b;
}
export const PI = 3.14;
```

```typescript
// app.ts
import { tambah, kurang, PI } from "./mathUtils";

console.log(tambah(10, 2)); // 12
console.log(kurang(10, 2)); // 8
console.log(PI);
```

---

**Tahap Basic Selesai!  
Selanjutnya, kamu siap masuk ke pemrograman web dengan TypeScript:  
Hari 8 - Manipulasi DOM & Web dengan TypeScript.**
