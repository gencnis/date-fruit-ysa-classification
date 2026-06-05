\# Rapor Notları



\## Proje Bilgileri



Ders: Hesaplamalı Zeka  

Öğrenci: Nisanur Genç  

Öğrenci No: 258273002044  

Yöntem: Yapay Sinir Ağı (YSA)  

Veri Seti: Date Fruit Dataset  

Problem Türü: Çok sınıflı sınıflandırma  



\## Veri Seti



Örnek sayısı: 898  

Giriş özelliği sayısı: 34  

Hedef değişken: Class  

Sınıf sayısı: 7  



Veri setindeki sınıflar:

\- BERHI

\- DEGLET

\- DOKOL

\- IRAQI

\- ROTANA

\- SAFAVI

\- SOGAY



Eksik değer: Yok



\## Model



Model türü: Yapay Sinir Ağı  

Giriş katmanı: 34 özellik  

Gizli katman 1: 64 nöron, ReLU  

Dropout: 0.20  

Gizli katman 2: 32 nöron, ReLU  

Dropout: 0.20  

Çıkış katmanı: 7 nöron, Softmax  



Optimizer: Adam  

Learning rate: 0.001  

Loss function: sparse categorical crossentropy  

Epoch: 100 maksimum  

EarlyStopping patience: 15  

Batch size: 32  

Train-test split: %80 eğitim, %20 test  

Scaling: StandardScaler  



\## Sonuçlar



Test Accuracy: 0.9167  

Macro Avg Precision: 0.9164  

Macro Avg Recall: 0.8904  

Macro Avg F1-Score: 0.8991  

Weighted Avg Precision: 0.9155  

Weighted Avg Recall: 0.9167  

Weighted Avg F1-Score: 0.9125  



\## Sınıf Bazlı Notlar



En başarılı sınıflar:

\- IRAQI

\- ROTANA

\- SAFAVI



Daha zayıf kalan sınıflar:

\- DEGLET

\- SOGAY



DEGLET recall: 0.6500  

SOGAY recall: 0.6842  



Confusion matrix sonucuna göre DEGLET sınıfına ait bazı örnekler DOKOL olarak tahmin edilmiştir. SOGAY sınıfında da DEGLET, DOKOL ve ROTANA sınıflarıyla karışma görülmüştür.



\## Rapor Görselleri



outputs/class\_distribution.png  

outputs/training\_validation\_accuracy.png  

outputs/training\_validation\_loss.png  

outputs/confusion\_matrix.png  



\## Rapor Tabloları



outputs/summary\_results.csv  

outputs/classification\_report.csv

