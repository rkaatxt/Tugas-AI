# Studi Ablasi RNN, LSTM, GRU vs ANN untuk Prediksi Trafik Seluler Milan

Tugas Workshop Deep Learning — Teknik Telekomunikasi ITERA.

<!-- Ganti seluruh isian bertanda [ ... ] di bawah. Hapus komentar ini. -->

## Kelompok

| Peran | Nama | NIM |
|---|---|---|
| Ketua | [Ade Raka Maulana] | [124400047] |
| Anggota | [Andriansyah Amir] | [124400065] |

- **Kelas:** [RA]
- **Lokasi kelompok:** [5] — [Bandara Linate] (digit terakhir NIM terkecil)
- **Laporan:** [`laporan-latex/main.pdf`]

## Cara Menjalankan

```bash
uv sync
uv run jupyter lab
```

Buka `tugas_ablasi.ipynb`, isi `LOKASI_KELOMPOK`, lalu jalankan semua sel. Semua run tercatat di `hasil/ablasi.csv`.

Perangkat yang kami pakai: [laptop CPU Intel i5], total waktu training: [227.6] menit.

## Ringkasan Hasil

[Pada lokasi Duomo, semua model mengalahkan baseline naif terbaik (MAE minggu lalu = 468). Dengan konfigurasi terbaik, test MAE rata-rata 3 seed adalah GRU 221.9, RNN 226.3, LSTM 245.0, dan ANN 254.9, jadi model rekuren unggul atas ANN. Penggabungan nilai terbaik per faktor memperbaiki test MAE semua model, paling besar pada ANN (313.9 → 254.9). Pada lokasi kelompok (Linate), konfigurasi hasil tuning di Duomo tidak konsisten menggeneralisasi: test MAE terbaik GRU 7.7, ANN 7.9, LSTM 8.5, dan RNN 8.5, tetap di bawah baseline naif terbaik (10.1).]

## Struktur

```
tugas_ablasi.ipynb      notebook eksperimen (di-commit beserta output)
data/                   data trafik per jam (Duomo + 10 lokasi tugas)
hasil/                  CSV seluruh run, tabel, dan grafik
laporan-latex/ atau laporan-typst/   sumber laporan + PDF
```

## Data

Telecom Italia Big Data Challenge (Barlacchi dkk., 2015, *Scientific Data*, lisensi ODbL), versi per jam dari Zhang dkk. (INFOCOM 2021). Disiapkan oleh pengajar di repo [mctosima/dl-workshop](https://github.com/mctosima/dl-workshop).
