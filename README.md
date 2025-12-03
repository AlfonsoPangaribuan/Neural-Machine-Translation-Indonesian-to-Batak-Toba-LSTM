# Neural Machine Translation Indonesia ke Bahasa Batak Toba

## Deskripsi Proyek
Repository ini berisi implementasi sistem penerjemahan otomatis dari Bahasa Indonesia ke Bahasa Batak Toba menggunakan pendekatan Neural Machine Translation berbasis BiLSTM dengan mekanisme Attention. Proyek ini dikembangkan untuk mendukung penelitian low resource machine translation dan menyediakan baseline terbuka untuk pasangan bahasa Indonesia dan Batak Toba.

## Fitur Utama
- Arsitektur BiLSTM Encoder–Decoder dengan Attention
- Dataset paralel berjumlah 5050 pasangan kalimat
- Evaluasi menggunakan BLEU 1–4 dan ROUGE 1, ROUGE 2, ROUGE L
- Checkpoint model pada epoch 10, 40, 70, dan 100
- Output berupa grafik BLEU, grafik ROUGE, tabel BLEU, dan tabel ROUGE
- Model dilatih dengan Early Stopping dan Adam Optimizer

## Arsitektur Model
Model terdiri dari Encoder BiLSTM, Attention Mechanism, dan Decoder LSTM. Encoder menghasilkan representasi konteks dua arah, Attention menghitung bobot relevansi token, dan Decoder menghasilkan token target langkah demi langkah.

## Struktur Repository
- data: korpus paralel
- notebooks: notebook pelatihan
- src: definisi model, preprocessing, training, evaluasi
- results: checkpoint, grafik, tabel, prediksi
- README.md: dokumentasi utama

## Instalasi
```
git clone https://example.com/repo
cd NMT-BatakToba
pip install -r requirements.txt
```

Google Colab:
```
pip install torch datasets evaluate sentencepiece matplotlib scikit-learn tqdm
```

## Menjalankan Pelatihan
```
python train.py --data data/corpus_batak.csv --epochs 100 --batch_size 64
```

## Evaluasi Model
```
python evaluation.py --checkpoint results/best_seq2seq.pt --data data/corpus_batak.csv
```

## Contoh Output
Input: akan tetapi, terdapat juga keluarga miskin yang terpaksa menjual aset  
Output: naeng alai, tardapot musem tondong pogos na tarabuk manggadis aset

Input: makan di hari minggu
Output: mangan i ari minggu


## Tujuan Proyek
- Memberikan baseline penelitian untuk bahasa daerah low-resource
- Menghasilkan evaluasi komprehensif BLEU dan ROUGE

## Kepentingan Proyek
Bahasa Batak Toba termasuk kategori terancam punah. Model ini diharapkan mendukung pelestarian bahasa daerah.

## Referensi
[1] I. Sutskever et al., Sequence to Sequence Learning with Neural Networks, NIPS, 2014.  
[2] M. T. Luong et al., Effective Approaches to Attention-based Neural Machine Translation, EMNLP, 2015.  
[3] H. Susanto et al., Replicable Benchmarking of Neural Machine Translation on Low-Resource Local Languages in Indonesia, ACL, 2023.  
[4] B. O. S. Miranda et al., Machine Translation Indonesian Bengkulu Malay Using NMT-LSTM, 2024.  
[5] S. Sakinah et al., Neural Machine Translation Sunda Loma–Sunda Halus Using LSTM, 2024.  
[6] D. Sulistyo et al., An Enhanced Pivot-Based Neural Machine Translation for Low-Resource Languages, IJAIN, 2025.
