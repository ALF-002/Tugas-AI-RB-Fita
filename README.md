# Studi Ablasi RNN, LSTM, GRU vs ANN untuk Prediksi Trafik Seluler Milan

Tugas Workshop Deep Learning — Teknik Telekomunikasi ITERA.

<!-- Ganti seluruh isian bertanda [ ... ] di bawah. Hapus komentar ini. -->

## Kelompok

| Peran | Nama | NIM |
|---|---|---|
| Ketua | [Alfita Eryani Nugroho] | [124400002] |
| Anggota | [Octavia Sesilia Malau] | [124400038] |
| Anggota | [Fitria Oktavianti] | [124400058] |

- **Kelas:** [RB]
- **Lokasi kelompok:** [2] — [Università Bocconi] (digit terakhir NIM terkecil)
- **Laporan:** [`laporan-latex/main.pdf`]

## Cara Menjalankan

```bash
uv sync
uv run jupyter lab
```

Buka `tugas_ablasi.ipynb`, isi `LOKASI_KELOMPOK`, lalu jalankan semua sel. Semua run tercatat di `hasil/ablasi.csv`.

Perangkat yang kami pakai: [Jupyter Notebook Lab], total waktu training: [182.3] menit.

## Ringkasan Hasil

[Setelah menggabungkan nilai terbaik per model, test MAE terbaik adalah GRU 221,9, RNN 226,3, LSTM 246,6, dan ANN 273,9 (acuan: 237,2; 229,6; 273,6; 309,9), sehingga model rekuren tetap jauh lebih baik daripada ANN dan semuanya mengalahkan baseline naif terbaik (“minggu lalu”, 468). Perbaikan paling jelas terjadi pada ANN (turun 36 poin) dan LSTM (turun 27 poin), sedangkan RNN hanya membaik 3,3 poin, lebih kecil dari std antar seed sehingga praktis sama dengan acuan. Faktor yang paling konsisten membantu adalah batch kecil (16) dan fitur waktu, sementara dropout justru memperburuk sebagian besar model. Namun val MAE gabungan hanya membaik untuk ANN (248,9 → 218,4) dan sedikit memburuk untuk GRU, LSTM, dan RNN, menunjukkan bahwa nilai terbaik per faktor tidak selalu terbaik bila digabung.]

## Struktur

```
tugas_ablasi.ipynb      notebook eksperimen (di-commit beserta output)
data/                   data trafik per jam (Duomo + 10 lokasi tugas)
hasil/                  CSV seluruh run, tabel, dan grafik
laporan-latex/ atau laporan-typst/   sumber laporan + PDF
```

## Data

Telecom Italia Big Data Challenge (Barlacchi dkk., 2015, *Scientific Data*, lisensi ODbL), versi per jam dari Zhang dkk. (INFOCOM 2021). Disiapkan oleh pengajar di repo [mctosima/dl-workshop](https://github.com/mctosima/dl-workshop).
