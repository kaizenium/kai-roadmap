# Kai Yol Haritası

Bu doküman, Kai dilinin ve ekosisteminin geliştirme sırasını takip eder. Fazlar tarih sırasına göre değil, bağımlılık sırasına göre düzenlenmiştir - her faz, kendinden önceki fazın temel çıktısına ihtiyaç duyar. Bu, henüz spesifikasyon aşamasında olan bir proje için gerçekçi bir taahhüt seviyesidir.
 
## Durum Anahtarı
 
| Etiket | Anlamı |
|---|---|
| TAMAMLANDI | Tamamlandı |
| DEVAM EDİYOR | Aktif olarak üzerinde çalışılıyor |
| PLANLANDI | Planlandı, henüz başlamadı |
| FİKİR | Değerlendiriliyor, henüz kesinleşmedi |
 
---
 
## Faz 0 — Dil Tasarımı
 
**Hedef:** Sözdizimini ve semantiği kağıt üzerinde netleştirmek.
 
| Durum | Madde |
|---|---|
| TAMAMLANDI | Felsefeyi ve hedef alanları tanımla |
| DEVAM EDİYOR | v0.1 dil spesifikasyonu ([about-kai](https://github.com/kaizenium/about-kai)) |
| PLANLANDI | Sözdizimi örneklerini genişlet (uç durumlar: jenerik kısıtlamalar, operatör aşırı yükleme kuralları, makro sistemi detayları) |
| PLANLANDI | Spesifikasyon hakkında topluluk geri bildirimi topla |
 
## Faz 1 — Sözcük Çözümleyici ve Ayrıştırıcı
 
**Hedef:** Kai kaynak kodunu AST'ye çevirebilen minimal bir ön uç.
 
| Durum | Madde |
|---|---|
| PLANLANDI | Lexer: token tanımları, string/char/sayısal literal işleme |
| PLANLANDI | Parser: ifade/deyim grameri, öncelik kuralları |
| PLANLANDI | AST tanımları |
| PLANLANDI | Parser hata mesajları (satır/sütun bilgisiyle) |
 
## Faz 2 — Semantik Analiz
 
**Hedef:** Çalışan tip kontrolü ve temel doğrulama.
 
| Durum | Madde |
|---|---|
| PLANLANDI | Sembol tablosu ve kapsam çözümlemesi |
| PLANLANDI | Tip kontrolü (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| PLANLANDI | Struct/class alan ve metot çözümlemesi |
| PLANLANDI | Görünürlük kurallarını uygula (`public`/`private`/`protected`) |
| PLANLANDI | Jenerik tip çözümlemesi (`Vector<T>`) |
 
## Faz 3 — Kod Üretimi
 
**Hedef:** Doğrulanmış bir AST'yi çalışan x86-64 Assembly'ye dönüştürmek.
 
| Durum | Madde |
|---|---|
| PLANLANDI | Temel ifadeler ve kontrol akışı için kod üretimi (`if`/`for`/`while`/`switch`) |
| PLANLANDI | Fonksiyon çağırma kuralı, yığın çerçevesi yönetimi |
| PLANLANDI | Struct/class bellek düzeni |
| PLANLANDI | Satır içi assembly (`asm {}`) blok entegrasyonu |
| PLANLANDI | NASM/GAS çıktısını linker üzerinden birleştir |
| PLANLANDI | Kilometre taşı: "Hello World" çalıştır (Linux x86-64) |
 
## Faz 4 — Derleyici Olgunluğu
 
**Hedef:** Gerçek programlar yazılabilir hale gelsin.
 
| Durum | Madde |
|---|---|
| PLANLANDI | Manuel bellek yönetimi altında pointer/referans kod üretimi |
| PLANLANDI | Constructor/destructor çağrı sırası, kalıtım ve sanal (virtual) dispatch |
| PLANLANDI | constexpr değerlendirmesi |
| PLANLANDI | Makro sistemi implementasyonu |
| PLANLANDI | Derleyici hata ve uyarı mesajlarını iyileştir |
| FİKİR | Temel optimizasyon geçişleri (ölü kod eleme, sabit katlama) |
 
## Faz 5 — Araç Ekosistemi
 
**Hedef:** Dili günlük kullanıma uygun hale getirmek.
 
| Durum | Madde |
|---|---|
| PLANLANDI | [kai](https://github.com/kaizenium/kai) CLI: `build`/`run`/`clean`/`add`/`remove`/`update` |
| PLANLANDI | [kai-syntax](https://github.com/kaizenium/kai-syntax): editör sözdizimi vurgulama (VSCode, Vim) |
| PLANLANDI | [kaifmt](https://github.com/kaizenium/kaifmt): kod biçimlendirici |
| PLANLANDI | [kaistd](https://github.com/kaizenium/kaistd): minimal standart kütüphane (I/O, string'ler, koleksiyonlar) |
| FİKİR | [kaitest](https://github.com/kaizenium/kaitest): test aracı |
| FİKİR | [kaibench](https://github.com/kaizenium/kaibench): benchmark aracı |
 
## Faz 6 — Platform Genişlemesi
 
**Hedef:** Linux x86-64'ün ötesine geçmek.
 
| Durum | Madde |
|---|---|
| FİKİR | Çapraz derleme: `--target windows-x86_64` |
| FİKİR | Çapraz derleme: `--target linux-arm64` |
| FİKİR | Çapraz derleme: `--target riscv64` |
| FİKİR | macOS desteği |
 
## Faz 7 — Geliştirici Deneyimi
 
**Hedef:** IDE seviyesinde destek ve dokümantasyon.
 
| Durum | Madde |
|---|---|
| FİKİR | [kailsp](https://github.com/kaizenium/kailsp): Dil Sunucusu (otomatik tamamlama, tanıma git, tanılama) |
| FİKİR | [kaidoc](https://github.com/kaizenium/kaidoc): dokümantasyon üretici |
| FİKİR | Paket ekosistemi (`shared/` topluluk deposu) |
 
## Faz 8 — Kendi Kendine Derleme (Self-Host)
 
**Hedef:** Kai derleyicisinin Kai ile yazılması.
 
| Durum | Madde |
|---|---|
| FİKİR | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap): bootstrap derleyici |
| FİKİR | Mevcut derleyiciyi Kai'ye taşı |
| FİKİR | Stabil bir ABI tanımla |
 
---
 
## Şu An Neredeyiz?
 
Proje **Faz 0**'da - dil spesifikasyonu aktif olarak üzerinde çalışılıyor. Faz 1'e (Sözcük Çözümleyici ve Ayrıştırıcı) geçiş, spesifikasyon üzerine inşa edilebilecek kadar olgunlaştığında başlayacak.
 
## Katkıda Bulunmak İster misiniz?
 
Bu aşamada en değerli katkı, [about-kai](https://github.com/kaizenium/about-kai) spesifikasyonu üzerine tartışma ve geri bildirimdir. Faz 1 başladığında kod katkıları için ayrı bir çağrı yapılacaktır.
