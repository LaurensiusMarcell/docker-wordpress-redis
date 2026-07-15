Dockerize WordPress dengan MySQL dan Redis

## WordPress installation page
![Install 1](wp-1.png)
![Install 2](wp-2.png)
![Install 3](wp-3.png)
![Install 4](wp-4.png)

## WordPress Dashboard
![Dashboard](wp-dashboard.png)

## Containers Running
![3 Containers](containers-running.png)

## Redis Object cache
![redis-1](redis-1.png)
![redis-2](redis-2.png)
![Redis CLI ping test](wp-3.png)
![Install 4](wp-4.png)

## Kenapa perlu volume untuk MySQL?
-> Agar data situs tidak hilang saat container dimatikan atau di restart (penyimpanan data yang permanen).
## Apa fungsi depends_on?
-> Mengatur urutan menyala. Memastikan MySQL dan Redis sudah siap beroperasi lebih dulu sebelum WordPress menyala, agar situs tidak mengalami error koneksi.
## Bagaimana cara WordPress container connect ke MySQL?
-> Melalui DNS internal Docker. WordPress cukup memanggil nama layanan `db` (seperti yang ditulis di compose), dan Docker otomatis menghubungkannya ke alamat IP container MySQL tersebut.
## Apa keuntungan pakai Redis untuk WordPress?
-> Redis menyimpan data yang sering diakses ke dalam RAM (Cache). Loading web menjadi sangat cepat dan meringankan beban server karena WordPress tidak perlu terus-menerus membaca data dari database yang lambat.
