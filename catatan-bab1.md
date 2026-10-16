# Catatan penyusunan BAB 1

Dokumen utama: `skripsi.tex`. Isi: `bab1.tex`. Referensi: `daftar-pustaka.bib`.
Build: `latexmk -xelatex skripsi.tex`.

## Sumber dan ruang lingkup

- Proposal penelitian CNN untuk deteksi website phishing pada arsitektur VPN.
- `LK02_ Research Gap - Kelompok 5.pdf`: sintesis 15 artikel.
- `Tugas Pendahulan MetPen S1.pdf`: tujuh komponen latar belakang dan hubungan gap, solusi, serta kontribusi.
- Fokus gateway/server VPN mengikuti proposal awal dan konfirmasi pengguna. Gagasan local VPN Android dari LK02 digunakan sebagai konteks literatur, bukan platform implementasi.
- Mode `\pendahuluansajatrue` di `skripsi.tex` menghasilkan BAB 1 dan daftar pustaka. Mode `\pendahuluansajafalse` mengaktifkan bagian awal skripsi dan bab lainnya; identitas dan bagian awal masih perlu diisi sebelum mode skripsi lengkap digunakan.

## Pemetaan ketentuan tugas

| Komponen | Letak dalam Latar Belakang |
| --- | --- |
| Konteks/topik | Phishing melalui URL dan perlindungan komunikasi VPN |
| Masalah nyata dan urgensi | Pencurian informasi melalui URL tiruan, konteks e-wallet, serta keterbatasan fungsi VPN dalam menentukan keamanan tujuan akses |
| Penelitian terdahulu | Sintesis model fuzzy, CNN karakter, model hibrida, CNN-Fusion, ekstensi peramban, dan evaluasi OpenVPN |
| Research gap | Celah bukti empiris mengenai keberhasilan pemblokiran phishing, kesalahan pemblokiran URL sah, serta biaya pemrosesan tambahan pada server VPN dalam satu lingkungan eksperimen |
| Solusi | CNN karakter pada server VPN dengan klien uji yang menyerahkan URL |
| Novelty/kontribusi | Bukti evaluasi operasional pengendalian akses dan dampak integrasi terhadap kinerja VPN; prototipe menjadi sarana eksperimen |
| Arah rumusan masalah | Dua pertanyaan yang dipasangkan dengan dua tujuan: pengukuran hasil pengendalian akses dan analisis dampak integrasi terhadap kinerja VPN |

Outline BAB 1 mengikuti Panduan Skripsi FILKOM v3.0: Latar Belakang, Rumusan Masalah, Tujuan, Manfaat, Batasan Masalah, dan Sistematika Pembahasan. Ketentuan administratif proposal hibah seperti RAB, RIP, CV pengusul, dan batas 1.000 kata untuk format proposal asal tidak dipindahkan menjadi ketentuan tugas Metopen, karena PDF tugas tidak menetapkannya.

## Penyesuaian substansi

