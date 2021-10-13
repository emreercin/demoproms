---
title: "Bayes Ağları"
date: 2018-11-28T15:14:39+10:00
featured: true
weight: 2
---

BA’lar bir grup değişken arasındaki birleşik olasılık dağılımını temsil eden grafiksel modellerdir (Pearl, 1988).

Bir BA grafiksel yapı ve parametreler olmak üzere iki parçadan oluşur. Grafiksel yapı yönlü döngüsüz graftır. Graftaki düğümler değişkenleri, oklar değişkenler arasındaki ilişkileri temsil eder. Bir BA’daki iki düğüm A ve B, A’dan B’ye doğrudan bir ok ile bağlıysa A B’nin ebeveyni, B A’nın çocuğudur. Her düğümün ebeveynleriyle olan koşullu olasılık dağılımını tanımlayan parametreleri vardır. Kesikli BA’larda bu parametreler koşullu olasılık tablolarında tanımlanır.

BA’da herhangi bir grup değişkene değer girildiğinde, diğer bilinmeyen değişkenlerin sonsal olasılık dağılımı birleşim ağacı gibi çıkarım algoritmalarıyla hesaplanabilir (Lauritzen ve Spiegelhalter, 1988). Değişkene değer girme işlemine kanıt girme veya gözlem girme de denilir. BA’daki olasılıksal çıkarımlar ile ebeveynlerden çocuğa doğru tahminsel çıkarım, çocuklardan ebeveyne doğru teşhissel çıkarım veya çocuk bilindiğinde ebeveynler arasında hepten gidişsel çıkarım hesaplanabilir.

Olasılıklar çıkarım algoritmalar HBSÖ’ler için kullanışlıdır. BA olarak modellenmiş bir HBSÖ’de herhangi bir soru kümesine değer girildiğinde, diğer soruların ve gizli faktörlerin sonsal dağılımları hesaplanabilir. BA’lar bilgiye, veriye veya bu ikisinin birleşimine dayanarak yapılabilir. BA yapısı bilgiye dayalı şekilde yapıldığında, modeldeki oklar konu hakkındaki neden-sonuç ilişkilerine göre belirlenir. BA’ları tamamen veriden öğrenmek için yapı öğrenme algoritmaları bulunmaktadır. Bu algoritmalar skor-bazlı, kısıt-bazlı ve melez algoritmalar olmak üzere üç gruba ayrılmaktadır. Skor bazlı algoritmalar, modelin veriye uyumunu ödüllendiren, model karmaşıklığını cezalandıran, regüle edilmiş skorları optimize eden yapıyı bulmayı amaçlar (Games vd., 2011). Bayes bilgi kriteri gibi skorlar bu amaca uygundur. Kısıt-bazlı algoritmalar veriye koşullu bağımsızlığı tespit etmek için istatistiksel testler uygular ve tespit edilen koşullu bağımsızlıklara uyumlu BA yapısını öğrenir (Le vd., 2019). Melez algoritmalar, skor-bazlı ve kısıt-bazlı prensipleri birleştirir. Örneğin, max-min tırmanma algoritması kısıt-bazlı testler uygulayarak modelin grafiksel yapısını yönsüz olarak bulur, daha sonra skor-bazlı tırmanma algoritması kullanarak yönleri belirlemeyi amaçlar (Tsamardinos vd., 2006).

__*To read the English version of the post, click [here](/services/bayesian-networks/).*__

# Kaynaklar

- Pearl, J. 1988. "Probabilistic Reasoning in Intelligent Systems". Morgan Kaufmann.
- Lauritzen, S. L., Spiegelhalter, D. J. 1988. "Local Computations with Probabilities on Graphical Structures and Their Application to Expert Systems". Journal of the Royal Statistical Society: Series B (Methodological), 50(2), 157–194.
- Gámez, J. A., Mateo, J. L., Puerta, J. M. 2011. "Learning Bayesian networks by hill climbing: efficient methods based on progressive restriction of the neighborhood". Data Mining and Knowledge Discovery, 22(1–2), 106–148.
- Le, T. D., Hoang, T., Li, J., Liu, L., Liu, H., Hu, S. 2019. "A Fast PC Algorithm for High Dimensional Causal Discovery with Multi-Core PCs". IEEE/ACM Transactions on Computational Biology and Bioinformatics, 16(5), 1483–1495.
- Tsamardinos, I., Brown, L. E., Aliferis, C. F. 2006. "The max-min hill-climbing Bayesian network structure learning algorithm". Machine Learning, 65(1), 31–78.
