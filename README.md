# Kuantum Sonrası Çok Değişkenli Açık Anahtar Kriptosistemleri (Post-Quantum MQ Cryptosystems)

Bu repository, "Kuantum Sonrası Çok Değişkenli Açık Anahtar Kriptosistemlerinin İncelenmesi" başlıklı yüksek lisans tezi kapsamında geliştirilen referans implementasyonları ve kriptanaliz simülasyonlarını içermektedir. 

Çalışma, Çok Değişkenli Polinom Tabanlı (ÇDPT) kriptografinin tarihsel gelişimini, matematiksel temellerini ve modern standartlaştırma süreçlerindeki (NIST PQC) güncel algoritmalardan tez kapsamında ilgilenilen temel yapıları bilgisayar cebiri sistemi SageMath üzerinde somutlaştırmayı amaçlamaktadır.

## 📌 İçerik ve Algoritmalar

Repository, tezin ilgili bölümlerine paralel olarak üç ana kategoride düşünülebilir:

### 1. Temel Çarpanlara Ayırma Algoritmaları (Bölüm 4)
Sonlu cisimler üzerinde polinomların çarpanlara ayrılması için gerekli temel cebirsel araçlar:
*   **Karesiz Çarpanlara Ayırma (Square-Free Factorization - SFF):** Monik polinomların karesiz bileşenlerine ayrıştırılması.
*   **Berlekamp Algoritması:** Çekirdek (nullspace) hesabı ve Frobenius endomorfizması kullanılarak indirgenemez çarpanların bulunması.
*   **Cantor-Zassenhaus Algoritması:** DDF (Distinct-Degree) ve EDF (Equal-Degree) aşamalarıyla olasılıksal çarpanlara ayırma.

### 2. BigField Tabanlı Sistemler (Bölüm 5)
Cisim Genişlemeleri ($\\mathbb{F}_{q^n}$) üzerinde tanımlanan tek değişkenli polinomların kullanıldığı öncü sistemler ve varyantları:
*   **Matsumoto-Imai (MI / C*):** BigField ailesinin temelini atan orijinal kriptosistem.
*   **PMI (Perturbed MI):** Lineerleştirme saldırılarına karşı iç karıştırma (gürültü) eklenmiş MI varyantı.
*   **SFLASH (C*-Minus):** Minus modifikasyonu ile güçlendirilmiş dijital imza şeması.
*   **Temel HFE (Hidden Field Equations):** Derece sınırı (D) ile kurgulanmış genel merkez dönüşüm mimarisi.
*   **HFEv- (Vinegar + Minus):** NIST PQC adaylarına (GeMSS, Gui vb.) temel oluşturan modern HFE varyantı.

### 3. Oil and Vinegar (OV) Tabanlı Sistemler (Bölüm 6)
Doğrudan temel sonlu cisim ($\\mathbb{F}_q$) üzerinde çalışan ve modern ÇDPT tasarımlarının odak noktasını oluşturan sistemler:
*   **UOV (Unbalanced Oil and Vinegar):** Klasik OV şeması ve imzalama süreçleri.
*   **Kipnis-Shamir Kriptanalizi:** Balanced OV şemasına yönelik, invaryant alt uzaylar kullanılarak yapılan denk anahtar bulma saldırısı. (Tek ve Çift Karakteristik için iki ayrı simülasyon).
*   **Rainbow:** UOV'nin çok katmanlı genellemesi.
*   **Modern UOV Reformülasyonu:** Açık anahtarın doğrudan gizli oil uzayını sıfırlayacak şekilde inşa edildiği, NIST 3. tur adayı UOV yaklaşımı.
*   **MAYO:** Küçük bir UOV dönüşümünü *whipping* tekniğiyle genişleterek anahtar boyutunu optimize eden güncel imza şeması.

## 🛠️ Kurulum ve Gereksinimler

Bu projedeki kodlar, matematiksel hesaplamalar ve sonlu cisim aritmetiği için [SageMath](https://www.sagemath.org/) ortamında geliştirilmiştir. (Minimum sürüm: SageMath 9.3+).

Çevrimiçi (Online) Çalıştırma ve Parametre Özelleştirme:
Bilgisayarınıza herhangi bir kurulum yapmadan da kodları test edebilirsiniz. Notebook'ların içindeki ilgili hücrelerdeki kod bloklarını sırasıyla alt alta kopyalayarak SageMathCell (https://sagecell.sagemath.org/) çevrimiçi derleyicisine yapıştırıp doğrudan çalıştırabilirsiniz. Ayrıca, kodların başındaki senaryo kısmında yer alan parametreleri ($q, n, m, v, o$ vb.) değiştirerek farklı parametre setlerinde yeni örnekler ve kriptografik simülasyonlar üretebilirsiniz.

Dosyalar `.ipynb` (Jupyter Notebook) formatındadır. Çevrimdışı olarak çalıştırmak için:
1. SageMath ortamını bilgisayarınıza kurun.
2. Jupyter Notebook'u SageMath çekirdeği ile başlatın:
   
