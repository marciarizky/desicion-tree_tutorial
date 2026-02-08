# desicion-tree\_tutorial

This is my simple desicion tree tutorial



\## Cara Kerja Decision Tree

Decision Tree adalah algoritma pembelajaran mesin yang menggunakan struktur pohon untuk membuat keputusan berdasarkan fitur input. Setiap node internal mewakili fitur, cabang mewakili aturan keputusan, dan setiap daun mewakili hasil.



\## Komentar dalam Kode

Berikut adalah penjelasan kode dengan komentar:

```python

import warnings

warnings.filterwarnings('ignore')  # Mengabaikan peringatan yang tidak diperlukan



import numpy as np

import pandas as pd



from sklearn import datasets

from sklearn.metrics import accuracy\_score

from sklearn.tree import DecisionTreeClassifier



\# Memuat dataset iris

iris = datasets.load\_iris()

data = pd.DataFrame(data= np.c\_\[iris\['data'], iris\['target']],

&nbsp;                    columns= iris\['feature\_names'] + \['target'])



\# Memisahkan fitur (X) dan target (y)

X = data.drop('target', axis=1)

y = data\[\['target']]



from sklearn.model\_selection import train\_test\_split

\# Membagi data menjadi data latih dan data uji

X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)



\# Membuat model Decision Tree

model = DecisionTreeClassifier()

model.fit(X\_train, y\_train)  # Melatih model dengan data latih



\# Memprediksi data uji

y\_pred\_dt = model.predict(X\_test)



\# Menghitung akurasi model

print('Akurasi', accuracy\_score(y\_test, y\_pred\_dt))

```



\## Langkah-langkah Membangun Decision Tree

1\. \*\*Memuat Dataset\*\*: Gunakan dataset yang relevan, seperti dataset iris dari `sklearn`.

2\. \*\*Memisahkan Fitur dan Target\*\*: Pisahkan data menjadi fitur (X) dan target (y).

3\. \*\*Membagi Data\*\*: Bagi dataset menjadi data latih dan data uji menggunakan `train\_test\_split`.

4\. \*\*Membuat Model\*\*: Inisialisasi model Decision Tree menggunakan `DecisionTreeClassifier`.

5\. \*\*Melatih Model\*\*: Latih model dengan data latih menggunakan `fit`.

6\. \*\*Memprediksi\*\*: Gunakan model untuk memprediksi data uji.

7\. \*\*Evaluasi\*\*: Hitung akurasi model menggunakan `accuracy\_score`.



Dengan langkah-langkah ini, Anda dapat membangun dan mengevaluasi model Decision Tree sederhana.



