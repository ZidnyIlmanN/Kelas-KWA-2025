# Login Bender
Pada tantangan ketiga terkait topik injection, kita diberi tugas untuk masuk ke akun Bender. Prosesnya sebenarnya sama dengan langkah-langkah pada tantangan sebelumnya, yaitu mencari alamat email Bender terlebih dahulu lalu memanfaatkan SQL Injection pada input email untuk melewati halaman login.
## Referensi

Bypass Login → [YouTube Shorts](https://youtube.com/shorts/XSpDXLFdPZk?si=1gzAPip35bbrxQK8)

## Bukti Hasil

<img width="1919" height="363" alt="Screenshot 2025-09-09 174339" src="https://github.com/user-attachments/assets/3f64f643-a7a4-4449-bfcf-7bc22377d5cd" />

### Langkah-langkah

1. Pertama, temukan informasi akun milik **Bender** untuk mendapatkan email yang akan dipakai pada form login.
   <img width="1919" height="865" alt="Screenshot 2025-09-09 174233" src="https://github.com/user-attachments/assets/b6e1e307-5804-4496-a830-aae37ae161e1" />


2. Selanjutnya, gunakan teknik SQL Injection dengan payload `bender@juice-sh.op'--` agar query selalu bernilai benar sehingga sistem melewati validasi login.
   <img width="1919" height="863" alt="Screenshot 2025-09-09 174318" src="https://github.com/user-attachments/assets/45fa632c-539d-48b1-8462-621d87d3091c" />

### Catatan

* Login berhasil dibypass → akses sebagai **Bender** tercapai 
