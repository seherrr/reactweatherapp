Bu uygulamada hava durumu Web API'a istek gönderildi ve aldığımız verilerle kullanıcının bulunduğu konumdaki hava durumunu ekrana yazdırıldı.

API: https://openweathermap.org/api

Bu linke tıklayın ve üye olun.

Üye olduktan sonra e-mail adresinize gelen maili onaylayın.

Ardından https://home.openweathermap.org/api_keys adresine giderek API Key'inizi kopyalayın ve bir yere kaydedin. Bu Key ile ücretsiz API üzerinden hava durumu verilerini çekebileceksiniz.

Proje için bir klasör oluşturun ve bu klasör içinde React projenizi oluşturun.

npx create-react-app .

Sondaki nokta bulunduğunuz klasör içinde projenizi kurmak için gereklidir. Bu komutu kullandığınız klasör boş olmalıdır.

Projenizin ana dizininde .env isimli bir dosya oluşturun ve Key'inizi bu dosya içinde REACT_APP_WEATHER_API_KEY olarak kaydedin.

REACT_APP_WEATHER_API_KEY=api_keyiniz_buraya_yazin

Oluşturduğunuz .env dosyasını .gitignore dosyanıza eklemeyi unutmayın.

Src klasörü içindeki bütün dosyaları silin ve iki adet dosya oluşturun: App.js ve index.js.

Uygulamamızı en basit haliyle çalışır hale getirdikten sonra terminalden uygulamamızı başlatın.

npm start

Kullanacağımız API Endpoint'i bulalım.

https://openweathermap.org/current adresine gidin ve By geographic coordinates bölümündeki örnek linki kopyalayın.

https://api.openweathermap.org/data/2.5/weather?lat={lat}&lon={lon}&appid={API key}
Bu link içine üç tane parametre gireceğiz: Enlem (lat), Boylam (lon), ve API Key.

Önce API isteğini yapacak olan paketimizi yükleyelim.

npm install axios

Kullanıcımızın lokasyon bilgilerine ulaşmaya çalışalım.

npm i use-position

------------------------------

Uygulamamızın dili varsayılan olarak ingilizce. Bunun nedeni; API isteğini yaparken herhangi bir dil seçeneği belirtmedik. Kullanıcının kullandığı tarayıcıdan dilini öğrenip bunu API isteğimize eklememiz gerekecek.

Sıcaklık değeri varsayılan olarak Kelvin birimine göre ayarlanmış. Bizim bunu metric sistemdeki birime, yani Celsius'a çevirmemiz gerekecek.
