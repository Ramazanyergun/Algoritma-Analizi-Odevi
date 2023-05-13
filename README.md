# Algoritma-Analizi-Odevi
Kısa Sıanv2 Kısım1

Kodun Amacının Açıklanması

Bu kod bir ağırlıklı graf algoritmasıdır. Kod genel olarak bir graf üzerinde dolaşarak bazı metotlar sayesinde en kısa yolu bulmak için kullanılır. 
Kod bloğunda ayrıca çalışma zamanını hesaplayan bir fonksiyonda bulunur.
Aşağıda her bir fonksiyonun çalışma mantığı verilmiştir:

Generate Fonksiyonu: Verilen bir diziye rastgele sayılar atayan bir fonksiyondur. Fonksiyon, size kadar döngü yaparak diziye rastgele sayılar atar. 
Her bir dizi elemanı için rastgele sayı elde edilir. Bu rastgele sayı, (2 * MAX_W) -MAX_W aralığından seçilir. Burada MAX_W, önceden tanımlanmış bir sabittir.

Function1: Bu kod, bir tamsayı dizisini sıralamak için kabarcık sıralama (bubble sort) algoritmasını kullanır.

Function2: fonksiyonu, verilen bir dizideki ardışık pozitif sayıların toplamının en büyük olduğu alt dizinin ortalamasını hesaplayan bir fonksiyondur.

Function3: “Floyd-Warshall" algoritmasını kullanarak tüm çift düğümler arasındaki en kısa yolları hesaplayan bir fonksiyondur.
Floyd-Warshall algoritmasının çalışma mantığını şöyledir:
1.	Başlangıçta, her düğümün kendisiyle olan en kısa yol uzunluğu olarak ayarlanır. Eğer iki düğüm arasında doğrudan bir kenar varsa, bu kenarın ağırlığı kullanılır.
 Eğer doğrudan bir kenar yoksa, yol uzunluğu sonsuz olarak kabul edilir.
2.	Tüm düğümleri çift çift dolaşan bir döngü oluşturulur. 
 Her bir çift (i, j) için, k döngüsü kullanılarak i'den j'ye giden yolun üzerindeki düğümlerden herhangi biri aracılığıyla geçerek daha kısa bir yolun bulunup bulunmadığı kontrol edilir.
3.	İç içe geçmiş k döngüsü, tüm düğümleri k geçişine göre kontrol eder. Yani, her bir (i, j) çifti için k=1'den başlayarak tüm düğümleri dolaşır. 
 Eğer düğüm k, i'den j'ye giden yol üzerinde bulunuyorsa ve bu yolu kullanarak daha kısa bir yol elde edilebiliyorsa, mevcut en kısa yol uzunluğu güncellenir.
4.	İç içe geçmiş döngüler tamamlandığında, en sonunda tüm çiftler arasındaki en kısa yol uzunlukları elde edilmiş olur.
5.	Algoritmanın sonucu olarak, her bir düğüm çifti (i, j) için i'den j'ye olan en kısa yol uzunluğu matrisi elde edilir.
	
Print1: Verilen diziyi ekrana yazdırmak için kullanılır her 10. elemandan sonra bir satır alta inerek devam eder.

Print2: Verilen matrisi ekrana yazdırır. Değeri INF(sonsuz) olan elemanların yerine "INF" yazılırken, diğer değerler üç basamaklı bir sayı olarak gösterilir.

Print3: Verilen ağırlık değerine göre düğümlerin birbirine olan uzaklığını ekrana yazdırır.

Zaman Karmaşıklığının Hesaplanması

1.	generate fonksiyonunun zaman karmaşıklığı:
•	for döngüsü boyunca N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N) olur.

2.	function1 fonksiyonunun zaman karmaşıklığı:
•	İki adet for döngüsü kullanılır.
•	İç içe geçmiş döngülerin her biri N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N^2) olur.

3.	function2 fonksiyonunun zaman karmaşıklığı:
•	Bir for döngüsü kullanılır.
•	Döngü N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N) olur.

4.	function3 fonksiyonunun zaman karmaşıklığı:
•	İki adet iç içe geçmiş for döngüsü kullanılır.
•	İç içe geçmiş döngülerin her biri N kez çalışır.
•	En içteki döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N^3) olur.

5.	print1 fonksiyonunun zaman karmaşıklığı:
•	Bir for döngüsü kullanılır.
•	Döngü N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N) olur.

6.	print2 fonksiyonunun zaman karmaşıklığı:
•	İki adet iç içe geçmiş for döngüsü kullanılır.
•	İç içe geçmiş döngülerin her biri N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N^2) olur.

7.	print3 fonksiyonunun zaman karmaşıklığı:
•	İki adet iç içe geçmiş for döngüsü kullanılır.
•	İç içe geçmiş döngülerin her biri N kez çalışır.
•	Her döngü adımında sabit zamanlı işlemler yapılır.
•	Bu nedenle, zaman karmaşıklığı O(N^2) olur.

Sonuç olarak kodun toplam zaman karmaşıklığı O(N^3) şeklindedir. Bu, kodun giriş boyutu size(N) büyüdükçe zaman karmaşıklığının hızla artacağı anlamına gelir.

Algoritmanın Veriminin arttırılması

Function1’de yapılan sıralama işlemi için kullanılan algoritma (buble sort) yerine daha hızlı olan inserion sort algoritması yazabiliriz. 
Bu düzeltme zaman karmaşıklığında pek bir fark yaratmasa da çalışma süresini kısaltacaktır.
Zaman karmaşıklığını en çok etkileyen kod parçası Funciton2’dir. Bu kod parçası Floyd-Warshall algoritmasını kullanır ve zaman karmaşıklığı O (N^3)’tür. 
Floyd-Warshall algoritması çok yönlü bir algoritmadır ve tüm çiftler arası en kısa yol problemi için özel olarak tasarlanmıştır. 
Bu nedenle, doğrudan Floyd-Warshall algoritmasını daha az zaman karmaşıklığına sahip başka bir algoritma ile değiştirmek mümkün değildir.
Bu durumda kod için function1’de bir düzenleme yapılmıştır. Yapılan bu düzenlemede zaman karmaşıklığı azaltılamasa da çalışma süresi az da olsa azaltılabilmiştir.
