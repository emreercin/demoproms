---
title: "Hasta Uyumlu Soru Seçme"
date: 2021-10-12T15:15:34+10:00
featured: true
weight: 4
usemathjax: true
---

HBSÖ’lerin yaygın olarak kullanımı karşısındaki önemli kısıtlardan bir tanesi fazla soru cevaplama gereksinimi ve eksik girdilere sahip HBSÖ’lerin kullanışsız olmasıdır.

BA’lar ve sahip oldukları olasılıksal çıkarım algoritmaları bu iki sorunun çözümü için de uygun bir ortam sağlar. HBSÖ için BA yapıldığında ne kadar soru cevaplanırsa cevaplansın, birleşim ağacı gibi olasılıksal çıkarım algoritmaları kullanılarak, ölçülen gizli faktörlerin sonsal dağılımları hesaplanabilir. Daha fazla soru cevaplandığında sonsal dağılımlar güncellenebilir. Bir HBSÖ’de genellikle aynı gizli faktöre ilişkin birden çok soru vardır. Eğer bir gizli faktöre ilişkin belirsizlik az ise, yani BA gizli faktör tahmininden emin ise, bu gizli faktöre ilişkin daha fazla soru sormak sonuçları değiştirmeyebilir. Bu durumda daha çok belirsizliğe sahip başka bir faktöre ilişkin soru sormak, tahminler için daha fazla bilgi verecektir.

Kullanıcıya uyumlu soru seçme, bir bilgi ölçüsü kullanarak, hastanın daha önceki cevaplarına göre en yüksek ortalama bilgi kazanımı olan soru sormayı amaçlar (Madigan ve Almond, 1996; Plajner ve Vomlel, 2016). BA’larda, bu işlem her soru sonrasında duyarlılık analizi yapmak ve duyarlılığı en yüksek olan soruyu bir sonraki soru olarak seçmek gibi düşünülebilir. Bir HBSÖ BA’da __*C*__ ölçülmesi amaçlanan gizli faktör olsun, __*x<sub>1</sub>...x<sub>a</sub>*__ daha önce cevaplanan __*X<sub>1</sub>...X<sub>a</sub>*__ sorularına veirlen cevaplar olsun ve __*X<sub>a+1</sub>...X<sub>m</sub>*__ henüz cevaplanmamış sorular olsun. Son olarak __*I(C;X<sub>i</sub>&#124;x<sub>i</sub>...x<sub>a</sub>)*__, __*X<sub>a+1</sub>...X<sub>m</sub>*__ cevapları bilinirken __*X<sub>i</sub>*__ sorusuna verilen cevabın sağladığı ekstra bilgi olsun. HBSÖ BA’da, daha önceki cevaplara göre gizli faktör hakkında en fazla bilgi sağlayan soru seçilecektir.

$$\underset{X{i} \in X}{\operatorname{argmax}}I(C;X{i}|x{1}...x{a})$$

Bunu hesaplamak için bir bilgi ölçüsüne ihtiyaç vardır. Entropi ve ortak enformasyon miktarı bu iş için uygun ölçülerdir. Entropi bir değişkenin belirsizlik miktarını ölçer. Kesikli bir değişken __*C*__’nin entropisi aşağıdaki gibi hesaplanır.

$$H(C)=-\sum{c}P(C)\log(P(C))$$

C ve X değişkenlerinin ortak enformasyon miktarı, X gözlemlendiğinde C hakkında sağladığı ortalama enformasyonu temsil eder. Bu C’nin entropisi ve C’nin X’e koşullu entropisi arasındaki farktır.

$$MI(C;X) = H(C) - H(C|X) = -\sum{c}P(C)\log(P(C)) + \sum{c, x}P(C, X)\log(P(C|X))$$

Eğer bir grup çoklu değişken hakkında enformasyon ölçütü hesaplanmak isteniyorsa, bu değişkenlerin birleşik entropisi aşağıdaki gibi kullanılabilir.

$$MI(C{1},...,C{k};X) = -\sum_{C}P(C{1},...,C{k})\log(P(C{1},...,C{k})) + \sum_{C{1},C{2},...,C{k}, X}P(C{1},...,C{k}, X)\log(P(C{1},...,C{k}|X))$$

Eğer gizli faktör C ikili değişken ise, beklenen kanıt kuvveti da uygun bir enformasyon ölçüsü olabilir (Madigan ve Almond, 1996). Bir gizli faktör C ve bir soru maddesi X arasındaki kanıt kuvveti __*W(L;X)*__, Bayes faktörünün logaritmasıdır.

$$ W(C;X) = \log(\frac{P(X|C)}{P(X|\bar{C})})$$

Beklenen kanıt kuvveti EW(C;X), C’ye koşullu ortalama kanıt kuvvetine eşittir.

$$ EW(C;X) = \sum{x}W(C;X)P(X|C) $$

HBSÖ BA’larında hastaya uyumlu soru sorma, ortak enformasyon miktarı veya beklenen kanıt kuvveti ölçülerinden birini
kullanarak, hastanın daha önce cevap verdiği sorulara göre, her bir cevap verilmemiş sorunun sağladığı bilgiyi ölçerek ve
maksimum enformasyona sahip soruyu seçerek uygulanabilir. Böyle bir algoritma için durma koşulu olarak maksimum
soru sayısı, ortak enformasyon miktarı eşik noktası veya entropi eşik noktası seçilebilir.

__*To read the English version of the post, click [here](/services/patient-coherent-questioning/).*__

# Kaynaklar

- Madigan, D., Almond, R. G. 1996. "On Test Selection Strategies for Belief Networks". Lecture Notes in Statistics, 112, 89–98.
