# 📘 JavaScript Concepts Explained

Dokumentasi singkat berbagai konsep penting di JavaScript, mulai dari DOM event, manipulasi string dan array, hingga teknik pemrograman fungsional.

---

## 🌐 DOM & Events

### `window.onload`

Digunakan untuk menjalankan kode JavaScript setelah seluruh halaman (termasuk gambar, script, dsb) selesai dimuat.

```js
window.onload = function () {
  console.log("Halaman siap!");
};
```

### `onchange`

Event handler yang dijalankan saat **nilai input berubah** (terutama untuk input `<select>`, `<input>`, `<textarea>`).

```html
<input type="text" onchange="alert(this.value)" />
```

### `event.target`

Mengacu ke elemen DOM yang **memicu event**. Berguna saat menggunakan event handler umum.

```js
document.addEventListener("click", function (event) {
  console.log(event.target); // elemen yang diklik
});
```

---

## 🐡 String

### `charCodeAt(index)`

Mengembalikan **kode Unicode** dari karakter pada posisi tertentu.

```js
"A".charCodeAt(0); // 65
```

### `String.fromCharCode(code)`

Kebalikan dari `charCodeAt` — mengubah kode menjadi karakter.

```js
String.fromCharCode(65); // "A"
```

### `split(separator)`

Memecah string menjadi array berdasarkan **pemisah** tertentu.

```js
"aku,suka,kopi".split(","); // ["aku", "suka", "kopi"]
```

### `slice(start, end)`

Mengambil sebagian string/array dari indeks `start` sampai sebelum `end`.

```js
"javascript".slice(0, 4); // "java"
```

### `includes(value)`

Cek apakah string/array mengandung nilai tertentu.

```js
[1, 2, 3].includes(2); // true
"hello".includes("ell"); // true
```

---

## 🗑️ Array Methods

### `forEach()`

Melakukan sesuatu untuk **setiap elemen array**, tapi tidak mengembalikan nilai.

```js
[1, 2, 3].forEach((x) => console.log(x));
```

### `fill(value, start, end)`

Mengisi array dengan nilai tertentu, dari `start` sampai sebelum `end`.

```js
[1, 2, 3, 4].fill(0, 1, 3); // [1, 0, 0, 4]
```

### `splice(start, deleteCount, ...items)`

Mengubah isi array dengan **menghapus/mengganti/menambahkan** elemen.

```js
let arr = [1, 2, 3];
arr.splice(1, 1, 99); // [1, 99, 3]
```

### `sort()`

Mengurutkan array secara **default sebagai string**. Gunakan fungsi pembanding untuk angka.

```js
[3, 1, 2].sort(); // [1, 2, 3] sebagai string
[3, 1, 2].sort((a, b) => a - b); // numerik
```

### `some(callback)`

Cek apakah **minimal satu elemen** memenuhi kondisi.

```js
[1, 2, 3].some((x) => x > 2); // true
```

### `every(callback)`

Cek apakah **semua elemen** memenuhi kondisi.

```js
[1, 2, 3].every((x) => x > 0); // true
```

---

## 🧪 Math

### `Math.ceil(x)`

Membulatkan ke atas.

```js
Math.ceil(4.2); // 5
```

---

## ⚙️ Object

### `hasOwnProperty(key)`

Cek apakah properti tersebut **ada di objek itu sendiri**, bukan dari prototipe.

```js
const obj = { name: "Ayu" };
obj.hasOwnProperty("name"); // true
obj.hasOwnProperty("toString"); // false
```

---

## 🔧 Functional Concepts

### Currying

Teknik memecah fungsi banyak argumen menjadi fungsi bertingkat satu argumen.

```js
function multiply(a) {
  return function (b) {
    return a * b;
  };
}

const timesTwo = multiply(2);
console.log(timesTwo(5)); // 10
```

### Immediately Invoked Function Expression (IIFE)

Fungsi yang **langsung dipanggil setelah didefinisikan**.

```js
(function () {
  console.log("Langsung jalan!");
})();
```

### Function Reference vs Invocation

```js
function sayHi() {
  console.log("Hi");
}

const ref = sayHi; // 👈 function reference
ref(); // panggil

const call = sayHi(); // 👈 langsung dipanggil (hasilnya masuk ke `call`)
```

---
