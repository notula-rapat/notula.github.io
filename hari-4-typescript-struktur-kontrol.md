# Hari 4: Struktur Kontrol (if, else, switch, for, while, do while) di TypeScript

## Tujuan
- Memahami struktur kontrol alur program di TypeScript
- Mampu menggunakan percabangan dan perulangan dalam kode

---

## 1. Percabangan: if, else, else if

```typescript
let nilai: number = 75;

if (nilai >= 80) {
  console.log("Nilai A");
} else if (nilai >= 70) {
  console.log("Nilai B");
} else {
  console.log("Nilai C");
}
// Output: Nilai B
```

---

## 2. Switch Case

```typescript
let hari: string = "Senin";

switch (hari) {
  case "Senin":
    console.log("Hari kerja");
    break;
  case "Sabtu":
  case "Minggu":
    console.log("Akhir pekan");
    break;
  default:
    console.log("Hari tidak valid");
}
```

---

## 3. Perulangan: for

```typescript
for (let i = 1; i <= 5; i++) {
  console.log("Iterasi ke-" + i);
}
```

---

## 4. Perulangan: while & do while

```typescript
let count: number = 1;
while (count <= 3) {
  console.log("Count: " + count);
  count++;
}

let angka: number = 1;
do {
  console.log("Angka: " + angka);
  angka++;
} while (angka <= 3);
```

---

## 5. For...of dan For...in

- **for...of** untuk iterasi nilai pada array
- **for...in** untuk iterasi key pada object/array

```typescript
let hobi: string[] = ["ngoding", "makan", "tidur"];

for (let h of hobi) {
  console.log(h); // ngoding, makan, tidur
}

let user = { nama: "Andi", umur: 22 };
for (let k in user) {
  // k adalah key: "nama", "umur"
  console.log(k + ": " + user[k as keyof typeof user]);
}
```

---

## 6. Tugas

1. Buat file baru bernama `kontrol.ts`
2. Buat kode untuk:
   - Pengecekan nilai dan tampilkan grade (A/B/C)
   - Loop untuk menampilkan bilangan genap dari 1-10
   - Switch case untuk menentukan hari kerja/akhir pekan
3. Compile dan jalankan hasilnya.

---

## Contoh Kode

```typescript
for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    console.log(i + " adalah genap");
  }
}
```

---

**Lanjutkan ke Hari 5: Object & Interface di TypeScript.**
