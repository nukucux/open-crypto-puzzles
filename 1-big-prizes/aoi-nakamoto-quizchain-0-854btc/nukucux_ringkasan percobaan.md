# Ringkasan Lengkap: Puzzle Real Big Block (Aoi Nakamoto)

**Target:** 0,777 BTC di `14zMkTgaVXJcxdh4JdWi29MLRR44iUSG9W` — didanai 24 Juli 2019, di-rehash 30 Juli 2019, **masih belum terpecahkan sampai hari ini**.

---

## 1. Mekanisme (terbukti, dasar semua pengujian)

```
teks kandidat --MD5--> entropy 128-bit --> mnemonic BIP39
--> BIP44 m/44'/0'/0'/0/i --> secp256k1 --> alamat P2PKH
```

Setiap kandidat diperiksa ke **dua** alamat sekaligus:
- `14zMkTgaVXJcxdh4JdWi29MLRR44iUSG9W` (target aktif)
- `1EFojcAo2vbhRGCGCa7q8Wwvzss28mhQYC` (escrow lama, sebelum rehash — kalau ini cocok, berarti teks & aturan benar, tinggal satu twist lagi)

---

## 2. Yang TERBUKTI benar (bukan dugaan)

| Fakta | Bukti |
|---|---|
| Sumber teks = chapter "Second", Wattpad ID 720888559, 273 paragraf | Dinyatakan eksplisit Aoi |
| Suntingan terakhir chapter: 23 Juli 2019, 06:36 | 3 sumber independen: API Wattpad, tweet Aoi sendiri, AMP page |
| Teks 272/273 paragraf akurat sampai byte | Checksum `data-p-id` (=MD5 paragraf) dari 2 render berbeda (halaman biasa + AMP) |
| Paragraf ke-273 ("What?") bukan misteri | Duplikat isi persis, Wattpad kasih ID beda ke kemunculan ke-2 |
| Separator antar paragraf = `\r\n\r\n` | Klaim eksplisit Aoi (post 31 Juli) **+** eksperimen browser nyata (copy dari HTML asli, tempel ke asciivalue.com, 272/272 batas paragraf konsisten) |
| NBSP → spasi, spasi ujung paragraf hilang saat disalin browser | Eksperimen browser yang sama |
| Aturan seleksi paragraf = ITASM (I,T,A,S,M jadi "aman", lainnya di-flip: huruf pertama kecil, huruf terakhir besar) | Reproduksi Stage One cocok alamat `19TbyN5KCg...`, dikonfirmasi independen (stakeados, GitHub issue #1), dikonfirmasi prefiks MD5 `9dd` yang Aoi terbitkan sendiri |
| 3 grup STNM ditanam sengaja di chapter (par. 4-7, 92-95, 167-170) | Pola F-F-W-W identik Stage One, dikonfirmasi independen oleh peneliti lain (fork AppleLamps) |
| RBB tidak punya baris "Format:" sama sekali | Satu-satunya blok dari 147+ yang begitu — disengaja, dinyatakan Aoi sendiri |
| Kata pengganti "vOIce", "himselF" di contoh Grycoin Block 2 BUKAN bagian solusi nyata | Dinyatakan eksplisit oleh Aoi sebagai ilustrasi |

---

## 3. Yang sudah disapu TUNTAS secara komputasi (semua NIHIL)

| Ruang pencarian | Jumlah kandidat |
|---|---|
| Setiap edit 1 karakter (ganti/sisip/hapus), semua posisi | ~105.000.000 (GPU) |
| Setiap pola kapitalisasi 1 kata, semua kemunculan sekaligus | ~7.000.000+ (GPU) |
| Setiap rentang paragraf berurutan (panjang 2–273) | 594.048 |
| Karakter kontrol (`\n`,`\r`,`\r\n`) di setiap posisi teks | 275.832 |
| Kombinasi kutip+ulang+balik+Atbash+hapus+sufiks (berpasangan) | ribuan |
| Klaster 11 paragraf "humanity" — grup, kata, kapitalisasi (256 pola), balik, Atbash, hapus | ~5.000 |
| Klaster 13 paragraf "spasi tertinggal" — berbagai kombinasi | ~270 |
| `<br>` internal diganti kosong/`\n`/`\n\n`/`\r\n`/`\r\n\r\n`/spasi, di 10 titik yang diketahui | 40 |
| Hierarki judul/subjudul (26 header) sebagai kandidat, MD5 & SHA-256 | ~190 |
| Aturan seleksi alternatif: STAOHI (huruf "Satoshi"), STNM sebagai aturan | ~300 |
| Sinyal "Only"/"Chance" (dari post "Grycoin is the Only Chance") sendiri & digabung temuan lain | ~700 |
| Caesar-shift & Atbash pada kata-kata tematik (Aoi, Tom, Satoshi, dll) | ~300 |

**Kesimpulan dari semua ini:** kalau jawabannya "teks chapter (atau bagian kontigunya) + satu modifikasi kecil yang sudah terdokumentasi", kita pasti sudah menemukannya. Bukan itu jawabannya.

---

## 4. Blok saudara — status dan mekanismenya

| Blok | Status | Mekanisme/Jawaban |
|---|---|---|
| **Stage One** (post Hal Finney) | ✅ Solved | ITASM/STNM, terverifikasi 3 arah |
| **Genesis puzzle run-1** ("The solution is the puzzle") | ✅ Solved (reddeneer, 15 Jul 2019) | `1A1 efi2DM Hal Finney TS mN ihsotaS otomakaN TOMI Omit TOMI [WIF blok 44]`, MD5 cocok `684` |
| **Block 23 run-1** | ✅ Solved (silver_anth, 23 Jul 2019) | `climate emergency episode on this planet. CGD` — kutipan literal dari chapter |
| **Block 29 run-1** | ✅ Solved | Draft 235 kata, twist `voice`→`vOIce` |
| **Block 13 run-1** ("Hint to 77") | ✅ Solved (userm1010110) | `Second Second Life Second Coming I thought xXJ`, **SHA-256** (bukan MD5!) — hierarki judul chapter dibaca sebagai kalimat |
| **Block 54** (Quizchain2) | ✅ Solved | `HAS TOMI HAL BIT Caesar` — permainan geser huruf ("huruf mendahului"), eksplisit dinyatakan "hint untuk 76" |
| **Block 76** (Quizchain2, 0,077 BTC) | ❌ Belum kita pecahkan, tapi sudah dikuras (Agustus 2026, anonim) | Filter gratis: solusi MD5 awal `1d`, string lengkap MD5 awal `f8e`. **Bukan kata kamus** (dikonfirmasi Aoi sendiri) |
| **Grycoin Block 2** ("cleczc", "recognize the signs") | ❌ Belum kita pecahkan, tapi dipecahkan puzzleponky (2019), dia menolak membagikan | Prefiks MD5 pertanyaan `7759227` (separator `\n\n`, beda dari RBB). Terbukti mengandung **kesalahan nyata** Aoi (bukan cuma logika murni) — 100 miliar+ kandidat GPU oleh Sea_Ferret_9615 (2026) tetap nihil |

---

## 5. Hipotesis yang DICOBA dan GAGAL (selain sapuan besar di atas)

- Twist "voice"→"vOIce" (dari Block 29) diterapkan ke kata lain di chapter — nihil
- Anomali `<b>b) THOMAS and Satosh</b><b>i</b>` — satu-satunya di seluruh chapter (terverifikasi tak berulang), kemungkinan besar jejak edit manual biasa, bukan sinyal. Menghapus huruf "i" dari kata itu — nihil
- Kutipan "Your turn, humanity" (gema dari penutup Section II) sebagai batas teks — nihil
- Section III ("My Identity") sebagai teks tersendiri, dengan berbagai batas — nihil
- Teks di antara/setelah grup STNM sebagai penanda batas — nihil
- Kata "Bitcoin"/"Grycoin"/"change"/"to" dengan geser huruf, dicoba ke oracle Block 76 — nihil
- 26 paragraf berawalan "I" (ditemukan manual, terverifikasi lengkap) sebagai grup — nihil
- Berbagai "false positive" yang lolos filter MD5 Block 76 tapi gagal di derivasi penuh (pelajaran: filter parsial ≠ bukti)

---

## 6. Sumber daya manusia — petunjuk yang BELUM tuntas dikejar

- **puzzleponky / ponky / pogo** — memecahkan Stage One DAN Grycoin Block 2, aktif di Discord sampai 2023, menolak membagikan jawaban ("saving for the glorious day Aoi may return"), tapi terbuka kalau ada info publik baru
- **RStudios** — anggota lama komunitas, Agustus 2026 tiba-tiba mengumumkan berhenti membantu orang lain, "mau coba sendiri di ruang tersembunyi" — tepat setelah Block 76 terpecahkan
- **anderson** — peneliti aktif Agustus 2026, mencari arsip asli 2019 (script, screenshot, cache) dari berbagai orang
- **Sea_Ferret_9615** — peneliti aktif 2026, sudah GPU sweep >100 miliar kandidat untuk Grycoin Block 2, menghubungi ponky langsung
- **Fork AppleLamps/open-crypto-puzzles** — riset paralel otomatis (AI agent) yang mengonfirmasi independen temuan 3 grup STNM kita

---

## 7. Yang MASIH terbuka

1. **Sapuan edit 2-karakter penuh** — belum selesai, ruangnya jauh lebih besar dari GPU semalam
2. **Kemungkinan twist bergaya wordplay personal** (seperti Block 54/76) — kalau ini benar, tidak ada komputasi yang akan pernah menemukannya
3. **Arsip Juli 2019 yang sebenarnya** — tidak ditemukan di mana pun (Wayback Blocks Wattpad)
4. **Kontak langsung dengan ponky/RStudios/anderson** — jalur yang paling realistis tersisa

---

## Pelajaran metodologis yang berulang kali terbukti

Aoi **terbukti salah** menjelaskan byte tulisannya sendiri, minimal 4 kali berbeda (Stage One, RBB pra/pasca-rehash, Grycoin Block 2). **Jangan pernah percaya klaim verbalnya soal byte** — hanya percaya pembuktian MD5 langsung atau eksperimen nyata. Filter MD5 parsial (2-3 digit) **bukan** bukti — selalu perlu derivasi penuh untuk konfirmasi.
