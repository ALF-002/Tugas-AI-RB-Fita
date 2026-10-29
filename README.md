# Studi Ablasi RNN, LSTM, GRU vs ANN untuk Prediksi Trafik Seluler Milan

Tugas Workshop Deep Learning — Teknik Telekomunikasi ITERA.

<!-- Ganti seluruh isian bertanda [ ... ] di bawah. Hapus komentar ini. -->

## Kelompok

| Peran | Nama | NIM |
|---|---|---|
| Ketua | Alfita Eryani Nugroho | 124400002 |
| Anggota | Octavia Sesilia Malau | 124400038 |
| Anggota | Fitria Oktavianti | 124400058 |

- **Kelas:** RB
- **Lokasi kelompok:** 2 — Università Bocconi
- **Laporan:** `laporan-latex/main.pdf`

## Cara Menjalankan

**Prasyarat:** Python 3.12+, [Git](https://git-scm.com/), dan [uv](https://docs.astral.sh/uv/).

```bash
git clone https://github.com/mctosima/dl-workshop.git
cd Tugas-AI-RB-Fita
uv sync
uv run jupyter lab
```

Buka `tugas_ablasi.ipynb`, lalu:

1. Pastikan `LOKASI_KELOMPOK = 2` (Universita Bocconi) di sel pertama.
2. Pastikan `CEPAT = False` untuk hasil akhir (`CEPAT = True` hanya untuk uji coba kode).
3. Jalankan semua sel dari atas ke bawah (**Kernel → Restart Kernel and Run All Cells**).

> **Windows:** jika `uv` tidak dikenali, jalankan dengan awalan `python -m uv` (contoh: `python -m uv sync`).

Perangkat yang kami pakai: Laptop CPU Intel i3, Jupyter Notebook Lab, total waktu training: 182.3 menit.

## Ringkasan Hasil

<<<<<<< HEAD
Setelah konfigurasi terbaik tiap faktor digabung, test MAE menjadi GRU 221,9, RNN 226,3, LSTM 246,6, dan ANN 273,9 (acuan: 237,2; 229,6; 273,6; 309,9), sehingga model rekuren tetap mengungguli ANN dan semuanya jauh di bawah baseline naif terbaik “minggu lalu” (468). Perbaikan terbesar terjadi pada ANN (turun sekitar 36 poin) dan LSTM (sekitar 27 poin), sedangkan RNN hanya membaik 3,3 poin yang masih di bawah simpangan baku antar seed, sehingga tidak berbeda secara statistik dari acuannya. Batch size kecil (16) menjadi faktor yang paling konsisten membantu, sementara dropout cenderung menurunkan kinerja pada sebagian besar model. Namun, val MAE gabungan hanya membaik pada ANN (248,9 menjadi 218,4) dan sedikit memburuk pada GRU, LSTM, dan RNN, yang menunjukkan bahwa nilai terbaik tiap faktor belum tentu terbaik saat digabung karena faktor-faktor tersebut saling berinteraksi.
=======
Setelah konfigurasi terbaik dari masing-masing faktor digabungkan, keempat model menunjukkan test MAE sebagai berikut: GRU 221,9, RNN 226,3, LSTM 246,6, dan ANN 273,9 (pada konfigurasi acuan: 237,2; 229,6; 273,6; dan 309,9). Hasil ini menegaskan bahwa arsitektur rekuren secara konsisten mengungguli ANN, dan seluruh model tetap jauh melampaui baseline naif terbaik, yaitu pola “minggu lalu” dengan MAE 468.

Peningkatan paling besar terjadi pada ANN, yang turun sekitar 36 poin, disusul LSTM dengan penurunan sekitar 27 poin. Sebaliknya, RNN hanya membaik 3,3 poin. Selisih sekecil ini masih berada di bawah standar deviasi antar-seed, sehingga secara statistik RNN tidak dapat dianggap berbeda dari konfigurasi acuannya.

Dari sisi faktor, ukuran batch kecil (16) dan penambahan fitur waktu merupakan dua hal yang paling konsisten memberi perbaikan di berbagai model. Dropout justru cenderung menurunkan kinerja pada sebagian besar model.

Meski demikian, penggabungan faktor tidak serta-merta memperbaiki val MAE. Hanya ANN yang membaik (248,9 menjadi 218,4), sedangkan GRU, LSTM, dan RNN mengalami sedikit penurunan. Temuan ini menunjukkan bahwa kombinasi dari nilai terbaik tiap faktor belum tentu menghasilkan konfigurasi terbaik secara keseluruhan, karena faktor-faktor tersebut dapat saling berinteraksi.
>>>>>>> 70a5eb9b0942bc627c05c96ba9e12fd6414b7c48

## Struktur

```
tugas_ablasi.ipynb      notebook eksperimen (di-commit beserta output)
data/                   data trafik per jam (Duomo + 10 lokasi tugas)
hasil/                  CSV seluruh run, tabel, dan grafik
laporan-latex/          sumber laporan + PDF
```

## Data

Telecom Italia Big Data Challenge (Barlacchi dkk., 2015, *Scientific Data*, lisensi ODbL), versi per jam dari Zhang dkk. (INFOCOM 2021). Disiapkan oleh pengajar di repo [mctosima/dl-workshop](https://github.com/mctosima/dl-workshop).