1. Klaim persentase kebocoran data global, keunggulan CNN atas seluruh algoritme klasik, dan tidak adanya VPN yang mampu mendeteksi phishing dihapus. Sumber yang ditelaah tidak cukup untuk mendukung generalisasi tersebut.
2. VPN tidak otomatis membuka path dan query URL HTTPS. Draf menetapkan mekanisme klien uji yang mengirim URL ke detektor server VPN sebelum akses ke tujuan, tanpa inspeksi/dekripsi TLS. Ini adalah rancangan operasional yang diusulkan untuk membuat batas eksperimen jelas, bukan fitur prototipe yang telah terimplementasi. Perlindungan dibatasi pada klien yang berpartisipasi.
3. Draf sebelumnya mempertahankan dua rumusan masalah dari nomor 1 dan 4 proposal awal. Revisi masukan dosen mengubah rumusan pertama dari langkah perancangan/implementasi menjadi tingkat keberhasilan pemblokiran phishing dan tingkat kesalahan pemblokiran URL sah. Rumusan kedua tetap menguji dampak integrasi terhadap kinerja VPN; ukuran pengendalian akses dipusatkan pada rumusan pertama. Tujuan, gap, kontribusi, manfaat, batasan, dan uraian BAB IV diselaraskan. Ketepatan prediksi model menjadi informasi pendukung untuk menjelaskan hasil tindakan sistem. Pengujian khusus zero-day, pergeseran distribusi berbasis waktu, dan pelatihan ulang berkala tetap berada di luar cakupan. Pemisahan data tetap digunakan untuk mengurangi kebocoran data.
4. Target akurasi proposal tidak ditulis sebagai hasil yang sudah dicapai. Angka penelitian terdahulu ditandai sebagai hasil yang dilaporkan penulisnya; angka lintas dataset tidak dijadikan peringkat langsung.
5. Seluruh 15 artikel LK02 dimasukkan ke BibTeX dan disitasi sesuai konteksnya. RFC 8446 ditambahkan sebagai sumber primer tentang TLS sehingga daftar pustaka berisi 16 sumber. Pemakaian semua artikel tidak berarti bobot relevansi atau kualitas buktinya sama.
6. Data dari Common Crawl diposisikan sebagai kandidat URL sah yang memerlukan penelaahan label. Data uji tidak memuat kredensial atau informasi pribadi pada URL.

## Pemeriksaan sumber

Pemeriksaan dilakukan pada metadata, abstrak, atau bagian teks yang tersedia dari laman penerbit/sumber primer. Ini bukan pemeriksaan ulang seluruh teks lengkap 15 artikel. Temuan yang tidak terverifikasi secara memadai tidak dipertahankan sebagai angka pembuktian dalam BAB 1.

