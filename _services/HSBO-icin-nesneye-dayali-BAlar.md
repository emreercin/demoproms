---
title: "HSBÖ için Nesneye Dayalı BA"
date: 2018-11-28T15:15:26+10:00
featured: true
weight: 3
---

HBSÖ’ler için BA, X ve C şeklinde iki ayrık değişken kümesinden oluşan BA olarak tanımlanacaktır. X HBSÖ’deki soru maddelerinin kümesini, C de HBSÖ’nün ölçmeyi amaçladığı gizli faktörlerin kümesini temsil eder.

HBSÖ BA’larının sabit bir yapısı yoktur. Model eldeki kaynaklara göre HBSÖ verisinden veya uzman bilgisinden öğrenilebilir. Örneğin, Şekil 2’de eğitimde ölçme değerlendirme BA yapısına dayanan bilgi temelli bir HBSÖ yapısı verilmektedir. Bu yapıda soru maddeleri gizli faktörlerin çocuklarıdır. Uzman bilgisine dayalı olarak bu yapı değiştirilebilir. Örneğin, gizli faktörler arasında doğrudan ilişkiler varsa, bunlar modele eklenebilir. Bunun yanında, skor-bazlı, kısıt-bazlı veya melez BA öğrenme algoritmaları HBSÖ yapısını tamamen veriden öğrenmek için kullanılabilir.

<figure>
<img src="/images/oobn.png" alt="Trulli" style="width:100%">
<figcaption align = "center"><b>Şekil 2. HBSÖ için Bilgi Temelli BA Yapısı Örneği</b></figcaption>
</figure>

Genellikle tek bir HBSÖ’nün karar vermedeki katkısı kısıtlıdır. Bir doktor, karar verirken birden çok HBSÖ’nün yanında, diğer klinik değişkenleri ve hasta tercihlerini de değerlendirir. HBSÖ BA’larının da kullanışlı karar destek sağlayabilmesi için modüler şekilde daha büyük yapıdaki olasılıksal modellere entegre olabilmesi gerekmektedir.

Nesneye Dayalı Bayes Ağları (NDBA) HBSÖ’lere bu modülerliği sağlamak için uygun bir yapı sunmaktadır. Bir NDBA nesnesi çıktı değişkenler O, girdi değişkenler I ve kapsüllenmiş değişkenler E olmak üzere üç ayrık değişken kümesinden oluşur (Koller ve Pfeffer, 1997). Nesne içindeki kapsüllenmiş değişkenlerin ebeveyn ve çocuk değişkenleri sadece nesne içindeki diğer değişkenler olabilir; kapsüllenmiş değişkenler nesne dışından ebeveyn ve çocuklara sahip olamazlar. Çıktı değişkenler, nesne dışından çocuk değişkenlere sahip olabilirler. Girdi değişkenler, kendileri nesne dışından olan ve nesne içinde çocuk değişken sahibi olan değişkenler için yer tutuculardır. Girdi değişkenler, nesne içinden çocuk değişkenlere sahip olabilirler fakat kendileri nesne içindeki başka bir değişkenin çocuğu olamazlar. Girdi ve çıktı değişkenler BA nesnesinin arayüzünü oluşturur. Sadece girdi ve çıktı değişkenler BA dışında ebeveyn ve çocuğa sahip olabilirler (NDBA hakkında daha detaylı bilgi için Koller ve Pfeffer (1997) incelenebilir).

HBSÖ BA çıktı değişkenleri gizli faktörler O := C, kapsüllenmiş değişkenleri soru maddeleri olan E := X bir NDBA nesnesidir. Gizli faktörler ve soru maddelerinin nesne dışındaki ebeveynleri de girdi değişkenlerdir. Girdi değişkenler yaş, cinsiyet gibi hasta bilgisi veya nedensel faktörler olabilir. Girdi değişkenler HBSÖ BA’larını daha kapsamlı ve büyük BA’lara bağlarken önemlidir.

Şekil 3A’da değişik HBSÖ’ler için yapılmış iki HBSÖ BA nesnesinin daha büyük bir modele entegre olmuş hali gösterilmektedir. NDBA bu BA’ları büyük modelle birleştirirken iç yapılarının özelliklerini soyutlamamızı sağlamaktadır. NDBA, BA’ların iç yapısında bir değişiklik yapmadan ve iç yapılarına çok bağlı olmadan, modüler şekilde büyük modellere entegre edilmeyi sağlamaktadır. Şekil 3B’de bu nesnelerin iç yapıları gösterilmektedir.

<figure>
<img src="/images/ndba.png" alt="Trulli" style="width:100%">
<figcaption align = "center"><b>Şekil 3. A - PROM BN Nesnelerinin başka BN modeline entegre olmuş hali, B - PROM Nesnelerinin iç yapıları</b></figcaption>
</figure>

__*To read the English version of the post, click [here](/services/object-oriented-BNs-for-PROM/).*__

# Kaynaklar

Koller, D., Pfeffer, A. 1997. "Object-Oriented Bayesian Networks". Içinde Proceedings of the 13th Conference on Uncertainty in Artificial Intelligence (ss. 302–313). Providence, RI.
