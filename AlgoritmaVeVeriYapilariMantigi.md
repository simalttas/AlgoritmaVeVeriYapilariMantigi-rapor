ALGORİTMA VE VERİ YAPILARI MANTIĞI

Veri yapıları; verinin bilgisayar belleğinde en düzenli, erişilebilir ve verimli şekilde saklanmasını, organize edilmesini ve işlenmesini sağlayan temel yapı taşlarıdır. Bilgisayar kaynakları (bellek ve işlemci) sınırsız değildir; bu yüzden veriyi rastgele depolamak yerine, üzerinde yapılacak işlemlere en uygun biçimde biçimlendirmek gerekir.

# Veri Yapıları Neden Vardır?

- Yanlış bir veri yapısı seçmek, milyonlarca veri içeren bir arama işlemini dakikalar süren bir sürece dönüştürebilir. Doğru veri yapısı ise aynı işlemi milisaniyeler içinde tamamlamanızı sağlar.

- Hayattaki her bilgi düz bir liste halinde durmaz. Örneğin bir bilgisayarın dosya sistemi hiyerarşiktir (Ağaç yapısı gerektirir). Veri yapıları, bu karmaşık ilişkileri koda mantıklı bir şekilde aktarmamızı sağlar.

- Algoritma bir problemi çözmek için izlenen adım adım yoldur, ancak bu yolun üzerinde çalıştığı malzeme veridir. Verinin bellekte nasıl yerleştiği, algoritmanın çalışma hızını doğrudan etkiler.

- Standartlaştırılmış veri yapıları (Yığın, Kuyruk, Listeler vb.), her projede tekerleği yeniden icat etmek yerine, test edilmiş ve optimize edilmiş mimarileri kullanarak daha temiz, modüler ve hata oranı düşük kodlar yazmanıza imkan tanır.

## Big-O Mantığı Nedir?

Bir algoritmanın girdi boyutu büyüdükçe çalışma süresinin veya bellek tüketiminin nasıl ölçekleneceğini (en kötü senaryoda nasıl bir eğriyle artacağını) matematiksel olarak ifade eden standart bir yöntemdir.

Bilgisayarların işlem gücü sürekli artsa da, verimsiz yazılmış bir algoritma büyük veri setleri karşısında en güçlü işlemcileri bile dakikalar içinde kitleyebilir. Big-O, donanım hızından bağımsız olarak kodun kendi matematiksel verimliliğini ölçmemizi sağlar.

# Big-O'nun Temel Mantığı Nasıl Çalışır?
- >En Kötü Senaryo (Worst-Case): 
Big-O genellikle olası en kötü durumu baz alır. Örneğin, bir listede aradığınız eleman listenin en sonundaysa veya hiç yoksa algoritmanın yapacağı maksimum işlem sayısı hesaplanır.

->Sabitleri ve Küçük Terimleri İhmal Etme: 
Bir algoritmanın çalışma süresi T(n) = 3n^2 + 5n + 2 gibi bir ifadeyle ölçülse bile, 'n' sonsuza giderken 'n^2' dışındaki terimler ve katsayılar (3 ve 5 gibi) önemsizleşir. Bu yüzden bu ifade O(n^2) olarak sadeleştirilir.

#En sık karşılaşılan Big-O Karmaşıklıkları

->Sabit Zaman (Constant)	
Girdi boyutundan bağımsız olarak işlem her zaman aynı sürede biter.

Örn: Dizi (Array) içindeki bir elemana indeksiyle doğrudan erişmek.

->Logaritmik Zaman (Logarithmic)	
Her adımda problem boyutu yarıya iner. Çok büyük verilerde inanılmaz hızlıdır.

Örn: İkili Arama (Binary Search).

->Doğrusal Zaman (Linear)
Girdi boyutu (n) arttıkça işlem süresi de aynı oranda doğru orantılı artar.

Örn: Sırasız bir listede tek bir döngüyle arama yapmak.

->Doğrusal- Logaritmik
Genellikle veriyi bölerek sıralayan gelişmiş algoritmaların performansıdır.

Örn: Merge Sort veya Quick Sort (ortalama durum).

->Karesel Zaman (Quadratic)
Genellikle iç içe döngülerin (nested loops) olduğu durumlarda ortaya çıkar. Büyük verilerde tehlikelidir.

Örn: Kabarcık Sıralaması (Bubble Sort).

# Performans Analizinde Nasıl Kullanılır?
->Ölçeklenebilirlik Testi: 
Kod 10 veriyle test edildiğinde hızlı çalışabilir; ancak şirket veritabanındaki 10 milyon kayıtla çalıştırıldığında sistemin çöküp çökemeyeceği Big-O analiziyle önceden öngörülür.