- [CNN-Fusion, sumber penerbit](https://www.sciencedirect.com/science/article/pii/S0020025523002281): halaman diperbaiki menjadi 328-345 dan DOI dilengkapi menjadi `10.1016/j.ins.2023.02.039`.
- [Minh Linh dkk., sumber penerbit](https://ijece.iaescore.com/index.php/IJECE/article/view/34479): penelitian mengembangkan ekstensi peramban dengan layanan deteksi pada server. Pengiriman URL dari klien ke server tidak diposisikan sebagai kebaruan penelitian ini.
- [Munadi dkk., sumber penerbit](https://telkomnika.uad.ac.id/index.php/TELKOMNIKA/article/view/12231): penelitian mengevaluasi tunnel broker melalui OpenVPN, termasuk throughput TCP/UDP. Sintesis gap membedakan fokus tersebut dari pengujian detektor phishing pada server VPN.
- [Dzaky dan Edrisy, sumber penerbit](https://al-haramjournal.id/index.php/PESHUM/article/view/8311): halaman diperbaiki menjadi 3614-3625.
- [Nanda dkk., sumber penerbit](https://www.sciencedirect.com/science/article/pii/S2772671124001153): DOI lengkap `10.1016/j.prime.2024.100533`. Angka confusion matrix/false positive dari LK02 tidak digunakan untuk menyimpulkan keunggulan universal.
- [Nordin dkk., PDF penerbit](https://ijeecs.iaescore.com/index.php/IJEECS/article/viewFile/25698/15307): nama lengkap penulis dan DOI dilengkapi dari halaman pertama artikel.
- Artikel Wangchuk dan Gonsalves (2026) dipertahankan dari LK02 untuk deskripsi arsitekturnya. Teks lengkap artikel belum berhasil diperiksa ulang; angka F1, ROC-AUC, dan klaim generalisasi dalam tabel LK02 tidak disalin. [Dataset yang diterbitkan penulis](https://data.mendeley.com/datasets/3jddhy2f6s/1) mengonfirmasi hubungan dataset dengan judul penelitian tersebut.
- [RFC 8446](https://www.rfc-editor.org/rfc/rfc8446) digunakan untuk menjelaskan perlindungan data aplikasi oleh TLS.

Identitas pribadi dan pembimbing tidak disimpulkan dari nama pengusul proposal maupun anggota kelompok LK02. PDF mode pendahuluan langsung dimulai dari BAB 1.

## Revisi masukan dosen (11 Oktober 2026)

Research gap dinyatakan sebagai kesenjangan bukti pada studi yang ditelaah, bukan klaim bahwa seluruh penelitian terdahulu belum pernah menggabungkan CNN dan VPN. Pembahasan menjelaskan keterbatasan transfer hasil klasifikasi dataset dan efisiensi model ke hasil tindakan sistem serta kinerja VPN.

| Pasangan | Hasil yang menjawab rumusan masalah | Tujuan yang sesuai |
| --- | --- | --- |
| Rumusan 1 dan tujuan 1 | Proporsi permintaan phishing yang berhasil diblokir dan proporsi permintaan sah yang keliru diblokir | Penelitian mengukur kedua tingkat pemblokiran pada skenario uji yang ditetapkan |
| Rumusan 2 dan tujuan 2 | Perubahan latensi, throughput, CPU, dan memori pada VPN tanpa dan dengan detektor | Penelitian menganalisis pengaruh integrasi melalui perbandingan kedua kondisi |

Penyebut masing-masing tingkat pemblokiran adalah seluruh permintaan uji pada kelas label yang bersangkutan. Pengukuran kinerja menggunakan trafik sah yang sama dan diizinkan pada kedua kondisi untuk menghindari kesimpulan keliru akibat berkurangnya trafik setelah pemblokiran. Definisi ukuran dan rincian pengukuran dipindahkan ke draf BAB 3 pada penyesuaian panduan FILKOM berikutnya; BAB 1 tetap menjelaskan cakupan evaluasinya.

Kalimat dalam BAB 1 diawali subjek, termasuk butir manfaat dan tujuan. Kedua rumusan masalah dikecualikan sesuai arahan terbaru pengguna dan diawali kata tanya "Bagaimana". Rumusan pertama tetap menanyakan hasil pengukuran keberhasilan pemblokiran dan kesalahan pemblokiran, sedangkan rumusan kedua menanyakan pengaruh integrasi terhadap kinerja VPN. Tujuan tetap selaras dengan kedua pertanyaan tersebut. Frasa pembuka seperti "Berdasarkan uraian tersebut", "Dalam penelitian ini", dan "Bagi pengembangan ilmu" dipindahkan atau dirumuskan ulang pada bagian lainnya.

## Penyesuaian Panduan Skripsi FILKOM v3.0

Acuan penyesuaian adalah `PanduanSkripsiFilkom-v3.0.pdf` yang diberikan pengguna. Nomor halaman pada tabel berikut merupakan nomor tercetak di panduan, bukan nomor urut halaman PDF (nomor PDF lebih besar 22 halaman).

| Bagian panduan | Ketentuan dan penerapan |
| --- | --- |
| 3.3.2, hlm. 29–30 | Judul disarankan 10–15 kata. Judul dipadatkan menjadi 13 kata: “Implementasi Convolutional Neural Network untuk Deteksi URL Phishing pada Arsitektur Virtual Private Network”. Topik dan lingkup tetap sama. |
| 3.4.1.1, hlm. 33–34 | Latar belakang disusun dari konteks umum menuju masalah khusus, dukungan penelitian terdahulu, kesenjangan bukti, dan fokus penelitian. |
| 3.4.1.2–3.4.1.3, hlm. 34–38 | Rumusan masalah berbentuk pertanyaan yang diawali "Bagaimana", dapat diukur, dan dipasangkan dengan tujuan yang sederhana serta jelas. Ketentuan mendahulukan subjek diterapkan pada bagian lainnya sesuai arahan terbaru pengguna; panduan sendiri mensyaratkan kalimat berita memiliki subjek dan predikat pada 3.6.2. |
| 3.4.1.4–3.4.1.6, hlm. 39 | Manfaat menyebut dampak substantif dan pemangku kepentingan. Batasan berisi ruang lingkup serta asumsi. Rincian model dan definisi ukuran dipindahkan ke bagian Rancangan Model dan Evaluasi dalam `bab3.tex`. |
| 3.2 dan 3.4.4, hlm. 28, 43–45 | Sistematika menggunakan Bab 1 Pendahuluan, Bab 2 Landasan Kepustakaan, Bab 3 Metodologi Penelitian, Bab 4 Hasil dan Pembahasan, serta Bab 5 Penutup. Panduan mengizinkan penyesuaian jumlah dan nama bab; lima bab dipertahankan untuk rancangan evaluasi ini. |
| 3.5.1, hlm. 46 | Daftar Pustaka diganti menjadi Daftar Referensi dan tetap memuat hanya sumber yang disitasi, diurutkan berdasarkan nama serta tahun. |
| 3.6.1, hlm. 47–48 | A4, margin kiri 4 cm dan sisi lain 3 cm, Calibri 12 pt, spasi tunggal, judul bab 16 pt, subbab level 2–3 sebesar 14 pt, serta level 4 sebesar 12 pt. Kedalaman penomoran dibatasi sampai X.X.X.X. Nomor halaman badan dan referensi berupa angka Arab di tengah bawah. |
| 3.6.2, hlm. 48 | Istilah digunakan secara konsisten, misalnya himpunan data. Istilah server dipertahankan sesuai arahan pengguna dan dicetak miring sebagai istilah asing. |
| 3.6.6.3, hlm. 55–56, 60–63 | Sitasi 2–3 penulis memuat semua nama; 4 penulis atau lebih memakai nama pertama diikuti et al. Referensi daring yang laman sumbernya berhasil diperiksa dilengkapi URL, medium, dan tanggal akses dalam bahasa Indonesia. |

Pemeriksaan laman sumber pada 11 Oktober 2026 mencakup metadata, abstrak, atau teks yang tersedia; tanggal akses tidak menyatakan bahwa seluruh teks lengkap telah ditelaah. Empat belas entri dilengkapi tanggal akses berdasarkan pemeriksaan pada sesi ini. Entri Dzaky dan Edrisy serta Wangchuk dan Gonsalves mempertahankan metadata dan DOI sebelumnya karena laman artikelnya tidak berhasil diperiksa ulang; tanggal akses baru tidak direka untuk kedua entri tersebut. Keterbatasan pemeriksaan teks lengkap Wangchuk dan Gonsalves tetap berlaku sebagaimana catatan sebelumnya.

Ruang lingkup keluaran tetap BAB 1 dan Daftar Referensi. BAB 2 dan BAB 3 masih berupa draf; perubahan nama bab dan pemindahan rincian tidak menyatakan kedua bab tersebut telah selesai. Bagian awal skripsi lengkap yang memerlukan identitas, persetujuan, dan hasil penelitian belum diaktifkan. Pengaturan jarak antarparagraf dan antarjudul tetap mengikuti template LaTeX yang tersedia karena panduan menyerahkan rincian tersebut kepada berkas template resmi terpisah yang tidak disertakan.

## Pemadatan Latar Belakang (13 Oktober 2026)

Pemadatan hanya berlaku pada subbab 1.1 Latar Belakang. Subbab 1.2-1.6 dikembalikan ke versi sebelum pemadatan sesuai klarifikasi pengguna. Dua rumusan masalah tetap diawali "Bagaimana", sedangkan kalimat lainnya tetap diawali subjek. Istilah server tetap digunakan dan dicetak miring.

Latar belakang mempertahankan alur konteks, masalah dan urgensi, penelitian terdahulu, research gap, solusi, kontribusi, serta arah penelitian. Kajian metode dan penjelasan berulang diringkas; seluruh 16 sumber tetap disitasi. Research gap tetap dibatasi pada bukti dari studi yang ditelaah, dengan fokus pada hasil pemblokiran dan dampak integrasi terhadap kinerja VPN. Ukuran huruf, margin, spasi, dan struktur bab mengikuti pengaturan sebelumnya.

Satu paragraf tambahan setelah research gap memperjelas konsekuensi pemblokiran URL sah, kegagalan menghentikan phishing, dan tambahan pemrosesan terhadap pengguna. Paragraf ini memperkuat alasan pengukuran keamanan dan kinerja secara bersama; kalimat-kalimatnya diawali subjek.

## Penajaman alasan pemilihan CNN dan VPN (13 Oktober 2026)

Pemilihan CNN dikaitkan dengan pembelajaran pola lokal karakter URL, ekstraksi fitur bersama klasifikasi, dan kebutuhan rancangan yang mempertimbangkan sumber daya. Perbandingan dengan SVM dan Random Forest dibatasi pada pendekatan berbasis fitur buatan; draf tidak menyatakan bahwa semua penggunaan kedua algoritma selalu memerlukan fitur buatan. [Aljofey dkk. (2020), PDF penerbit](https://mdpi-res.com/d_attachment/electronics/electronics-09-01514/article_deploy/electronics-09-01514-v2.pdf) mendukung pembelajaran fitur URL secara otomatis.

[Wei dkk. (2020), pratinjau penerbit](https://www.sciencedirect.com/science/article/pii/S1389128620301109) melaporkan pelatihan CNN yang lebih cepat daripada LSTM pada perbandingan mereka dengan data dan perangkat yang sama. Klaim tersebut tidak dipindahkan menjadi klaim inferensi CNN selalu lebih cepat. [Hussain dkk. (2023), pratinjau penerbit](https://www.sciencedirect.com/science/article/pii/S0020025523002281) mendukung potensi rancangan CNN yang ringkas. Pemilihan CNN merupakan alasan rancangan yang didukung literatur, bukan pembuktian bahwa CNN paling unggul atas seluruh alternatif; evaluasi penelitian tetap membandingkan VPN tanpa dan dengan detektor.

Pemilihan VPN dijelaskan sebagai konteks arsitektur penelitian bagi klien yang berbagi layanan VPN. Pemusatan inferensi dan pengelolaan model merupakan tujuan rancangan, bukan hasil eksperimen atau kemampuan bawaan VPN mendeteksi phishing. Klien uji mengirim URL melalui koneksi VPN; keterbatasan pembacaan URL HTTPS dan penerapan keputusan pada klien tetap dinyatakan. Penempatan pada server yang sama memungkinkan pengujian perebutan sumber daya antara detektor dan layanan VPN. Pemeriksaan sumber pada tanggal tersebut tidak mengubah tanggal akses lama dalam basis referensi.

Isi subbab 1.2-1.6 dipertahankan. Pengaturan Needspace menjaga judul Tujuan bersama butirnya serta judul BAB 3 bersama uraiannya dalam Sistematika Pembahasan.

## Verifikasi hasil

- PDF hasil revisi berhasil dibangun ulang dengan XeLaTeX melalui latexmk dan terdiri atas 7 halaman. Latar belakang berakhir pada halaman 2 sebelum Rumusan Masalah, dengan panjang kurang dari dua halaman isi. Rumusan masalah tampil pada halaman 2 dan tujuan pada halaman 3. Salinan hasil akhir tersedia di `output/pdf/pendahuluan-revisi.pdf`.
- Keenam subbab tampil dengan penomoran 1.1-1.6. Seluruh 16 kunci sitasi ditemukan dalam basis referensi.
- Semua halaman telah dirender dan diperiksa secara visual. Tanda kutip, sitasi, margin, nomor halaman, dan pemisahan entri daftar pustaka diperiksa.
- Log kompilasi XeLaTeX tidak memuat sitasi belum terselesaikan, karakter hilang, atau overfull/underfull box. Dua peringatan bawaan template tentang alias bahasa dan inputenc tetap ada dan tidak menghambat build.
