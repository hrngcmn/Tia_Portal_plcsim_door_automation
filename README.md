# Tia_Portal_plcsim_door_automation
TiaPortalV16  üzerinden otomatik kapı otomasyon sistemi için  ladder diyagramı oluşturma, oluşturulan ladder diyagramın S7_PLCSIM üzerinden simülasyon edilmesinin kodlarını içerir. Bu proje TiaportalV16 kullanılarak ladder diyagramı ve s7_plcsim kullanılarak simulasyon işlemi gerçekleştirilmiştir. 
...............................................

Otomatik kapının çalışma prensibleri şu şekildedir;
-- Stop yada asırı akım rölelesi kontağı sisteminin tamamını durdurur.
-- Yukarı yada asagi yönde araçları gören sensör olduğu varsayılmıştır. Sönsör nesne(araba,insan vb.)  algıladığında kapi açılmaya başlayacaktır.
-- Açılması için çalışan motorun durmasını sınır anahtarı belirlemektedir. Sınır anahtarı kapının açılabileceği son noktaya kadar gittiğinde devreye girecektir. 
-- Kapanma motorunun kontrolü için de aynı durum geçerlidir. 
-- Kapanma sırasında sensörler tekraradan bir nesne algılarsa kapanma duracaktır. Ve kapı açılmaya başlayacaktır. 
..................................................

Farklı versyon programlar kullanıyorsanız veya dosyaları indirseniz de açılmıyorsa(versiyon farklı vb. nedenlerden dolayı) networklerin fotoğrafını ekledim. 
simülasyon üzerinden yaptığım için S7-1500 plc seçimi yaptım. 
