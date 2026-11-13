# AirQualityHealth — DA Gelar Rasa 2026

Repository ini memuat proses **preprocessing** dan **exploratory data analysis (EDA)** untuk dashboard **AirQualityHealth**, yang menghubungkan data kualitas udara per jam dengan data kesehatan harian.

> **Penting:** Dataset yang digunakan adalah **Synthetic Metropolitan AQMS** dari panitia DA Gelar Rasa 2026. Seluruh data bersifat sintetis dan tidak merepresentasikan kondisi aktual Indonesia. Analisis dalam repository ini bersifat asosiatif, bukan kausal.

## Isi Repository

```text
.
├─ notebooks/
│  ├─ 01_preprocessing.ipynb   # pembersihan dan pembentukan fact/dimension
│  └─ 02_eda.ipynb             # EDA lengkap + figure + tabel ringkasan
├─ data/
│  ├─ fact_air_quality.parquet
│  ├─ fact_health.parquet
│  ├─ dim_date.csv
│  ├─ dim_time.csv
│  ├─ dim_site.csv
│  └─ dim_hospital.csv
├─ requirements.txt
└─ README.md
```

## Menjalankan

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter lab
```

Buka `notebooks/02_eda.ipynb` lalu jalankan seluruh cell. Notebook ini memakai Parquet yang disertakan dan akan membuat `figures/` serta `data/eda_summary/` secara lokal.

Untuk menjalankan ulang preprocessing, letakkan data mentah dari panitia di `data/raw/`:

```text
data/raw/
├─ *_AQMS.csv
├─ HLT-01_health_outcomes_daily.csv
├─ sites.csv
├─ sensors.csv
├─ hospitals.csv
└─ metadata/
   ├─ metadata_sensors.csv
   └─ metadata_dates.csv
```

Data mentah tidak disertakan dalam repository. Setelah itu jalankan `notebooks/01_preprocessing.ipynb`; hasilnya ditulis ke `data/`.

## Ringkasan Data

- Periode analisis: **1 Januari 2024–14 Oktober 2026**.
- Fact-level: **667.981** baris AQMS dan **27.491** baris kesehatan.
- Sampel analisis EDA: **667.844** baris AQMS dan **27.486** baris kesehatan.
- **533.813** observasi PM2.5 valid dari **24 stasiun** di **18 provinsi**.
- Notebook EDA menghasilkan **19 figure** dan **12 tabel ringkasan**.

## Catatan

- Data sintetis; temuan bukan representasi kondisi aktual Indonesia.
- Tidak ada denominator populasi, sehingga angka kesehatan adalah volume kunjungan/rawat inap, bukan prevalensi atau insidensi.
- Tidak ada pemetaan resmi stasiun AQMS–rumah sakit; analisis gabungan dilakukan pada level provinsi-bulan.
- Oktober 2026 hanya mencakup 1–14 Oktober.
- Dashboard Power BI dibangun terpisah dari repository ini.
