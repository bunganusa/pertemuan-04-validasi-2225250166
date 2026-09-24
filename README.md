# Pertemua 04  Seleksi Multi-Kondisi dan Validasi Input

Nama: Bunga Nusa Pertiwi
NIM: 2225250166
Kelas: 3F

## Tujuan 
Membangun program validasi dan klasifikasi dengan rantai if-elif-else.

## Cara Menjalankan 
python praktik/validasi_klasifikasi_nilai.py

## Tabel Keputusan 
| Kategori / Cabang | Syarat Logika | Contoh Masukan |
|---|---|---|
| Input Tipe Data Salah | try-except ValueError | Ujian = abc |
| Ujian Luar Rentang | not (0 <= ujian <= 100) | Ujian = 105 |
| Tugas Luar Rentang | not (0 <= tugas <= 100) | Tugas = -5 |
| Kehadiran Luar Rentang | not (0 <= hadir <= 100) | Kehadiran = 120 |
| Kehadiran Kurang | hadir < 80 | Ujian = 80, Tugas = 80, Hadir = 70 |
| Predikat A (Lulus) | akhir >= 85 dan hadir >= 80 | Ujian = 90, Tugas = 85, Hadir = 100 |
| Predikat B (Lulus) | 70 <= akhir < 85 dan hadir >= 80 | Ujian = 80, Tugas = 80, Hadir = 90 |
| Predikat C (Lulus) | 60 <= akhir < 70 dan hadir >= 80 | Ujian = 65, Tugas = 60, Hadir = 85 |
| Predikat D (Belum Lulus) | 50 <= akhir < 60 dan hadir >= 80 | Ujian = 55, Tugas = 50, Hadir = 80 |
| Predikat E (Belum Lulus) | akhir < 50 dan hadir >= 80 | Ujian = 40, Tugas = 30, Hadir = 80 |

## Hasil Pengujian
| No | Ujian | Tugas | Hadir | Keluaran yang Diharapkan | Keluaran Aktual | Status |
|---|---|---|---|---|---|---|
| 1 | 80 | 80 | abc | Masukan ditolak: seluruh data harus berupa angka. | Masukan ditolak: seluruh data harus berupa angka. | Sesuai |
| 2 | 80 | -5 | 90 | Masukan ditolak: nilai tugas di luar rentang 0 sampai 100. | Masukan ditolak: nilai tugas di luar rentang 0 sampai 100. | Sesuai |
| 3 | 80 | 80 | 70 | Nilai akhir = 80.00, Status: Tidak memenuhi syarat kehadiran. | Nilai akhir = 80.00, Status: Tidak memenuhi syarat kehadiran. | Sesuai |
| 4 | 80 | 80 | 90 | Nilai akhir = 80.00, Predikat: B, Status: Lulus | Nilai akhir = 80.00, Predikat: B, Status: Lulus | Sesuai |
| 5 | 40 | 30 | 80 | Nilai akhir = 36.00, Predikat: E, Status: Belum lulus | Nilai akhir = 36.00, Predikat: E, Status: Belum lulus | Sesuai |

## Refleksi
Masukan tidak valid yang semula terlewat adalah ketika pengguna memasukkan teks/huruf (seperti abc) pada input angka. Hal ini menyebabkan program mengalami crash akibat kesalahan ValueError saat konversi float(). Penanganannya dilakukan dengan membungkus konversi input ke dalam blok try-except ValueError. Jika konversi gagal, program tidak akan break, melainkan menampilkan pesan peringatan ramah pengguna: "Masukan ditolak: seluruh data harus berupa angka."