# Sosyal Ağ Yönetimi Projesi

## Proje Tanımı
Bu proje, C dili kullanılarak bir sosyal ağ yönetimi sistemini modellemektedir.  
Kullanıcılar, **Red-Black Tree** veri yapısında saklanır.  
Arkadaşlık ilişkileri ise, her kullanıcının bir dizi arkadaş referansı tutmasıyla **graph (graf)** yapısında yönetilir.  
Amaç, bir sosyal ağdaki kullanıcılar ve arkadaşlık ilişkileri üzerinde etkili işlemler yapmaktır.

## Kullanım Amacı
- Kullanıcı eklemek ve onları hızlıca aramak
- Arkadaşlık ilişkilerini kurmak ve yönetmek
- Kullanıcılar arasında ortak arkadaşları bulmak
- Belirli bir kullanıcının ulaşabileceği kişileri keşfetmek (etki alanı)
- Toplulukları (bağlı bileşenleri) tespit etmek
- Verileri bir dosyaya kaydederek dışa aktarmak (`veriseti.txt`)

Bu yapı, gerçek bir sosyal medya platformunun temel altyapısını modellemektedir.

## Nasıl Çalışır?

###  Kullanıcılar Red-Black Tree'ye Eklenir
Kullanıcılar, ID numaralarına göre Red-Black Tree'ye eklenir.  
Bu sayede:
- Kullanıcılar **hızlı** bir şekilde eklenir,
- Kullanıcılar **hızlı** bir şekilde bulunur.

###  Arkadaşlıklar Graph Yapısında Tutulur
Her kullanıcı bir arkadaş listesine sahiptir.  
İki kullanıcı arkadaş olduğunda, birbirlerinin listelerine eklenirler.  
Bu yapı, sosyal ağdaki bağlantıları gösterir.

###  DFS (Derinlik Öncelikli Arama) ile Arkadaşlar Listelenir
Bir kullanıcı seçildiğinde:
- DFS algoritması çalıştırılır.
- Belirtilen derinliğe kadar arkadaşları ve onların arkadaşları bulunur.

Örneğin:
- 0. derinlikte kendisi,
- 1. derinlikte doğrudan arkadaşları,
- 2. derinlikte arkadaşlarının arkadaşları listelenir.

###  Ortak Arkadaşlar Analiz Edilir
İki kullanıcı seçilerek:
- İki kullanıcının arkadaş listeleri karşılaştırılır.
- Ortak olanlar bulunup ekrana yazdırılır.

###  Etki Alanı Hesaplanır
Bir kullanıcı seçildiğinde:
- DFS ile bu kullanıcının ulaşabileceği tüm kullanıcılar taranır.
- Kaç kişiye etkisinin ulaştığı hesaplanır.

Bu, sosyal ağdaki bir kullanıcının "network reach" etkisini gösterir.

###  Topluluk (Connected Component) Tespiti Yapılır
Tüm kullanıcılar üzerinde:
- Her bağlı bileşen (topluluk) bulunur.
- Birbirine ulaşabilen kullanıcılar topluluk olarak listelenir.

Bu özellik, sosyal ağda izole edilmiş grupları veya toplulukları keşfetmek için kullanılır.

###  Veriler Dosyaya Kaydedilir
Program sonunda:
- Tüm kullanıcılar ve arkadaşlık ilişkileri `veriseti.txt` dosyasına yazılır.
- Dosyada önce kullanıcılar listelenir, ardından arkadaşlık ilişkileri sıralanır.


## Özellikler
- Red-Black Tree ile kullanıcı yönetimi
- Graph yapısıyla arkadaşlık ilişkisi yönetimi
- DFS tabanlı arama ve analiz
- Ortak arkadaş bulma
- Etki alanı hesaplama
- Topluluk (connected component) keşfi
- Veri dışa aktarımı

## Dosyalar
- `sosyalag.c` : Ana kaynak kod dosyası
- `veriseti.txt` : Program sonunda oluşturulan veri seti dosyası

## Gereksinimler
- GCC derleyicisi
- Temel C programlama bilgisi

## Lisans
Bu proje eğitim amaçlı geliştirilmiştir.

