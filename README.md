# Redis

由於近幾年來 Web 2.0 網站與社群網站盛行，於是開始出現採用如 NoSQL 資料庫解決網站的資料流量急速增漲的問題，並且 NoSQL 資料庫具備水平擴充能力，只要增加新的伺服器節點，就能夠不斷擴充資料庫的容量。

Redis 是近年來出現 NoSQL 開源資料庫的一種，並且將資料存放在記憶體中，以提升讀取的效率。Redis 的長處，在於提供豐富的資料型態操作，例如 Hashs、Lists、Sets、Sorted Sets、HyperLogLog 等，並內建複寫（replication）與叢集功能，以及能夠直接就地更新作業的特性。

REmote DIctionary Server (Redis) 是一個由Salvatore Sanfilippo寫的key-value存儲系統。Redis是一個開源的使用ANSI C語言編寫、遵守BSD協議、支持網絡、可基於內存亦可持久化的日誌型、Key-Value數據庫，並提供多種語言的API。它通常被稱為數據結構服務器，因為值 (value) 可以是字符串 (String), v (Map), 列表 (list), 集合 (sets) 和有序集合 (sorted sets) 等類型。

## Memcached vs. Redis
較於同為 NoSQL 記憶體資料庫的 Memcached，Redis 通常只會使用處理器的單一執行緒，若真的想要利用多核處理器，在建置上可以採多個 Redis 實例（Instance），以充分應用CPU硬體資源，但設定及操作上有許多需要注意之處，效果有好有壞。Redis 使用 jemalloc 及 tcmalloc 模式降低記憶體碎片化的情況，而不採用 Free-list 或其他方法，是為了維持其簡單、單純、較有效率的設計原則，相較之下，Memcached 採用預先分配的方式，雖然較能有效降低記憶體碎片化問題，卻會帶來浪費空間的情況。Memcached 與 Redis 有許多的架構上的差異，例如 Memcached 支援多個處理器核心和執行緖，較能充分利用現代處理器的效能，並且採用預先分配的記憶體池零碎空間，減少記憶碎片，而使得實際的記憶體使用量較 Redis 要少，以及記憶體分配壓力也同時減少。

## Redis basics
* Redis 主要以 key/value 為儲存的方式
* 但請注意，它能當成 cache 使用，卻無法當成永久性的儲存 (persistence)。若你希望系統當機重新啟動後資料仍存在，redis 便不適用。
* 性能極高 – Redis 能讀的速度是 110000 次/s,寫的速度是 81000 次/s 。
* 豐富的數據類型– Redis 支持二進制案例的 Strings, Lists, Hashes, Sets 及 Ordered Sets 數據類型操作。
* 原子 – Redis 的所有操作都是原子性的，同時 Redis 還支持對幾個操作全併後的原子性執行。
* 豐富的特性 – Redis 還支持 publish/subscribe, 通知, key 過期等特性。
* 和 MongoDB 不同，並沒有 schema 的概念，常被用作快取系統。

![alt text](redis.png "redis logo")

## 什麼是 Redis？
Redis 是一種內存資料庫(in-memory)的架構，可以被當作一個簡易的資料庫(key-value database)，這功能就讓我想起 Android 的 Shared Preferences 一樣是可以將資料存在用戶自己的裝置中，也等同於網頁中的 cookie、localStorage，Redis 使用 RAM 來存取資料所以相對來得快速，缺點是重開機後記憶體就會被釋放掉，但 Redis 有個功能 persistence 可以解決這個問題，此外 Redis 也能設定資料的生命週期(Expire)當你在儲存資料的時候，你可以新增一個 Expire time 的參數，時間一到之後，這個 key 就會自動被清除。

## 教學

[https://blog.techbridge.cc/2016/06/18/redis-introduction/](https://blog.techbridge.cc/2016/06/18/redis-introduction/)

[https://aws.amazon.com/tw/redis/](https://aws.amazon.com/tw/redis/)
