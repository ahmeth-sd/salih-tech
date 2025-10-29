# Netlify Deployment Guide

Bu rehber, projenizi Netlify'a deploy etmek için gereken adımları açıklar.

## Önkoşullar

✅ Remote URL HTTPS olarak ayarlandı: `https://github.com/ahmeth-sd/salih-tech.git`
✅ Contact form Netlify Forms ile uyumlu hale getirildi
✅ `netlify.toml` konfigürasyon dosyası oluşturuldu
✅ `.gitignore` dosyası eklendi

## Netlify'ye Deploy Etme Seçenekleri

### Seçenek 1: Netlify UI ile Deploy (Önerilen - En Kolay)

1. **Netlify'ye Git**
   - [https://www.netlify.com/](https://www.netlify.com/) adresine gidin
   - GitHub hesabınızla giriş yapın (Sign up / Log in)

2. **Yeni Site Oluştur**
   - Dashboard'da "New site from Git" butonuna tıklayın
   - "GitHub" seçeneğini seçin
   - Netlify'ye GitHub erişim izni verin (ilk defa kullanıyorsanız)

3. **Repository Seçin**
   - `ahmeth-sd/salih-tech` repository'sini seçin
   - Branch seçin: `main` (veya aktif branch'iniz)

4. **Build Ayarları**
   - **Build command:** (boş bırakın)
   - **Publish directory:** `.` (nokta - root dizini)
   - "Deploy site" butonuna tıklayın

5. **Deploy Durumunu İzleyin**
   - Deploy işlemi başlayacak (genellikle 1-2 dakika sürer)
   - Deploy tamamlandığında size bir URL verilecek (örn: `random-name-123456.netlify.app`)

### Seçenek 2: Netlify CLI ile Deploy

1. **Netlify CLI'ı Yükleyin**
   ```bash
   npm install -g netlify-cli
   ```

2. **Netlify'ye Giriş Yapın**
   ```bash
   netlify login
   ```
   - Browser'da açılan sayfadan Netlify'ye giriş yapın ve yetkiyi onaylayın

3. **Projeyi Netlify'ye Bağlayın**
   ```bash
   cd D:\Docs\Ceng\Projects\resume-website\salih-tech
   netlify init
   ```
   
   Sorulan sorular:
   - "What would you like to do?" → **"Create & configure a new site"**
   - "Team:" → Kendi team'inizi seçin
   - "Site name:" → İstediğiniz bir isim girin (örn: `salih-portfolio`)
   - "Your build command:" → (Enter - boş bırakın)
   - "Directory to deploy:" → `.` (nokta)

4. **Production'a Deploy Edin**
   ```bash
   netlify deploy --prod
   ```
   - Deploy işlemi tamamlandığında site URL'si gösterilecek

## Contact Form Nasıl Çalışır?

- **Netlify Forms** otomatik olarak form gönderilerini yakalar
- PHP backend'e gerek yok
- Tüm form gönderileri Netlify dashboard'unda görüntülenebilir
- Spam koruması (honeypot) dahil

### Form Gönderilerini Görme

1. Netlify dashboard'a gidin
2. Site'inizi seçin
3. "Forms" sekmesine tıklayın
4. Tüm form gönderileri burada görünecek

### E-posta Bildirimleri (Opsiyonel)

1. Netlify dashboard → Site → Settings → Forms
2. "Form notifications" bölümünden e-posta bildirimleri ekleyebilirsiniz
3. Her form gönderisinde e-posta alabilirsiniz

## Önemli Notlar

### PHP Dosyaları
- `contactengine.php` ve `contactthanks.php` artık kullanılmıyor
- Netlify PHP çalıştırmaz, bu yüzden Netlify Forms kullanıyoruz
- Eski PHP dosyaları referans için saklanabilir veya silinebilir

### Custom Domain (Opsiyonel)
Netlify dashboard'dan kendi domain'inizi ekleyebilirsiniz:
1. Site settings → Domain management
2. "Add custom domain" butonuna tıklayın
3. Domain'inizi girin ve DNS ayarlarını yapın

### HTTPS
- Netlify otomatik olarak HTTPS sağlar (Let's Encrypt)
- Ek bir ayar yapmanıza gerek yok

## Sorun Giderme

### Form çalışmıyor
- Netlify Forms'un düzgün çalışması için HTML'de `data-netlify="true"` attribute'u olmalı ✓
- `form-name` hidden input olmalı ✓
- Form method `POST` olmalı ✓

### Deploy başarısız
- Branch'inizde tüm değişiklikler commit ve push edilmiş olmalı
- `netlify.toml` dosyasının syntax hatası olmadığından emin olun

### 404 Hatası
- Publish directory'nin `.` (root) olarak ayarlandığından emin olun
- `index.html` dosyasının root'ta olduğunu kontrol edin ✓

## Test Etme

Deploy sonrası test için:
1. Site URL'ini açın
2. Contact form'a gidin (`#contact` anchor)
3. Tüm alanları doldurun
4. "Send" butonuna tıklayın
5. "Your message has been sent!" sayfası görünmeli
6. Netlify dashboard'da form gönderisi görünmeli

## Yardım

Sorun yaşarsanız:
- [Netlify Documentation](https://docs.netlify.com/)
- [Netlify Support](https://www.netlify.com/support/)
- [Netlify Forums](https://answers.netlify.com/)
