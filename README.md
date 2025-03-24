Metro Ağı Yöneticisi;
Bu proje, bir metro ağı simülasyonu oluşturmak ve iki belirli istasyon arasında en az aktarma yaparak veya en hızlı rotayı bulmak amacıyla geliştirilmiştir. Uygulama, BFS (Breadth-First Search) algoritması ile en az aktarmalı rotayı ve A* algoritması ile en hızlı rotayı hesaplar.

İçindekiler;
Proje Hakkında
Kurulum
Kullanım
Kod Yapısı
Algoritmalar
Test Senaryoları
Lisans

Proje Hakkında;
Bu proje, bir metro ağı yöneticisi yazılımıdır. Kullanıcılar, başlangıç ve hedef istasyonları belirleyerek bu istasyonlar arasında en az aktarma yaparak veya en hızlı şekilde nasıl seyahat edileceğini öğrenebilirler. BFS (Breadth-First Search) algoritması, en az aktarmalı rotaları bulmak için kullanılırken, A* algoritması en hızlı rotaları hesaplamak için kullanılır.

Örnek olarak, Süleymaniye, Vefa, Saraçhane, Unkapanı gibi istasyonlar ve hatlar ile simülasyon yapılmıştır. Uygulama, farklı metro hatlarında aktarma noktalarını ve sürelerini yönetebilir.

Kurulum;
Bu projeyi çalıştırabilmek için Python 3.x sürümüne ihtiyacınız olacak. Python'un yüklü olup olmadığını aşağıdaki komutla kontrol edebilirsiniz:

bash
Kopyala
python --version
Eğer Python yüklü değilse, Python'un resmi sitesinden Python'u indirip yükleyebilirsiniz.

1. Depoyu İndirme
Projeyi bilgisayarınıza indirmek için terminal veya komut istemcisinde şu komutu çalıştırabilirsiniz:

bash
Kopyala
git clone https://github.com/kullanici-adi/metro-agi.git
Alternatif olarak, projeyi zip olarak indirip çıkartabilirsiniz.

2. Gereksinimler
Proje, Python'un standart kütüphanelerini kullanmaktadır, bu nedenle ek bir bağımlılık kurmanıza gerek yoktur. Kodun çalışması için sadece Python 3.x sürümü gereklidir.

3. Uygulamayı Çalıştırma
Projeyi çalıştırmak için şu adımları takip edebilirsiniz:

Proje dizinine gidin:

bash
Kopyala
cd metro-agi
Uygulamayı çalıştırın:

bash
Kopyala
python metro_agi.py
Eğer Python 3.x yüklü ise:

bash
Kopyala
python3 metro_agi.py
Uygulama, metro ağını kuracak ve istasyonlar arasında rota hesaplamalarını başlatacaktır.

Kullanım
İstasyon Ekleme
Yeni bir istasyon eklemek için istasyon_ekle fonksiyonunu kullanabilirsiniz. Her istasyon, idx (istasyon kodu), ad (istasyon adı) ve hat (metro hattı adı) ile tanımlanır.

python
Kopyala
metro.istasyon_ekle("S1", "Süleymaniye", "Mavi Hat")
Bağlantı Ekleme
İki istasyon arasındaki bağlantı eklemek için baglanti_ekle fonksiyonu kullanılır. Bu fonksiyon, iki istasyon arasındaki seyahat süresini belirler.

python
Kopyala
metro.baglanti_ekle("S1", "S2", 5)  # Süleymaniye -> Vefa
Rota Bulma
En Az Aktarma: En az aktarmalı rotayı bulmak için en_az_aktarma_bul fonksiyonunu kullanabilirsiniz. Bu fonksiyon, başlangıç ve hedef istasyonlarını alarak BFS algoritmasıyla en az aktarma ile rota hesaplar.

python
Kopyala
rota = metro.en_az_aktarma_bul("Süleymaniye", "Unkapanı")
En Hızlı Rota: En hızlı rotayı bulmak için en_hizli_rota_bul fonksiyonunu kullanabilirsiniz. Bu fonksiyon, başlangıç ve hedef istasyonlarını alarak A* algoritması ile en hızlı rota ve süreyi hesaplar.

python
Kopyala
rota, sure = metro.en_hizli_rota_bul("Süleymaniye", "Unkapanı")
Kod Yapısı
Istasyon Sınıfı
Özellikler:

idx: İstasyonun benzersiz kimliği.

ad: İstasyon adı.

hat: İstasyonun ait olduğu hat adı.

komsular: İstasyonun komşu istasyonları ve bağlantı süreleri.

Metodlar:

komsu_ekle: İstasyonun komşularını ve sürelerini ekler.

MetroAgi Sınıfı
Özellikler:

istasyonlar: İstasyonların tutulduğu sözlük.

hatlar: Hatlar ve o hatlara ait istasyonlar.

Metodlar:

istasyon_ekle: Yeni bir istasyon ekler.

baglanti_ekle: İki istasyon arasına bağlantı ekler.

en_az_aktarma_bul: BFS algoritması ile en az aktarmalı rota hesaplar.

en_hizli_rota_bul: A* algoritması ile en hızlı rota ve süreyi hesaplar.

Algoritmalar
BFS (Breadth-First Search)
BFS algoritması, grafiği katmanlar halinde gezerek her istasyonu birer "katman" olarak ele alır ve ilk hedefe ulaşan rotayı döndürür. Bu algoritma, en az aktarma yapan rotayı bulmak için kullanılır.

A* (A Star) Algoritması
A* algoritması, mevcut durumu ve hedefi göz önünde bulundurarak, en hızlı rotayı ve en kısa süreyi hesaplar. Heuristic fonksiyonu, hedefe ne kadar yakın olduğumuzu belirlemek için kullanılır. Bu projede, basitlik açısından sabit bir değer (0) kullanılmıştır.

Test Senaryoları
Aşağıda, metro ağı üzerindeki bazı test senaryolarını bulabilirsiniz. Bu senaryolar, belirli istasyonlar arasında en az aktarmalı ve en hızlı rotaların hesaplanmasını sağlar.

Süleymaniye'den Unkapanı'na:

En az aktarmalı rota ve en hızlı rota hesaplanır.

Vefa'dan Saraçhane'ye:

İki istasyon arasında en kısa ve en hızlı rota hesaplanır.

Her bir senaryo için rota ve süreler ekrana yazdırılacaktır.

Lisans
Bu proje, MIT Lisansı altında lisanslanmıştır.
