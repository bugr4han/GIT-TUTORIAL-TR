<h1 align="center">🚀 GitHub CLI</h1>
<p align="center">
  <strong>GitHub CLI</strong>, GitHub ile etkileşimi doğrudan terminal üzerinden gerçekleştirmeyi sağlayan güçlü bir komut satırı aracıdır.  
  Depo oluşturma, issue yönetimi, pull request açma, commit geçmişini görüntüleme ve kimlik doğrulama gibi birçok işlemi tarayıcıya ihtiyaç duymadan hızlıca yapmanıza imkân tanır.
  <br><br>
  Özellikle <strong>auth (kimlik doğrulama)</strong> sürecini kolaylaştırmasıyla geliştiricilerin iş akışını hızlandırır.  
  Böylece GitHub ile tüm etkileşimlerinizi tek bir terminal penceresinden yönetebilir, daha verimli bir geliştirme deneyimi yaşayabilirsiniz.
</p>

## 🔧 GitHub CLI Kurulumu

### 🍎 macOS

```bash
brew install gh
```

### 🪟 Windows

```powershell
winget install --id GitHub.cli -e
```

### ✔️ Kurulum Kontrolü

```bash
gh --version
```

---

## ⚡ GitHub CLI Komutları

```bash
# GitHub CLI ile GitHub’a Giriş Yapma (GitHub.com → HTTPS → Tarayıcıyla giriş)
gh auth login
```

```bash
# GitHub CLI Giriş Durumunu Kontrol Etme
gh auth status
```

```bash
# GitHub CLI’den Çıkış Yapma
gh auth logout
```

---

<p align="center">
    <a href="./03-genel-komutlar.md">
        <img 
            src="https://img.shields.io/badge/➜%20Devam%20Et-724CF9?style=for-the-badge&logoColor=white"
            alt="Devam Et"
            width="125"
        >
    </a>
</p>
