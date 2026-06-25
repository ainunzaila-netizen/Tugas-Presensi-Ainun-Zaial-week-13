**1. Apa yang dimaksud dengan State, Action, dan Reward dalam Reinforcement Learning?**
Jawaban : a. Yang dimaksud State adalah merupakan kondisi atau situasi saat ini berdasarkan agen
             <img width="97" height="114" alt="image" src="https://github.com/user-attachments/assets/b6c40e53-1ff5-4c65-a024-546d21e25db3" />
             Setiap kotak memiliki nomor state tertentu.
          b. Yang dimaksud Action adalah merupakan aksi yang akan dipilih agen untuk mencapai tujuan tindakan yang dapat dilakukan agen
             Pada FrozenLake terdapat 4 aksi:
             0 = left
             1 = down
             2 = right
             3 = up
          c. Yang dimaksud Reward adalah merupakan sebuah nilai untuk mengukur keberhasilan aksi agen yang digunakan sebagai indikator keberhasilan agen
             Contoh Mencapai goal rewardnya 1 sedangkan selain goal rewardnya 0
             
**2. Apa fungsi dari Learning Rate (α)?**
Jawaban : Fungsi dari Learning Rate adalah mengatur seberapa besar informasi baru mempengaruhi nilai Q yang lama.
          <img width="631" height="43" alt="image" src="https://github.com/user-attachments/assets/f407ba84-7e3d-40fb-af5d-437815a2b64b" />
          Artinya:
          80% informasi baru digunakan untuk memperbarui Q-Value.
          Nilai lama masih dipertahankan sebagian.

          Jika α besar:
          Belajar lebih cepat.
          Bisa menjadi kurang stabil.

          Jika α kecil:
          Belajar lebih lambat.
          Lebih stabil.
   
**3. Apa fungsi dari Discount Factor (γ)?**
   Jawaban : Discount Factor (γ) menentukan seberapa penting reward di masa depan dibanding reward saat ini.
             <img width="577" height="34" alt="image" src="https://github.com/user-attachments/assets/e85f332f-73c2-4fb0-b749-ddd0d1f72f35" />
             Artinya reward masa depan masih dianggap sangat penting sebesar 95%.
             Jika γ mendekati 1:
             Agent berpikir jangka panjang.
             Mencari jalur terbaik menuju goal.
             Jika γ mendekati 0: Agent hanya fokus pada reward langsung.
   
**4. Mengapa digunakan metode Exploration dan Exploitation?**
   Jawaban : a. Exploration adalah agen mencoba aksi secara acak. Tujuannya untuk menemukan jalur baru dan Mengumpulkan pengalaman.
                <img width="642" height="61" alt="image" src="https://github.com/user-attachments/assets/1f67506c-6726-4dca-8971-eff77ea30b38" />
             b. Exploitation adalah agen memilih aksi terbaik berdasarkan Q-Table.
                <img width="454" height="39" alt="image" src="https://github.com/user-attachments/assets/a64cf6e8-0942-422e-9f0d-9d1c01575ce8" />
                Tujuannya memanfaatkan pengetahuan yang telah dipelajari.
             c. Alasannya Jika hanya Exploration:
                Jika hanya Exploration:
                Agent terus mencoba secara acak.
                Sulit mencapai solusi optimal.

                Jika hanya Exploitation:
                Agent bisa terjebak pada solusi yang belum tentu terbaik.
             Karena itu digunakan kombinasi keduanya agar agent dapat belajar secara efektif.
   
**5. Bagaimana perubahan nilai reward setelah training 2000 episode?**
   Jawaban : Pada awal proses training, nilai reward cenderung rendah dan tidak stabil karena agent masih banyak melakukan exploration (mencoba berbagai aksi secara acak). Akibatnya, agent sering gagal mencapai tujuan sehingga reward yang diperoleh sebagian besar bernilai 0.

Seiring bertambahnya jumlah episode, agent mulai mempelajari lingkungan melalui pembaruan nilai pada Q-Table. Dengan semakin baiknya pengetahuan yang dimiliki agent, frekuensi keberhasilan mencapai goal meningkat sehingga nilai reward juga meningkat.

Setelah mencapai 2000 episode, reward menjadi lebih tinggi dan lebih stabil dibandingkan awal training. Hal ini menunjukkan bahwa agent telah berhasil mempelajari strategi atau jalur terbaik menuju goal dan lebih sering memperoleh reward maksimal.

**Tugas Lanjutan**
Modifikasi program sehingga:
1. Menggunakan environment Taxi-v3 Menampilkan rata-rata reward setiap 100 episode Membandingkan hasil training 1000, 2000, dan 5000 episode
   1000 episode:
   <img width="1392" height="340" alt="image" src="https://github.com/user-attachments/assets/d2591fa4-2ca4-4a84-a92e-015d237f889e" />
   <img width="277" height="1003" alt="image" src="https://github.com/user-attachments/assets/61f9d1ef-5491-4dd9-a487-b62ba97856ed" />
   <img width="1221" height="588" alt="image" src="https://github.com/user-attachments/assets/e0e93fff-b08a-41ee-97e6-db63a103b4a4" />
 
   2000 episode:
   <img width="1423" height="343" alt="image" src="https://github.com/user-attachments/assets/776aca85-3207-4cc7-ac51-8e97b393b6f7" />
   <img width="274" height="997" alt="image" src="https://github.com/user-attachments/assets/814ffd19-7251-4e2e-9249-7fb23d44ec97" />
   <img width="1348" height="583" alt="image" src="https://github.com/user-attachments/assets/ee5ed1d9-1153-44a3-a632-ac70c634d14e" />

   5000 episode:
   <img width="1398" height="325" alt="image" src="https://github.com/user-attachments/assets/843bb569-0c46-49c4-8376-8188e7087aef" />
   <img width="261" height="1006" alt="image" src="https://github.com/user-attachments/assets/15e0b583-73ff-43c5-89ee-da7a2dc351e8" />
   <img width="1254" height="586" alt="image" src="https://github.com/user-attachments/assets/f7af1005-3318-42e4-8e42-ecacc0da1f7b" />
 
   Perbandingan 1000, 2000, 5000 episode.
   Berdasarkan percobaan, semakin banyak jumlah episode training maka performa agent semakin baik. Training 1000 episode sudah mampu mempelajari lingkungan dasar, namun masih terdapat kesalahan. Pada 2000 episode reward meningkat dan lebih stabil. Pada 5000 episode agent telah mendekati policy optimal sehingga memperoleh rata-rata reward tertinggi dan mampu menyelesaikan tugas Taxi-v3 dengan lebih efektif.  
   
