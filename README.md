# LSTM ile Doğal Dil İşleme Projesi

> Eldeki şiir verilerinden yeni şiirler üreten veri setine yeni bir veri eklendiğinde herhangi bir değişikliğe gerek kalmadan çalışmaya devam eden dinamik bir uygulama geliştirdim. Aşağıdaki görselde genel mantığa yer verdim.


![image](https://user-images.githubusercontent.com/32402864/112366753-3c7d1b80-8cea-11eb-9ec5-411e22703071.png)

##  1. Aşama: Veri setini programlama diline aktarıyoruz.

* İhtiyacımız olabilecek bazı önemli ve gerekli python kütüphanelerini import ediyoruz.
* Şiir verilerini github da aradığım özelliklere sahip bir şekilde buldum ve response ile projeye dahil ettim.
* Verileri data değişkenimize çekiyorum.

## 2. Aşama: Veri setine uyguladığım ön işleme algoritması...

* Sıradaki adım, metin verisini ön işlemeye sokmak ve modelimiz için hazır hale getirmek, dosyamızı okuduktan sonra tüm metni küçük harflere çevirmeli ve kelimelerine ayırmalıyız. Ayrıca noktalama işaretlerinden kurtulmalıyız.
* 91330 kelimelik bir veri setinden 1396 benzersiz verisetine sahip olduğumuzu göreceğiz.

## 3. Aşama: Veri setini ... şeklinde sayısallaştırdım.

* Verilerimizdeki büyük-küçük harf ayrımını kaldırıyoruz.
* Verilerimizi kelimeler halinde parçalama
* Noktalama işaretlerinin arındırılması
* Verileri şifrelenmiş bir şekilde yazdırdım.

## 4. Aşama: LSTM ağını (veya modelini) nasıl oluşturdum, eğittim ve test ettim.

* Verileri eğitim için hazırlıyorum - Prepare Training Data
* Ele aldığımız proje gereği girdi olarak aldığımız bütün veriyi geri verecek şekilde modeli oluşturmalıyız. Bu nedenden dolayı verilerimizi eğitim veya test amaçlı bölmüyor hepsini eğitim için kullanıyoruz.
* Oluşturacağımız model için verilerimizi aynı boyuta getirmemiz gerekiyor, Bu durumda padding metodunu kullanırız.
* Modelimi oluştururken bir embedding katmanı iki lstm katmanı ve bir çıkış katmanı kullandım. 
* Çıkış katmanımda çok sınıflı bir veri kullandığım için aktivasyon fonksiyonu olarak softmax foksiyonunu kullandım. 
* Daha sonra loss fonksiyonu olarak categorical crossentropy ve optimizasyon algoritması olarak Adam algoritmasını, metric olarak da accuracy kullandım.
* Eğitimin her yinelemesinin kaybını hesaplamak için, kategorik çapraz entropiyi kullanacağız. Ayrıca ağımızı optimize etmek için, adam optimizasyonunu, tekrarlayan sinir ağları için genellikle çok iyi bir seçenek olduğundan kullanıyor olucam.

## 5. Aşama: LSTM ağını (veya modeline) yeni veri girişlerinin nasıl yapıldığını açıkladım ve yeni şiir üretimi gerçekleştirdik.
