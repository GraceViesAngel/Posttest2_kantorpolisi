# Posttest2_kantorpolisi

Kantor polisi adalah lembaga layanan publik yang menjaga ketertiban, menegakkan hukum, dan melindungi masyarakat; untuk menertibkan alur kerja harian. nama sistem saya yaitu, aplikasi "Sistem Kantor Polisi" ini adalah program lanjutan Post Test 1 yang memusatkan pengelolaan Informasi Polisi, Jadwal Patroli, dan Kasus Penyelidikan melalui operasi CRUD yang dilengkapi validasi input (NRP wajib 3 digit dan unik, status terkontrol: Aktif/Cuti untuk personel; Dijadwalkan/Telah Selesai untuk jadwal; Baru/Proses/Ditutup untuk kasus; serta pengecekan bahwa NRP harus terdaftar saat membuat jadwal/kasus), menyediakan pencarian personel berdasarkan nama/pangkat dan filter jadwal per area/status serta kasus per status, menampilkan data dalam tabel konsol rapi dengan judul di tengah agar mudah dibaca saat demo, menomori otomatis entitas terjadwal dan kasus (J-1, J-2… / K-1, K-2…), menyimpan data sementara secara in-memory menggunakan List sama seperti post test 1 saya tetapi dimodif, dan ditata terstruktur dalam package data_kantorpolisi (model ber-atribut private + constructor + getter/setter), operasional_kantorpolisi (logika/CRUD, validasi, dan generator ID), serta menu_kantorpolisi (UI/entry point) sekaligus memenuhi seluruh ketentuan tugas (≥3 class, ≥3 atribut, constructor, access modifier, dan pemisahan package).



### (MASUK PROGRAM)
Secara tampilan dan fungsi, output program pada Post Test 2 sama seperti Post Test 1, saat dijalankan aplikasi menampilkan menu utama (Informasi Polisi, Jadwal Patroli, Kasus Penyelidikan), tiap menu membuka sub-menu CRUD, dan data dicetak dalam tabel konsol rapi (mis. NRP | Nama | Pangkat | Status), sehingga perilaku hasil di layar tidak berubah; perbedaannya ada pada arsitektur dan kualitas internal kode dipisah per package dan program lebih terstruktur .

