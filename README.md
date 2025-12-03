Neural Machine Translation Indonesia ke Bahasa Batak Toba

BiLSTM Encoder Decoder dengan Attention dan Evaluasi BLEU dan ROUGE

Deskripsi Proyek

Repository ini berisi implementasi sistem penerjemahan otomatis dari Bahasa Indonesia ke Bahasa Batak Toba menggunakan pendekatan Neural Machine Translation berbasis BiLSTM dengan mekanisme Attention. Proyek ini dikembangkan untuk mendukung penelitian low resource machine translation dan menyediakan baseline terbuka untuk pasangan bahasa Indonesia dan Batak Toba.

Fitur Utama

Arsitektur BiLSTM Encoder Decoder dengan Attention.

Dataset paralel berjumlah 5050 pasangan kalimat Indonesia dan Batak Toba.

Evaluasi performa menggunakan BLEU 1 sampai 4 dan ROUGE 1, ROUGE 2, ROUGE L.

Penyimpanan model pada epoch tertentu yaitu 10, 40, 70, dan 100.

Output berupa grafik BLEU, grafik ROUGE, tabel BLEU, dan tabel ROUGE.

Model dilatih dengan Early Stopping dan Adam Optimizer.

Arsitektur Model

Model terdiri dari tiga komponen utama yaitu Encoder BiLSTM, Attention Mechanism, dan Decoder LSTM. Encoder menghasilkan representasi konteks dua arah, Attention memberikan bobot relevansi terhadap token sumber, dan Decoder menghasilkan token target secara bertahap berdasarkan hidden state sebelumnya.

Struktur Repository

data berisi file korpus paralel
notebooks berisi file pelatihan model dalam format ipynb
src berisi modul model, utilitas data, pelatihan, dan evaluasi
results berisi checkpoint model, grafik, tabel, dan prediksi
README.md sebagai dokumentasi utama

Instalasi

Clone repository
git clone https or ssh repository
cd NMT-BatakToba

Install dependencies
pip install -r requirements.txt

Atau pada Google Colab
pip install torch datasets evaluate sentencepiece matplotlib scikit-learn tqdm

Menjalankan Pelatihan

Gunakan notebook yang tersedia atau jalankan perintah berikut
python train.py --data data/corpus_batak.csv --epochs 100 --batch_size 64

Checkpoint model otomatis disimpan pada direktori results atau checkpoints sesuai konfigurasi.

Evaluasi Model

Evaluasi BLEU dan ROUGE dapat dilakukan dengan menjalankan
python evaluation.py --checkpoint results or checkpoints best_seq2seq.pt --data data/corpus_batak.csv

Hasil evaluasi disimpan dalam bentuk file CSV dan grafik pada folder results atau metrics.

Contoh Output

Input: apa kabar hari ini
Output: aso do hamu on

Input: saya pergi ke rumah nenek
Output: au pesta tu jabu namboru

Tujuan Proyek

Membangun sistem penerjemahan otomatis bahasa Indonesia ke Batak Toba.

Memberikan baseline penelitian untuk NMT bahasa daerah dengan sumber daya terbatas.

Menghasilkan evaluasi komprehensif menggunakan BLEU dan ROUGE.

Kepentingan Proyek

Bahasa Batak Toba termasuk kategori terancam punah. Dengan adanya model terjemahan dasar berbasis NMT, penelitian ini diharapkan dapat mendukung upaya pelestarian bahasa daerah serta memperluas akses pembelajaran bahasa Batak Toba.

Referensi (Format IEEE)

[1] I. Sutskever, O. Vinyals, and Q. V. Le, Sequence to sequence learning with neural networks, NIPS, 2014.
[2] M. T. Luong, H. Pham, and C. D. Manning, Effective approaches to attention based neural machine translation, EMNLP, 2015.
[3] H. Susanto, A. Diandaru, G. Krisnadhi, A. Purwarianti, and D. Wijaya, Replicable Benchmarking of Neural Machine Translation on Low Resource Local Languages in Indonesia, ACL, 2023.
[4] B. O. S. Miranda, H. Yuliansyah, and M. K. Biddinika, Machine Translation Indonesian Bengkulu Malay Using Neural Machine Translation LSTM, 2024.
[5] S. Sakinah, R. Ramadhan, and Y. Hartono, Neural Machine Translation untuk Bahasa Sunda Loma Sunda Halus Menggunakan Long Short Term Memory, 2024.
[6] D. Sulistyo, A. Wibawa, D. Prasetya, and F. Ahda, An Enhanced Pivot Based Neural Machine Translation for Low Resource Languages, International Journal of Advances in Intelligent Informatics, vol. 11, no. 2, pp. 258 to 274, 2025.
