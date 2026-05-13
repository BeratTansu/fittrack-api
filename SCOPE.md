# FitTrack — Proje Kapsamı

## 1. Bu Proje Ne?
FitTrack, kullanıcıların spor programlarını set ve tekrar sayısına 
kadar kaydedip zaman içindeki ilerlemelerini takip etmelerini sağlayan 
bir fitness takip uygulamasıdır.

## 2. Hangi Problemi Çözüyor?
Spora düzenli giden biri olarak, geçen hafta hangi egzersizi kaç kilo 
ile yaptığımı sürekli unutuyordum. "Bugün hangi gün, ne çalışacağım?" 
sorusu her seferinde aklımı karıştırıyordu. FitTrack tam bu problemi 
çözmek için doğdu — her antrenmanı kaydet, ilerlemeyi gör.

## 3. Hedef Kullanıcı
Sporla düzenli ilgilenen, antrenmanlarını sistematik takip etmek 
isteyen herkes. Özellikle ağırlık çalışan, "geçen sefer kaç kilo 
kaldırdım" sorusunu sık soran sporcular.

## 4. MVP Özellikleri

### Kimlik Doğrulama
- E-posta ve şifre ile kullanıcı kaydı
- Giriş yapınca kullanıcıya bir token verilir
- Şifreler veritabanında düz yazı olarak değil, hash'lenmiş halde saklanır
- Sadece geçerli token'ı olan kullanıcılar antrenmanlara erişebilir

### Antrenman Yönetimi
- Antrenman oluştur, listele, güncelle, sil (CRUD)
- Her antrenmanın bir adı, tarihi ve opsiyonel notu olur
- Kullanıcı sadece kendi antrenmanlarını görür ve değiştirebilir

### Egzersiz Yönetimi
- Bir antrenmana egzersiz ekle (set, tekrar, kilo)
- Egzersizleri güncelle ve sil
- Her egzersizin opsiyonel notu olabilir (örn: "form bozuldu")

## 5. Şimdilik Yapmayacağım Şeyler (Out of Scope)

Aşağıdaki özellikler ileride **feature** olarak eklenecek. MVP'de yer 
almamasının sebebi, odağı dağıtmamak ve projeyi bitirilebilir tutmak.

- **Vücut ölçüleri (kilo, yağ oranı, çevre):** Ayrı bir problem alanı 
  (kompozisyon takibi). MVP'nin asıl çözdüğü problem antrenman 
  hatırlamak, vücut takibi başka bir özellik.

- **İstatistikler ve grafikler:** Önce yeterli veri birikmesi gerekiyor. 
  Kullanıcı 2-3 hafta antrenman kaydetmeden istatistiğin anlamı yok.

- **Sosyal özellikler (arkadaş ekleme, paylaşım):** Karmaşıklığı çok 
  artırır (ilişkiler, izinler), ana probleme katkısı yok.

- **Hazır antrenman programları:** İçerik hazırlama gerektirir, ayrı 
  bir veri modeli. MVP'de kullanıcı kendi antrenmanını giriyor.

- **Mobil uygulama:** Sadece web. Mobil için ayrı bir kod tabanı (React 
  Native vb.) gerekir, iş yükünü ikiye katlar.

## 6. Kullandığım Teknolojiler

### Backend

- **FastAPI:** Type hints sayesinde input validation otomatik yapılıyor 
  ve OpenAPI uyumlu dokümantasyon (Swagger UI) otomatik üretiliyor. 
  Python ekosistemine hakim olduğum için geliştirme hızım yüksek.

- **PostgreSQL:** FitTrack verisi ilişkisel — kullanıcı, antrenman ve 
  egzersiz birbirine bağlı tablolar halinde. Endüstride yaygın 
  kullanılan, açık kaynak ve gelişmiş bir veritabanı. JSON sütun 
  desteği gibi modern özellikleri de var.

- **Docker:** Uygulamayı izole bir ortamda çalıştırıyor, bağımlılıkları 
  container içinde tutuyor. "Bende çalışıyor" problemini ortadan 
  kaldırıyor. Backend + PostgreSQL'i tek komutla ayağa kaldırabiliyorum.

### Frontend
(Frontend geliştirmeye başlandığında doldurulacak)