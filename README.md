# Tia Portal Plcsim Door Automation
TiaPortalV16  üzerinden otomatik kapı otomasyon sistemi için  ladder diyagramı oluşturma, oluşturulan ladder diyagramın S7_PLCSIM üzerinden simülasyon edilmesinin kodlarını içerir. Bu proje TiaportalV16 kullanılarak ladder diyagramı ve s7_plcsim kullanılarak simulasyon işlemi gerçekleştirilmiştir. 

**Otomatik kapının çalışma prensipleri şu şekildedir;**
-- Stop yada aşırı akım rölelesi kontağı sisteminin tamamını durdurur.
-- Yukarı yada asagi yönde araçları gören sensor olduğu varsayılmıştır. Sönsör nesne(araba, insan vb.)  algıladığında kapı açılmaya başlayacaktır.
-- Açılması için çalışan motorun durmasını sınır anahtarı belirlemektedir. Sınır anahtarı kapının açılabileceği son noktaya kadar gittiğinde devreye girecektir. 
-- Kapanma motorunun kontrolü için de aynı durum geçerlidir. 
-- Kapanma sırasında sensörler tekrardan bir nesne algılarsa kapanma duracaktır. Ve kapı açılmaya başlayacaktır. 

Farklı versyon programlar kullanıyorsanız veya dosyaları indirseniz de açılmıyorsa(versiyon farklı vb. nedenlerden dolayı) networklerin fotoğrafını ekledim. 
simülasyon üzerinden yaptığım için S7-1500 plc seçimi yaptım. 

**Taglara verdiğim isimler aşağıda gösterilmiştir.** 
![enter image description here](https://github.com/hrngcmn/Tia_Portal_plcsim_door_automation/blob/main/PLC%20tags%20foto.png?raw=true)
**LADDER DİYAGRAMI AÇIKLANMASI**

**Network 1** de yapılan işlem; yukarı yada aşağı sensörleri aktif olduğunda(lojik 1 olduğunda) yardımcı röleyi set et.
**Network 2** de yapılan işlem de aa ile stop u paralel olarak çizin dostlar :D . 

![enter image description here](https://github.com/hrngcmn/Tia_Portal_plcsim_door_automation/blob/main/network%201%20-%202%20foto.png?raw=true)

**Network3** yapılan işlem kapının motorun sola çalışmasını sağlamaktır.  açma sınır anahtarına geldiğinde kapının çalışması duracaktır. 
**Network4** kapı açık kaldıktan sonra 20 sn bekleme işlemi yaptırır. Ton(düz zaman rölesi kullanılmıştır.) 

![enter image description here](https://github.com/hrngcmn/Tia_Portal_plcsim_door_automation/blob/main/network3%20-%204%20foto.png?raw=true)

**network5** 20 sn beklendikten sonra kapının kapanma(motor sağa) işleminin kontrolünü yapar. Kapama sınır anahtarına aktif olduğunda sağa dönen motor duracaktır. Aynı şekilde aşağı veya yukarı sensörleri aktif olduğunda kapama işlemi yapılmayacaktır. Kapının sola dönme motorunun kapalı kontağı konması elektriksel kilitleme işlemidir. 
**network6**  kapanma sınır anahtarı aktif olduğunda yardımcı röle 2 çalışıyor. yardımcı röle 2 nin kullanılmasının amacı network1 deki sola dönme motorunun, sağa dönme motoru durur durmaz çalışmaya başlaması durumunu engellemektir. 

![enter image description here](https://github.com/hrngcmn/Tia_Portal_plcsim_door_automation/blob/main/network5%20-%206%20foto.png?raw=true)
