# PM2 System Anlatım.

**Hepinize merhaba arkadaşlar, Yakın zamanlarda Electus ile paylaşacağımız Bot ve Web Site projesi içerisinde olan Bot için bilgilendirme yapacağım.**

* Basit bir şekilde PM2 Nedir size onu açıklayayım.
* PM2 sizin kullanmış olduğunuz pc niz veya vds inizi **Web host** gibi kullanmanıza olanak sağlıyan sistemdir.

# Kullanım

* Kullanmak istediğiniz botları bir dosya içerisinde toplayıp, Node Modüllerini CMD üzerinden açarak modülleri yükleyiniz.
* Sonrasında dosyanızın içerisinde **ecosystem.config.js** Dosyası oluşturunuz.

# ecosystem.config.js Dosyasını oluşturduk içerisine neler yazacağız.

```js
module.exports = {
    apps: [
      {
        name: "ticket-system",
        namespace: "BotiStudio Ticket",
        script: 'main.js',
        watch: false,
        exec_mode: "cluster",
        instances: 1,
        max_memory_restart: "500M",
        cwd: "./ticket",
        env: {
          NODE_ENV: "production"
        }
      }
    ]
};
```

**Name, namespace, script, cwd Opsiyonel olarak sizlerin dosyasına göre doldurulabilir.**

# Sistemi Çalıştır.

Bütün herşeyiniz hazır olduğu zaman dosyanızın içerisinde CMD açarak;
**npm init -y** Yazarak yeni bi package.json dosyası oluşturunuz.
PM2 Modülünü yüklemek için CMD'ye **npm i pm2@latest -g** yazınız.
Sonrasında pm2 start yazarak botunuzu başlatabilirsiniz.

# Hataları göremiyorum hatalar nerede?

Hatalari görmek için pm2 logs yazarak hataları veyahut logları görebilirsiniz.

# Önemli!

pm2 restart all yaparak botları yeniden başlatabilirsiniz.

pm2 kill yaparak botu kapatabilirsiniz, **SEKMEYİ KAPATIP GİTMEYİN ARAKDA ÇALIŞMAYA DEVAM EDECEK**

# Kendinize iyi bakın!

**Anlatacaklarım bu kadardı yakında çok güzel bir proje ile karşınıza çıkacağız takip etmeyi unutmayın iyi günler.**
