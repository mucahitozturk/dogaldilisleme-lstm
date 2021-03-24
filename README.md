# LSTM ile Doğal Dil İşleme Projesi

> Eldeki şiir verilerinden yeni şiirler üreten veri setine yeni bir veri eklendiğinde herhangi bir değişikliğe gerek kalmadan çalışmaya devam eden dinamik bir uygulama geliştirdim. Aşağıdaki görselde genel mantığa yer verdim.


![image](https://user-images.githubusercontent.com/32402864/112366753-3c7d1b80-8cea-11eb-9ec5-411e22703071.png)

##  1. Aşama: Veri setinizi programlama diline nasıl aktardınız.

* İhtiyacımız olabilecek bazı önemli ve gerekli python kütüphanelerini import ediyoruz.
* Şiir verilerini github da aradığım özelliklere sahip bir şekilde buldum ve response ile projeye dahil ettim.
* Verileri data değişkenimize çekiyorum.

## 2. Aşama: Veri setine uyguladığınız ön işleme algoritmasını açıklayınız.

* Sıradaki adım, metin verisini ön işlemeye sokmak ve modelimiz için hazır hale getirmek,

-Dosyamızı okuduktan sonra tüm metni küçük harflere çevirmeli, ve kelimelerine ayırmalıyız. Ayrıca noktalama işaretlerinden kurtulmalıyız.

-91330 kelimelik bir veri setinden 1396 benzersiz verisetine sahip olduğumuzu göreceğiz.
