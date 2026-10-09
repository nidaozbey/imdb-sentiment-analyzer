# 🎬 IMDB Movie Reviews Sentiment Analysis (Duygu Analizi)

Bu proje, 50.000 adet İngilizce IMDB film yorumunu inceleyerek yorumların "Olumlu" (Positive) mu yoksa "Olumsuz" (Negative) mu olduğunu tahmin eden bir Doğal Dil İşleme (NLP) ve Makine Öğrenmesi modelidir. 

## 📊 Veri Seti
Bu projede kullanılan 50.000 yorumluk IMDB veri setine [Kaggle üzerinden buradan](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews) ulaşabilirsiniz. Kodları kendi ortamınızda çalıştırmak için veriyi indirip `.ipynb` dosyasıyla aynı dizine koymanız yeterlidir.

## 🖥️ Web Arayüzü (Gradio UI)
Kullanıcıların kendi film yorumlarını test edebilmeleri için Gradio kullanılarak aşağıdaki interaktif web arayüzü tasarlanmıştır:

![Uygulama Arayüzü](arayüz.png)

## 🧠 Proje Adımları (Pipeline)

1. **Veri Ön İşleme (Text Preprocessing):**
   - HTML etiketleri (`<br />`) temizlendi.
   - Tüm metinler küçük harfe (lowercase) çevrildi.
   - Regex kullanılarak noktalama işaretleri ve özel karakterler kaldırıldı.
2. **Vektörizasyon (Bag of Words):**
   - Makinenin metinleri anlayabilmesi için `CountVectorizer` kullanılarak metinler sayısal matrislere dönüştürüldü. RAM optimizasyonu için en çok geçen 5000 kelime (`max_features=5000`) baz alındı.
3. **Veri Bölme (Train/Test Split):**
   - Modelin ezberlemesini (overfitting) önlemek için veri seti %80 Eğitim (Train) ve %20 Test olarak ayrıldı.
4. **Model Eğitimi:**
   - Sınıflandırma algoritması olarak `Logistic Regression` kullanıldı.

## 🚀 Sonuçlar
Model, daha önce hiç görmediği 10.000 test yorumu üzerinde çalıştırıldı ve başarı oranı **%88.3** olarak ölçüldü.

## 🛠️ Kullanılan Teknolojiler
- Python
- Pandas (Veri Analizi)
- Scikit-Learn (Makine Öğrenmesi)
- Gradio (Arayüz Geliştirme)
- Google Colab
