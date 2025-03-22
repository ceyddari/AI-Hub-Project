## Metro Simülasyonu

Bu proje, bir metro ağı üzerinde en az aktarmalı ve en hızlı rotaları bulan bir simülasyon sistemidir. 
Breadth-First Search (BFS) ve A* algoritmaları kullanılmıştır.

## Proje Amacı

- Metro ağını graf yapısıyla modellemek
- BFS ile **en az aktarma** yapılan rotayı bulmak
- A* algoritması ile **en hızlı** (süre bazlı) rotayı bulmak

## Kullanılan Teknolojiler ve Kütüphaneler

- **Python 3**
- `collections.deque`: BFS algoritması için kuyruk yapısı sağlar.
- `heapq`: A* algoritmasında öncelik kuyruğu için kullanılır.
- `typing`: Fonksiyonların giriş-çıkış türleri için anotasyon sağlar.


## Algoritmaların Çalışma Mantığı

###  BFS – En Az Aktarmalı Rota
- Metro ağı bir graf olarak modellenir.
- BFS algoritması, komşu istasyonları sırayla gezerek hedefe ulaşmaya çalışır.
- Her adımda en kısa adım sayılı yol aranır, böylece en az aktarmalı rota elde edilir.

###  A* – En Hızlı Rota
- Her istasyonun komşularına geçiş süresi dikkate alınır.
- A* algoritması (heuristic olmadan Dijkstra gibi), öncelik kuyruğunda toplam süreye göre çalışır.
- Hedef istasyona **en düşük toplam süreyle** ulaşılan yol döndürülür.

---

## Örnek Kullanım ve Test Sonuçları

Aşağıdaki örnek metro ağı kullanılmıştır:

- **Kırmızı Hat**: Kızılay, Ulus, Demetevler, OSB
- **Mavi Hat**: AŞTİ, Kızılay, Sıhhiye, Gar
- **Turuncu Hat**: Batıkent, Demetevler, Gar, Keçiören

Test senaryoları:

```text
1. AŞTİ ➝ OSB
   - En az aktarmalı rota: AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB
   - En hızlı rota (süre): AŞTİ -> Kızılay -> Demetevler -> OSB (toplam süre: XX dk)

2. Batıkent ➝ Keçiören
   - En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
   - En hızlı rota (süre): Batıkent -> Demetevler -> Gar -> Keçiören

3. Keçiören ➝ AŞTİ
   - En az aktarmalı rota: Keçiören -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
   - En hızlı rota (süre): Keçiören -> Gar -> M4 -> M3 -> M2 -> M1
