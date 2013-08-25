IGOS Nusantara Software Development Kit
=======================================

Standar Aplikasi
----------------
Revisi XX Agustus 2013

[http://ignsdk.web.id][1]

========================================================================

##Daftar Isi
1. Penjelasan Umum
2. Tentang Aplikasi
3. Nama Aplikasi
4. Lokasi Aplikasi
5. Struktur Berkas dan Direktori

========================================================================

### Penjelasan Umum
1. Standar ini bersifat __wajib__. Setiap aplikasi yang dikembangkan dengan
IGN SDK harus mengikuti kaidah-kaidah yang dijabarkan dalam standar ini.
2. Nama __IGOS Nusantara Software Development Kit__ selanjutnya ditulis
sebagai __IGN SDK__.
3. __Aplikasi__ adalah aplikasi yang dibuat dengan IGN SDK.
4. __Host__ adalah lingkungan sistem operasi sebagai tempat dijalankannya
IGN SDK dan Aplikasi.
5. __API__ adalah kependekan dari _Application Programming Interface_.

### Tentang Aplikasi
Aplikasi dalam hakikatnya adalah sebuah direktori berisi yang halaman
web (yang ditulis sesuai dengan standar HTML4/HTML5) dan berkas-berkas
lain (lihat bagian _Struktur Berkas dan Direktori_). Aplikasi dapat
mengakses fungsi-fungsi pada Host dengan memanfaatkan API IGN SDK.

Aplikasi dikategorikan menjadi tiga, yaitu:

1. Aplikasi _test_, adalah Aplikasi yang digunakan untuk
mendemonstrasikan API IGN SDK. Aplikasi ini dibuat oleh pengembang IGN
SDK.
2. Aplikasi contoh, adalah Aplikasi yang dibuat oleh pengembang IGN SDK
dan/atau pihak ketiga dan pengembangannya berada di repositori
[ignsdk-example][2].
3. Aplikasi pihak ketiga, adalah Aplikasi yang dibuat oleh pihak ketiga.

### Nama Aplikasi
Nama Aplikasi ditulis dalam huruf kecil (lowercase) dan berakhiran
".ign", misalnya "aplikasi-bagus.ign".

### Lokasi Aplikasi
Lokasi Aplikasi dibedakan menjadi lokasi untuk Aplikasi _test_, Aplikasi 
contoh, dan Aplikasi pihak ketiga.

* Aplikasi _test_ berada di direktori `/usr/share/ign-sdk/test/`.
* Aplikasi contoh berada di direktori `/opt/ignsdk/example/`.
* Aplikasi pihak ketiga berada di direktori `/opt/ignsdk/`.

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
|   +-- app.png
|
+-- bin/
|
+-- menu/
    |
    +-- ignsdk-namaaplikasi.desktop
```

#### Berkas `ignsdk.json`
Berkas `ignsdk.json` merupakan _manifest_ Aplikasi. Berkas tersebut
ditulis dengan format JSON (JavaScript Object Notation). Berikut adalah
struktur dari berkas `ignsdk.json`:

```
{
"config" :	{ "debug" : value }
"window" :	{
			"transparent" : value,
			"noframe" : value,
			"fullscreen" : value,
			"width" : value,
			"height" : value
			}
"button" :	[
			"back",
			"forward",
			"stop",
			"reload"
			]
}
```

#### Berkas `index.html`
Berkas ini adalah berkas utama yang harus ada dalam Aplikasi. Saat
Aplikasi dijalankan, IGN SDK akan mengeksekusi berkas ini terlebih
dahulu.

#### Direktori `icon/` dan Berkas `app.png`
Direktori ini digunakan untuk menyimpan berkas yang akan dipakai sebagai
ikon aplikasi. Format gambar yang dipakai adalah PNG (Portable Network Graphics).

#### Direktori `bin/`
Direktori ini digunakan untuk menyimpan berkas executable sebagai
penunjang Aplikasi. Berbagai macam berkas executable bisa diletakkan
dalam direktori ini, misalnya shell script (.sh), Python (.py), maupun
format ELF Linux.

#### Direktori `menu/` dan Berkas `ignsdk-namaaplikasi.desktop`
Direktori `menu/` digunakan untuk menyimpan berkas [_desktop entry_][3]
(berkas berakhiran ".desktop"). Semua berkas dalam direktori ini
nantinya akan dipasang ke direktori `/usr/share/applications/` saat
proses instalasi.

Berkas _desktop entry_ dalam direktori ini harus diberi nama dengan
awalan "ignsdk-" diikuti dengan nama aplikasi, misalnya
`ignsdk-aplikasi-bagus.desktop`. Jika terdapat lebih dari satu berkas
_desktop entry_, maka bedakan nama berkas-berkas tersebut pada
akhirannya, misalnya `ignsdk-aplikasi-bagus.desktop`, 
`ignsdk-aplikasi-bagus-help.desktop`, dan seterusnya.

[1]: http://ignsdk.web.id
[2]: https://github.com/anak10thn/ignsdk-example
[3]: http://standards.freedesktop.org/desktop-entry-spec/latest/
