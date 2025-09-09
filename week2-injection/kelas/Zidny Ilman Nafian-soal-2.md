# Login Jim
Pada challenge kedua terkait topik injection, tugasnya adalah melakukan login ke akun milik Jim. Konsepnya mirip dengan proses saat kita mencoba masuk sebagai admin, hanya saja kali ini kita perlu mengetahui alamat email Jim terlebih dahulu agar bisa dimasukkan ke dalam query yang digunakan untuk melewati halaman login.
## Referensi

Bypass Login → [YouTube Shorts](https://youtube.com/shorts/LT4JZrtrazM?si=ZiliDvZT-KVUzDU2)

## Bukti Pengerjaan

<img width="1919" height="358" alt="Screenshot 2025-09-09 172910" src="https://github.com/user-attachments/assets/749b309a-fd9e-4d43-a347-343ca1e641d0" />

### Langkah-langkah

1. Pertama, cari tahu informasi akun dengan meninjau data milik **Jim**.
   <img width="1919" height="862" alt="Screenshot 2025-09-09 172547" src="https://github.com/user-attachments/assets/eb1d11bb-4d71-4ced-8125-c4a87f71911a" />

2. Setelah itu, gunakan payload SQL Injection `' OR 1=1--` untuk memaksa query bernilai true, sehingga proses autentikasi dapat dilewati.
   <img width="1919" height="864" alt="Screenshot 2025-09-09 172818" src="https://github.com/user-attachments/assets/3d3832f7-af2e-46ee-9add-843c0c8b850b" />

### Catatan

* Berhasil masuk ke sistem dengan akun Jim 

