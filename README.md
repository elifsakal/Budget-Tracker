Budget Tracker App 📊

Bu proje, kullanıcıların farklı kategorilerde bütçe limitleri belirlemelerine, mevcut harcamaları takip etmelerine ve bütçeleri aşmaları durumunda uyarı almalarına olanak tanıyan bir bütçe takip uygulamasıdır. Proje, React ve Context API kullanılarak geliştirilmiştir.

Özellikler
Kullanıcılar farklı kategoriler için bütçe limiti ekleyebilir.
Eklenen limitler listelenir ve gerekirse silinebilir.
Harcamalar, belirlenen bütçe limitleriyle karşılaştırılarak limit aşımı kontrol edilir.
Limitin %80'ine yaklaşıldığında veya aşıldığında uyarı mesajı gösterilir.
Veriler LocalStorage'a kaydedilerek sayfa yenilense bile kalıcı hale getirilir.

Kurulum ve Çalıştırma

1. Depoyu Klonlayın
git clone https://github.com/elifsakal/budget-tracker.git

2. Proje Dizinine Geçin
cd budget-tracker

3. Gerekli Bağımlılıkları Yükleyin
npm install

4. Uygulamayı Başlatın
npm start

Uygulama, varsayılan olarak http://localhost:3000 adresinde çalışacaktır.

Kullanım
1. Kategori ve Limit Belirleme
Adımlar:
Budget Limit (Bütçe Limiti) sayfasına gidin.
Bu sayfa, src/app/budgetLimit/page.tsx altında tanımlıdır.
"Kategori" ve "Limit" alanlarına, belirli bir harcama kategorisi (örneğin, "Eğitim") ve bu kategori için belirlediğiniz limit miktarını girin.
"Ekle" butonuna tıklayın.
Eklediğiniz kategori ve limit, aşağıda bir liste olarak görüntülenecektir.
2. Limit Silme
Adımlar:
Eklenen kategorilerin listesi, Budget Limit sayfasında gösterilir.
Listede, her kategorinin yanında bir "Sil" butonu bulunur.
Silmek istediğiniz kategorinin yanındaki "Sil" butonuna tıklayın.
Kategori ve limiti hem listeden hem de local storage'dan kaldırılır.
3. Limit Aşımı Kontrolü
Özellikler:
Belirlediğiniz kategorideki harcamalar, belirlenen limitin %80'ine yaklaştığında kırmızı bir uyarı mesajı görüntülenir.
Limit aşımı veya yaklaşımı olduğunda uyarılar, sayfa yenilendiğinde de korunur.
Bu durum, local storage kullanılarak yönetilir.
4. İşlemler ve Grafikler
İşlemler, Transactions (İşlemler) sayfasında eklenip yönetilir.
Bu sayfa src/app/transactions/page.tsx altında bulunur.
Eklediğiniz harcamalar kategorilere atanır.
Charts (Grafikler) sayfası üzerinden harcama trendlerini ve kategorik harcamaları görselleştirebilirsiniz.
Bu sayfa, src/app/charts/page.tsx altında yer alır.



Proje Yapısı

src/
├── app/                             # Sayfa ve route yapılarını içerir (Next.js kullanımı için).
│   ├── budgetLimit/                 # Bütçe limiti ile ilgili sayfa ve işlemler.
│   │   └── page.tsx                 # Bütçe limiti ayarlama ve gösterim sayfası.
│   ├── charts/                      # Grafiklerle ilgili sayfa.
│   │   └── page.tsx                 # Harcama ve trend grafikleri sayfası.
│   ├── features/                    # Özel özelliklere ait sayfa.
│   │   └── page.tsx                 # Özellikler sayfası.
│   ├── savingRecommendation/        # Tasarruf önerileri ile ilgili sayfa.
│   │   └── page.tsx                 # Kullanıcıya tasarruf önerileri sunan sayfa.
│   ├── transactions/                # İşlemlerle ilgili sayfa ve layout.
│   │   ├── layout.tsx               # İşlem sayfasının genel layout dosyası.
│   │   └── page.tsx                 # İşlemleri listeleme ve yönetme sayfası.
│   └── page.tsx                     # Ana sayfa (root route).
│
├── components/                      # Yeniden kullanılabilir React bileşenleri.
│   ├── charts/                      # Grafik bileşenleri.
│   │   ├── ExpenseChart.tsx         # Harcama kategorilerine göre grafik.
│   │   └── TransactionTrendChart.tsx# İşlem trend grafiği bileşeni.
│   ├── forms/                       # Formlarla ilgili bileşenler.
│   │   ├── BudgetLimitForm.tsx      # Bütçe limiti ayarlama formu.
│   │   └── TransactionForm.tsx      # Yeni işlem ekleme formu.
│   ├── lists/                       # Listeleme bileşenleri.
│   │   ├── TransactionList.tsx      # İşlem listesini gösteren bileşen.
│   │   └── DownloadReport.tsx       # Rapor indirme işlemi için bileşen.
│   ├── Header.tsx                   # Uygulamanın üstbilgi (header) bileşeni.
│   └── SavingsRecommendation.tsx    # Tasarruf önerilerini gösteren bileşen.
│
├── context/                         # Uygulama genelindeki durumu yöneten Context API dosyaları.
│   ├── BudgetContext.tsx            # Harcamalarla ilgili durum yönetimi.
│   └── BudgetLimitsContext.tsx      # Bütçe limitleriyle ilgili durum yönetimi.
│
├── styles/                          # CSS ve stil dosyaları.
│   └── globals.css                  # Uygulama genelindeki stil tanımlamaları.
└── /


Teknolojiler

React: Kullanıcı arayüzü oluşturmak için.
TypeScript: Daha güçlü bir yazım desteği için.
Context API: Durum yönetimi için.
LocalStorage: Verilerin kalıcı olarak saklanması için.
