IGOS Nusantara Software Development Kit
=======================================

## Standar Aplikasi
Revisi XX Agustus 2013

[http://ignsdk.web.id][1]

========================================================================

### Penjelasan Umum
1. Standar ini bersifat _wajib_. Setiap aplikasi yang dikembangkan dengan
IGN SDK harus mengikuti kaidah-kaidah yang dijabarkan dalam standar ini.
2. Nama _IGOS Nusantara Software Development Kit_ selanjutnya ditulis
sebagai IGN SDK.
3. _Aplikasi_ adalah aplikasi yang dibuat dengan IGN SDK.
4. _Host_ adalah lingkungan sistem operasi sebagai tempat dijalankannya
IGN SDK dan Aplikasi.
5. _API_ adalah kependekan dari _Application Programming Interface_.

### Tentang Aplikasi
Aplikasi dalam hakikatnya adalah sebuah direktori berisi yang halaman
web (yang ditulis sesuai dengan standar HTML4/HTML5) dan berkas-berkas
lain (lihat bagian _Struktur Berkas dan Direktori_). Aplikasi dapat
mengakses fungsi-fungsi pada Host dengan memanfaatkan API IGN SDK.

Aplikasi dikategorikan menjadi tiga, yaitu. 

1. Aplikasi _test_, adalah Aplikasi yang digunakan untuk
mendemonstrasikan API IGN SDK. Aplikasi ini dibuat oleh pengembang IGN
SDK.
2. Aplikasi contoh, adalah Aplikasi yang dibuat oleh pengembang IGN SDK
dan/atau pihak ketiga dan pengembangannya berada di repositori
[ignsdk-example][2].
3. Aplikasi pihak ketiga, adalah Aplikasi yang dibuat oleh pihak ketiga.

### Nama Aplikasi
Nama Aplikasi ditulis dalam huruf kecil (lowercase) dan berakhiran
".ign", misalnya _aplikasi-bagus.ign_.

### Struktur Berkas dan Direktori

Aplikasi setidaknya memuat beberapa berkas dan direktori dengan struktur
sebagai berikut:

```
aplikasi.ign/
|
+-- ignsdk.json
|
+-- index.html
|
+-- icon/
|   |
|   +-- icon.(svg|png)
|
+-- bin/
|
+-- menu/
    |
    +-- ignsdk-aplikasi.desktop
```

### Lokasi Aplikasi
Lokasi Aplikasi dibedakan menjadi lokasi untuk Aplikasi _test_, Aplikasi 
contoh, dan Aplikasi pihak ketiga.

* Aplikasi _test_ berada di direktori `/usr/share/ign-sdk/test/`.
* Aplikasi contoh berada di direktori `/opt/ignsdk/example/`.
* Aplikasi pihak ketiga berada di direktori `/opt/ignsdk/`.

[1]: http://ignsdk.web.id
[2]: https://github.com/anak10thn/ignsdk-example
