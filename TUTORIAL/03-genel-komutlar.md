<h1 align="center">🗝️ Genel Komutlar</h1>
<p align="center">
  Git ve terminal kullanımında en sık başvurulan temel komutların özetini içerir.  
  Bu komutlar, dosya yönetiminden Git yapılandırmasına ve depo işlemlerine kadar günlük geliştirme sürecinde ihtiyaç duyulan temel araçları sağlar.
</p>

## 📂 Temel Terminal Komutları

```bash
pwd                       # Bulunduğun dizinin tam yolunu gösterir

ls                        # Dizin içindeki dosya ve klasörleri listeler
ls -l                     # Detaylı liste (izinler, boyut, tarih vs.)
ls -a                     # Gizli dosyalar dahil tüm dosyaları gösterir

cd klasorAdi              # Belirtilen klasöre geçiş yapar
cd ..                     # Bir üst dizine çıkar
cd ~                      # Ana dizine gider

clear                     # Terminal ekranını temizler (Ctrl+L kısayolu da var)

mkdir yeni_klasor         # Yeni klasör oluşturur
mkdir -p klasor/yeni      # Arada klasör yoksa onlar da oluşturulur

touch yeni_dosya.txt      # Yeni boş dosya oluşturur veya var ise tarihini günceller

nano dosya.txt            # Terminal tabanlı basit metin editörü
```

## 👤 Git Kullanıcı Bilgisi

```bash
# Kullanıcı Bilgisi Ayarlama
git config --global user.name "Adınız Soyadınız"
git config --global user.email "githubMailAdresiniGirin@ornek.com"

# Kullanıcı Bilgisini Kontrol Etme
git config --global --list
git config user.name
git config user.email

# Kullanıcı adı ve e-posta silme
git config --global --unset user.name
git config --global --unset user.email
```

## ⚡ Temel GitHub Komutları

```bash
git init                                  # Yeni bir Git deposu oluşturur
git branch -M main                        # Varsayılan branch'i 'main' yapar
git add .                                 # Tüm dosyaları commit için hazırlar
git commit -m "first commit"              # İlk commit'i oluşturur
git remote add origin REPO_ADRESINIZ      # GitHub repo adresini bağlar
git push -u origin main                   # Projeyi GitHub'a gönderir ve izlemeyi ayarlar

git status                                # Çalışma dizinindeki değişiklikleri gösterir
git log                                   # Commit geçmişini listeler
```

## 🌿 Branch Yönetimi

```bash
git branch                         # Mevcut branchleri listele
git branch yeniBranch              # Yeni branch oluştur
git branch --all                   # hem yerel hem de uzak branch’leri gösterir.
git switch branchAdi               # Branch değiştir
git checkout branchAdi             # Branch değiştir
git merge branchAdi                # Branchleri birleştir - Master ile
```

## 📥 Depo Klonlama

```bash
git clone REPO_LINK          # Uzaktaki bir depoyu yerel bilgisayara kopyalar


# Klonladıktan sonra yaygın işlemler
git remote -v                # Uzaktaki bağlantıları gösterir (origin gibi)
git fetch                    # Uzaktaki değişiklikleri indirir (otomatik merge yapmaz)
git pull                     # Uzaktaki değişiklikleri indirir ve birleştirir (fetch + merge)
```

## ✏️ Değişiklikleri Yönetme

```bash
git diff                         # Henüz eklenmemiş değişiklikleri gösterir
git diff dosyaAdi.js             # Belirli dosyanın farkını gösterir
git diff --staged                # Eklenen değişikliklerin farkı

git rm dosya.js                  # Dosyayı sil ve değişiklik olarak ekle
git rm -r klasorAdi              # Tüm Klasörü sil r = recursive
git mv eskiAdi yeniAdi           # Dosya adını değiştir
git mv tasinacakDosya klasor/
```

## 🔄 Geri Alma Komutları

```bash
git restore dosya.txt                     # Çalışma alanını eski haline getir
git restore --staged dosya.txt            # Staged değişikliği kaldır (Silersek)
git checkout COMMIT_KODU dosya.txt        # Belirli versiyonu geri yükle
```

## 🔀 Checkout Komutları

```bash
# BRANCH GEÇİŞİ / BRANCH OLUŞTURMA
git checkout branchAdi                   # Var olan branch'e geç
git checkout -b yeniBranch               # Yeni branch oluştur + o branch'e geç
git checkout --track origin/branch       # Uzak branch'i takip eden lokal branch oluştur

# COMMITE GEÇME (DETACHED HEAD)
git checkout COMMIT_HASH                 # Belirli commit'e geçer (detached HEAD)
git checkout HEAD~3                      # Şu andan 3 commit önceki sürüme geç

# DOSYA / KLASÖR GERİ GETİRME
git checkout -- dosya.txt                # Dosyayı son commit'teki haline döndür
git checkout COMMIT_HASH -- dosya.txt    # Dosyayı belirli commit'teki haline getir
git checkout branchAdi -- dosya.txt      # Başka branch'teki dosyayı çek

# MERGE ÇATIŞMALARINDA KULLANIM
git checkout --ours dosya.txt            # Çatışmada kendi (aktif branch) versiyonunu al
git checkout --theirs dosya.txt          # Çatışmada karşı branch'in versiyonunu al

# DİĞER FAYDALI KULLANIMLAR
git checkout main                        # Ana branch'e geç
git checkout -f branchAdi                # Zorla branch değiştir (dikkat: değişiklikleri siler!)

```

## 🧹 Geçmiş Commitleri Silme

```bash
git checkout --orphan new_branch            # Yeni bir branch oluştur
git add .                                   # Her şeyi yeni branche ekle
git commit -m "commit"                      # Commit işlemi
git branch -D main                          # 'main' branch'ini sil
git branch -m main                          # Mevcut branch'i 'main' olarak yeniden adlandır
git push -f origin main                     # Zorla gönder ve işlemi tamamla
```

## 🧹 DS_Store Ignore Ekleme / Silme

```bash
# 1️⃣ Git'e global ignore dosyasını tanıt
git config --global core.excludesfile ~/.gitignore_global

# 2️⃣ Global ignore dosyasına .DS_Store ekle
echo .DS_Store >> ~/.gitignore_global

# 3️⃣ Eklemeyi kontrol et (opsiyonel)
cat ~/.gitignore_global

# 4️⃣ .DS_Store'u global ignore dosyasından kaldırmak istersen:
rm ~/.gitignore_global                              # ignore dosyasını sil
git config --global --unset core.excludesfile       # Git ayarını temizle
```

<br>

<p align="center">
    <a href="./04-kaynaklar.md">
        <img 
            src="https://img.shields.io/badge/➜%20Devam%20Et-724CF9?style=for-the-badge&logoColor=white"
            alt="Devam Et"
            width="125"
        >
    </a>
</p>
