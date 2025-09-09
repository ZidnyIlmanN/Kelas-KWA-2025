# Login Bender

## Referensi

Bypass Login → [YouTube Shorts]([https://youtube.com/shorts/LT4JZrtrazM?si=ZiliDvZT-KVUzDU2](https://youtube.com/shorts/XSpDXLFdPZk?si=1gzAPip35bbrxQK8))

## Hasil & Bukti

![login](<img width="440" height="202" alt="Screenshot 2025-09-09 170522" src="https://github.com/user-attachments/assets/ced1620b-3823-4f24-9b8c-52c4d7a197f2" />)

### Langkah Pengerjaan

![bender](<img width="1919" height="864" alt="Screenshot 2025-09-09 170620" src="https://github.com/user-attachments/assets/53e7f670-18a3-48c7-805a-45841ec21e49" />)

1. Dari soal diberikan instruksi untuk mencoba login dengan user `admin`.
   ![login](<img width="1919" height="863" alt="Screenshot 2025-09-09 170717" src="https://github.com/user-attachments/assets/3d9bd657-cb25-4bf0-b04d-07582f33a5ae" />)

2. Saat login menggunakan admin, muncul respon berupa nilai `[object]`. Ini mengindikasikan input tidak tervalidasi dengan baik. Dengan menyisipkan payload sederhana `' OR 1=1--` kita bisa memanipulasi query agar selalu bernilai true, sehingga login bisa dilewati.
   ![login](<img width="1919" height="869" alt="Screenshot 2025-09-09 170937" src="https://github.com/user-attachments/assets/9507cae2-69cf-44a7-b630-90bde74dac07" />)

3. Akhirnya proses login berhasil dilewati dan kita masuk dengan hak akses admin.
   <img width="1919" height="383" alt="Screenshot 2025-09-09 171015" src="https://github.com/user-attachments/assets/bfc8ea5c-bad6-4ad0-82b7-189901269728" />

* Login berhasil dibypass → akses sebagai Admin tercapai 