![WhatsApp Image 2025-09-13 at 19 19 29_b5e7d7e1](https://github.com/user-attachments/assets/71a1afd0-6f99-45d7-99dc-fbf46c521fda)
=> PENJELASAN
Saat dijalankan, 'AplikasiKantorPolisi' membuat data contoh (seed), lalu menampilkan **Menu Utama** berisi tiga yaitu: **Informasi Polisi**, **Jadwal Patroli**, dan **Kasus Penyelidikan**. saya memilih menu, kemudian di sub-menu menjalankan **CRUD** (tambah, lihat tabel, ubah, hapus) serta fitur **cari/filter** sesuai modul; setiap input dicek validasinya (NRP 3 digit unik, status hanya nilai yang diizinkan, dan NRP harus terdaftar saat membuat jadwal/kasus). Setelah sebuah aksi selesai, aplikasi kembali ke sub-menu; jika memilih **Kembali**, pengguna balik ke Menu Utama. Seluruh data selalu ditampilkan dalam **tabel yang rapi** dengan judul di tengah. Bila saya memilih **Keluar**, program menutup dengan aman.



### MENGETIK ANGKA 1 (Informasi Polisi) dan 1 (Tambah data Polisi)


<img width="544" height="665" alt="image" src="https://github.com/user-attachments/assets/2fb9de55-b1da-4d34-a61c-a7ab32229093" />

=> PENJELASAN
Selanjutnya pada tampilan ini saya berada di Menu Utama lalu memilih 1. Informasi Polisi, sehingga program membuka sub-menu Fitur Informasi Polisi; selanjutnya saya memilih 1. Tambah data polisi dan program meminta input berurutan NRP, Nama, Pangkat, dan Status sambil melakukan validasi (NRP harus 3 digit dan unik, status hanya *Aktif/Cuti*). Saya mengisi NRP: 109, Nama: Yolla Karin, Pangkat: Brimob, Status: aktif; karena semua valid, data disimpan ke daftar personel dan muncul pesan "Berhasil ditambahkan." Setelah itu program kembali ke sub-menu Fitur Informasi Polisi agar saya bisa melanjutkan inputan lainnya (misalnya Lihat Data untuk melihat Yolla Karin sudah masuk di tabel, Ubah/Hapus, atau Kembali ke Menu Utama).



### FITUR INFORMASI POLISI (2. Lihat data)

<img width="541" height="570" alt="image" src="https://github.com/user-attachments/assets/6c6e2813-6643-4d0a-8bb9-a9fc8956c933" />


=> PENJELASAN
Selanjutnya saya berada di sub-menu Fitur Informasi Polisi dan memilih opsi 2 (Lihat Data), sehingga program menampilkan tabel "DAFTAR POLISI" berkolom NRP, Nama, Pangkat, dan Status yang berisi seluruh personel yang tersimpan saat ini; terlihat data yang baru saya tambahkan sebelumnya, yaitu NRP 109 Yolla Karin berpangkat Brimob dengan status Aktif, sedangkan baris lain adalah personel seed; setelah tabel dicetak, aplikasi otomatis kembali ke sub-menu yang sama agar saya bisa melanjutkan tindakan lain seperti melihat detail per NRP, mengubah, mencari, menghapus data, atau kembali ke Menu Utama.


### FITUR INFORMASI POLISI (3. Detail ringkasan (by NRP))

<img width="531" height="481" alt="image" src="https://github.com/user-attachments/assets/f395fdef-c76b-4a38-962a-328f1ddf2f04" />


<img width="539" height="261" alt="image" src="https://github.com/user-attachments/assets/b08bab7b-19cc-49cc-a876-3fcb751a932b" />


=> PENJELASAN
Pada tampilan ini saya berada di sub-menu Fitur Informasi Polisi dan memilih opsi 3 (Detail Ringkasan by NRP); program meminta saya memasukkan NRP, saya ketik 106, lalu sistem mencari data personel dengan NRP tersebut dan menampilkan ringkasan satu orang—NRP 106 atas nama Dhany Indra, pangkat Jendral, status Aktif dalam kotak “DETAIL RINGKASAN”; jika NRP tidak ditemukan mestinya muncul pesan penolakan, dan setelah ringkasan ditampilkan program otomatis mengembalikan saya ke sub-menu Fitur Informasi Polisi untuk memilih aksi berikutnya.


 ### FITUR INFORMASI POLISI (4. Ubah data)

<img width="547" height="433" alt="image" src="https://github.com/user-attachments/assets/e02aa68c-7f3e-408d-a789-64781ac3c3c6" />

<img width="529" height="254" alt="image" src="https://github.com/user-attachments/assets/d881f677-6809-46b7-8119-397529a73e7b" />



=> PENJELASAN
Pada tampilan ini saya memilih opsi 4 (Ubah Data) di Fitur Informasi Polisi, lalu memasukkan NRP 102 agar sistem mencari record personel yang ingin diubah; program menawarkan tiga kolom yang bisa diisi sebagian atau dilewati (kosong = tidak diubah), jadi saya membiarkan nama kosong (tetap seperti semula), mengganti pangkat menjadi Kapolsek, dan mengisi status menjadi aktif; karena NRP 102 valid dan nilai status sesuai aturan (Aktif/Cuti), sistem berhasil memperbarui data dan menampilkan pesan “Diupdate.”, kemudian saya dikembalikan lagi ke sub-menu Fitur Informasi Polisi untuk melanjutkan aksi lain (misalnya lihat tabel untuk memastikan perubahan); jika NRP tidak ditemukan atau status tidak valid, muncul pesan penolakan dan perubahan dibatalkan.







