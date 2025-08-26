# 🧪 Hypothesis Testing — Wine Marketing Campaign

## 🎯 Objective
Menguji apakah terdapat **perbedaan rata-rata pengeluaran untuk wine** antara pelanggan dengan tingkat pendidikan yang berbeda, menggunakan dataset *Marketing Campaign Product Wine*.

---

## 🗃️ Dataset
- **Sumber**: Marketing Campaign Dataset (Wine)
- **Unit analisis**: Setiap baris = 1 pelanggan
- **Variabel kunci**:
  - `Education` → kategori pendidikan (Basic, 2n Cycle, Graduation, Master, PhD)
  - `MntWines` → pengeluaran untuk produk wine

---

## 🧩 Hipotesis
- **H0**: Tidak ada perbedaan rata-rata pengeluaran wine antar tingkat pendidikan (μBasic = μ2nCycle = μGraduation = μMaster = μPhD)
- **H1**: Ada perbedaan rata-rata pengeluaran setidaknya di satu tingkat pendidikan
- α = 0.05

---

## 🧪 Uji Statistik
1. **Normalitas (Shapiro–Wilk per grup)**  
   - Semua p-value ≪ 0.05 → distribusi **tidak normal**
2. **Homogenitas varians (Levene)**  
   - p-value < 0.05 → varians antar grup **tidak homogen**
3. **Transformasi log**  
   - Hasil tetap tidak normal
4. **ANOVA**  
   - F-test menghasilkan **p-value ≈ 7.10 × 10⁻²⁴**
   - Karena p-value < 0.05 → **Tolak H0**

---

## 📈 Hasil & Interpretasi
- Terdapat **perbedaan signifikan** rata-rata pengeluaran wine antar tingkat pendidikan
- Pelanggan dengan pendidikan **lebih tinggi (Master, PhD)** cenderung membelanjakan lebih banyak
- Outlier signifikan membuat asumsi normalitas/homogenitas tidak terpenuhi → hasil tetap informatif tapi perlu hati-hati
- Saran lanjutan: gunakan uji non-parametrik (*Kruskal–Wallis*) sebagai validasi

---

## 📊 Visualisasi
- Boxplot pengeluaran (`MntWines`) per kategori pendidikan
- Histogram distribusi pengeluaran