->Zaman ve Alan (Time & Space) Dengesi: Algoritma analizinde sadece Zaman Karmaşıklığı (Time Complexity) değil, aynı zamanda Alan Karmaşıklığı (Space Complexity) da incelenir. Bazen hızı artırmak için ekstra bellek harcayan (O(n) alan kullanan) bir veri yapısı seçmeniz gerekebilir.

#Array(Dizi)

-Mantığı: 
Verilerin bellekte ardışık (yan yana) olarak saklandığı sabit boyutlu (veya dinamik olarak büyüyebilen) yapılardır.

-Avantajı: 
İndeks numarası (örneğin dizi[5]) biliniyorsa elemana O(1) yani anında erişim sağlar.

-Dezavantajı: 
Boyutu sabittir (veya büyütülmesi maliyetlidir). Araya yeni bir eleman eklemek veya baştan bir eleman silmek, diğer tüm elemanların kaydırılmasını gerektirdiği için O(n) maliyetlidir.

-Ne Zaman Kullanılır?
 Veri sayısı bellise ve elemanlara sürekli indeks numaralarıyla hızlıca erişmeniz gerekiyorsa.

##Linked List (Bağlı Liste)

-Mantığı: 
Veriler bellekte ardışık durmaz. Her eleman bir sonraki elemanın bellek adresini (işaretçi/pointer) tutan düğümler (node) şeklinde zincir gibi birbirine bağlanır.

-Avantajı:
 Boyutu esnektir; bellekte boş yer buldukça genişler. Araya veya başa eleman eklemek/silmek çok hızlıdır (O(1)), çünkü sadece işaretçileri değiştirmek yeterlidir.

-Dezavantajı: 
İstediğiniz bir elemana ulaşmak için baştan başlayıp tek tek zinciri takip etmeniz gerekir, bu yüzden rastgele erişim yavaştır (O(n)). Ayrıca her düğüm adres tuttuğu için ekstra bellek harcar.

-Ne Zaman Kullanılır? 
Boyutunun sürekli değişeceği, ekleme ve silme işlemlerinin yoğun olduğu durumlarda.

##Stack (Yığın)

-Mantığı:
 LIFO (Last In, First Out - Son Giren İlk Çıkar) prensibiyle çalışır. Tıpkı üst üste dizilmiş tabaklar gibidir; en son koyduğunuz tabak en üsttedir ve ilk siz alırsınız.

-Temel İşlemleri:
 Push (üst üste ekleme), Pop (en üsttekini çıkarma), Peek (en üsttekine bakma).

-Ne Zaman Kullanılır? 
Geri alma (Undo/Redo) mekanizmalarında, fonksiyon çağrılarının takip edilmesinde (Call Stack) veya parantez kontrolü gereken durumlarda.

##Queue (Kuyruk)

-Mantığı:
 FIFO (First In, First Out - İlk Giren İlk Çıkar) prensibiyle çalışır. Tıpkı market kasası kuyruğu gibidir; ilk gelen kuyruktan ilk çıkar.

-Temel İşlemleri: 
Enqueue (kuyruğun sonuna ekleme), Dequeue (kuyruğun başından çıkarma).

-Ne Zaman Kullanılır? 
Yazdırma kuyrukları (Printer Spooler), asenkron görev yönetimleri veya verilerin sırayla işlenmesi gereken senaryolarda.

##HashMap / Hash Table (Sözlük / Eşleme Tablosu)

-Mantığı: 
Verileri Anahtar-Değer (Key-Value) ikilileri şeklinde saklar. Örneğin {"ogrenci_no": 123} gibi. Bir "Hash Fonksiyonu" kullanarak anahtarı doğrudan verinin bellekteki adresine çevirir.

-Avantajı: 
Veri seti ne kadar büyük olursa olsun, anahtarını biliyorsanız arama, ekleme ve silme işlemleri ortalama olarak O(1)(sabit zamanda) yani inanılmaz hızlı gerçekleşir.

-Dezavantajı: 
Sıralı veri tutmazlar (dağınıktır) ve bazen farklı anahtarlar aynı hash değerini üretebilir ("çakışma / collision") ki bu da performansı çok az da olsa etkileyebilir.

-Ne Zaman Kullanılır? 
Bir veriyi benzersiz bir kimlikle (ID, e-posta, kullanıcı adı) eşleştirip saniyesinde bulmanız gerektiğinde (örn: veritabanı indeksleri, cache sistemleri).

#Hangi Durumda Hangisini Seçmelisiniz?

-Verilerin sayısı belli ve kaçıncı sırada olduklarıyla ilgileniyorsanız: Array

-Sürekli eleman ekleyip çıkaracaksanız ve sıralı bir zincire ihtiyacınız varsa:Linked List

-İşlemleri "en son gelen önce çıkacak" veya "ilk gelen ilk çıkacak" kuralıyla yönetecekseniz: Stack veya Queue

-Verilere bir isim, ID veya anahtar kelimeyle anında ve en hızlı şekilde ulaşmak istiyorsanız: HashMap


