# eye_disease_clasification
model untuk klasifikasi penyakit pada mata 

**Project Objective:  Klasifikasi Gambar**

**Objective Summary:**
Tujuan dari proyek ini adalah untuk membuat sistem kklasifikasi gambar medis (penyakit pada mata). Sistem akan mengambil sekumpulan gambar sebagai input, menggunakan model deep learning yang telah dilatih sebelumnya (InceptionV3) untuk mengklasifikasikan objek dalam gambar, lalu kelas dan probabilitas yang diprediksi.

**Libraries Used:**
1. **TensorFlow and Keras:**Digunakan untuk pembelajaran mendalam, khususnya untuk tugas klasifikasi gambar.
2. **Pandas:** Digunakan untuk membuat dan menampilkan hasil dalam format tabel.
3. **Matplotlib:** Digunakan untuk memvisualisasikan gambar dan prediksinya 
4. **Numpy:** Library utama untuk komputasi numerik di Python.
5. **Tqdm:** Progress bar untuk loop dan operasi yang memakan waktu.
6. **Opencv-python (cv2):** Computer vision dan manipulasi gambar.
7. **Pillow (PIL):** Library pengolahan gambar berbasis Python.
8. **Scikit-image:** Pemrosesan gambar berbasis sains.
9. **Scikit-learn:** Library pembelajaran mesin klasik dan statistik.
10. **Kagglehub:** Untuk mengakses model dari KaggleHub secara langsung.

**Execution Process:**

1. **Melakukan load dan preprocessing dataset:**
   - Project di awali dengan melakukan data loading yang berasal dari kaggle : https://www.kaggle.com/datasets/gunavenkatdoddi/eye-diseases-classification
   - Selanjutnya dataset di olah menggunakan bantuan pandas, PIL dan numpy untuk mempermudah proses pengolahan, pemisahan path dan label.
   - Setelah itu dilakukan visualisasi gambar yang akan digunakan untuk mengenali karakteristik dataset.
   - Jumlah gambar pada masing masing kelas juga diperhatikan, dan didapat kesimpulan bahwa dataset yang digunakan cukup balance dengan rata rata 1000 gambar pada masing masing kelas
   - Dilakukan juga data splitting dengan membagi dataset menjadi tiga bagian (training 70%, validasi 15%, dan testing 15%)
   - Kemudian terakhir dilakukan augmentasi gambar dengan menerapkan zoom, rescale, shear, dan rotate untuk memberikan sedikit noise pada gambar.
   
2. **Melakukan modelling dan training model**
   - Modelling dimulai dengan loading pretrained deep learning model (Inception3) menggunakan Tensorflow dan keras. Model ini sudah di training sebelumnya dengan dataset ImageNet
   - Selanjutnya menambahkan pretrained model yang sudah di load ke dalam model sequential, serta ditambahkan layer pooling dan juga dense layer dengan fungsi aktivasi softmax di output layer karena kelas gambar yang ingin diprediksi memiliki 4 kelas.
   - model di compile dan dilatih menggunakan 3000 lebih gambar.
   - dilakukan finetunning pada model untuk memaksimalkan akurasi model

3. **Testing dan evaluasi model**
   - model di evaluasi performanya menggunakan matriks akurasi, f1 score, recall, precision dan confussion matrix untuk mengetahui kemampuan model dalam memprediksi klasifikasi kelas pada gambar.

4. **Menyimpan model ke dalam format saved_model, tfjs, dan tflite**
   - model yang sudah layak dan memiliki akurasi lebih dari 85% disimpan ke dalam format saved_model, tfjs, dan tflite.
 
