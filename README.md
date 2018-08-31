# Redis

由於近幾年來Web 2.0網站與社群網站盛行，於是開始出現採用如NoSQL資料庫解決網站的資料流量急速增漲的問題，並且NoSQL資料庫具備水平擴充能力，只要增加新的伺服器節點，就能夠不斷擴充資料庫的容量。

Redis是近年來出現NoSQL開源資料庫的一種，並且將資料存放在記憶體中，以提升讀取的效率。Redis的長處，在於提供豐富的資料型態操作，例如Hashs、Lists、Sets、Sorted Sets、HyperLogLog等，並內建複寫（replication）與叢集功能，以及能夠直接就地更新作業的特性。

REmote DIctionary Server (Redis) 是一個由Salvatore Sanfilippo寫的key-value存儲系統。Redis是一個開源的使用ANSI C語言編寫、遵守BSD協議、支持網絡、可基於內存亦可持久化的日誌型、Key-Value數據庫，並提供多種語言的API。它通常被稱為數據結構服務器，因為值 (value) 可以是字符串 (String), v (Map), 列表 (list), 集合 (sets) 和有序集合 (sorted sets) 等類型。

## Memcached vs. Redis
較於同為NoSQL記憶體資料庫的Memcached，Redis 通常只會使用處理器的單一執行緒，若真的想要利用多核處理器，在建置上可以採多個 Redis 實例（Instance），以充分應用CPU硬體資源，但設定及操作上有許多需要注意之處，效果有好有壞。Redis使用jemalloc及tcmalloc模式降低記憶體碎片化的情況，而不採用Free-list或其他方法，是為了維持其簡單、單純、較有效率的設計原則，相較之下，Memcached採用預先分配的方式，雖然較能有效降低記憶體碎片化問題，卻會帶來浪費空間的情況。Memcached與Redis有許多的架構上的差異，例如Memcached支援多個處理器核心和執行緖，較能充分利用現代處理器的效能，並且採用預先分配的記憶體池零碎空間，減少記憶碎片，而使得實際的記憶體使用量較Redis要少，以及記憶體分配壓力也同時減少。

## Redis basics
* Redis主要以key/value為儲存的方式
* 但請注意，它能當成cache使用，卻無法當成永久性的儲存(persistence)。若你希望系統當機重新啟動後資料仍存在，redis便不適用。
* 性能極高 – Redis能讀的速度是110000次/s,寫的速度是81000次/s 。
* 豐富的數據類型– Redis支持二進制案例的Strings, Lists, Hashes, Sets 及Ordered Sets 數據類型操作。
* 原子 – Redis的所有操作都是原子性的，同時Redis還支持對幾個操作全併後的原子性執行。
* 豐富的特性 – Redis還支持publish/subscribe, 通知, key 過期等特性。

![alt text](redis.png "redis logo")
