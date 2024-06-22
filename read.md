## 🦈 Requirements
- NodeJS
- Server Mariadb/MySQL
- Datacenter/Residentiel Proxy
- Optionnel:
  - PM2

## 🚀 KURULUM
- Asagidaki bilgileri teker teker yapmaniz gerekmektedir!:
  - Linux icin: **`./install.sh`**
  - Windows icin:: **`./install.bat`**
- Database oluşturup tum izinleri olan db yi **`Database/index.ts`**'de  doldurun. (BU DB OLMADAN HIC BIR SEKILDE BOTUNUZ AKTIF OLMAZ)
  - Bundan sonra **`phpmyadmin`**'den Admin sayfasindan kendi idnizi girin -> **bot sayfasından owner vermesseniz kimseyi owner olarak ekliyemezsiniz**
- complie programlari
  - linux icin: **`./compilate.sh`**
  - windows icin: **`./compilate.bat`**
- **`API`** Klasorunun icinde **`npm start`** yapin (API KLASORUNDE CMD YI ACMANIZ GEREKMEKTEDIR.)
  - PM2: **`pm2 start dist --name "API"`** (ONERILEN)
- **`Client`** icindeki `runClient.sh`'yi calistirarak botunuzu aktif edebilirsiniz eğer üstteki bilgileri harfi harfiyen doğru yaptiysaniz.
  - örnek:: **`./runClient.sh IdOfBot Token`**
  - Windows icin yapmaniz gereken: **`runClient.bat BotId'si BotTokeni`**
    - node kullanarak: **`node dist/Client/Client.js Token`**
- Proxylerinizi bu dosyanin icine yerleştirin: **`ips-data_center.json`** (complie'yi calistirmadan once. eğer calistirdiysanizi tekrar calistirmaniz gerekmekte eğer olmassa **`Client/dist/ips-data_center.json`**'dan değiştirmeniz gerekmektedir proxylerinizi.)
  - örnek: 
```json
[
    "IP:PORT:USER:PASSWORD",
    "IP:PORT:USER:PASSWORD",
    ...
]
```

## 📝 BOT AYARLARI (ADIM ADIM YAPILMALIDIR.)
- **`Client`** Dosyasindaki **`/config.ts`**'i **`REDIRECTION_URI`**'ni koy
  - örnek: **`http://localhost:3000/callback`**
  - örnek: **`http://IP:3000/callback`**
  - örnek: **`http://DOMAIN:3000/callback`**
  - örnek: **`http://DOMAIN/callback`**
- Developer portaldan yeni bot oluştur.
- Botun tüm intentleri acik olmak zorundadir.
- `OAuth2` bölümünden -> `General` `Redirects` url ni yerleştir. (API BAGLANTINIZ)
  - örnek: **`http://localhost:3000/callback`**
  - örnek: **`http://IP:3000/callback`**
  - örnek: **`http://DOMAIN:3000/callback`**
  - örnek: **`http://DOMAIN/callback`**

## 🔒 BOTUN DAVETINI ALMA
- `OAuth2` -> `URL Generator`'den `botunuzun` linkini alabilirsiniz. `Administrator` yaparak en yüksek yetkiyi verebilirsiniz.
  - ![](https://s3files.m1000.fr/screenshot/2023/04/chrome_ACkzihgTq2.png)

## 📅 ROUTINE
<!-- Requirement Proxy list -->
**⚠️ Routine yani Refresh icin proxy gerekmektedir. !**
- Routineyi baslatmak icin `Routine` klasorunde cmd'ye bunu yazabilirsin: `node dist/Routine` 
  - PM2 kullanarak: `pm2 start dist/Routine/Routine.js --name "Routine"` (ÖNERİM BUDUR.).