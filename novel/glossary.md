# 《平凯仙录：云起分布式》术语对照与设定集

全书修仙概念与 TiDB 技术一一对应。后续章节用词一律依本表，不得另起别名。

## 世界

| 修仙称谓 | 技术对应 | 法则 |
| --- | --- | --- |
| 数灵界 | 数据世界 | 天地因果皆由数符凝练，宗门功业记于玉简表 |
| 数符 | Data Record / Row | 最小因果单元，写入即落因果 |
| 玉简表 | Table | 宗门账册，列字段、行因果 |
| 命牌 | Primary Key / 主键行 | 弟子身份唯一印记 |
| 青云单机鉴 | 单机数据库实例 | 太数门旧法核心宝鉴，Scale-Up 遗物 |
| 太数门 | 旧法宗门 | 百年大典仍托身单机巨灵道 |
| 巨石宗 | Scale-Up 阵营 | 以巨资堆砌单体算力 |
| 大千交易所 | 跨库跨城交易系统 | 依赖全局时序与分布式事务 |
| 青云仙盟 | 多宗联盟业务 | 同时需要 OLTP 流转与 OLAP 推演 |

## 人物

| 名 | 身份 | 定型 |
| --- | --- | --- |
| 莫寻 | 太数门杂役，天生单机伪灵根 | 敏锐、身份卑微，后为分布式真传传人 |
| 东旭真君 | 《平凯玄天录》器灵 | 毒舌学究，讲解硬核机理，不代主角出手 |
| 执事 | 太数门执事 | 盲目加大单机内存灵石 |
| 石天霸 | 巨石宗少主 | 祭出八十一路纯阳神机巨灵傀儡 |

## 境界

| 境界 | 对应篇章 | 技术跨越 |
| --- | --- | --- |
| 炼气·筑基 | 第一卷 第 1–4 章 | 从单机崩溃到计算层无状态化、CBO 与下推 |
| 结丹·元婴 | 第二卷 第 5–9 章 | LSM、Raft、Region、TSO、Percolator |
| 化神·飞升 | 第三卷 第 10–14 章 | HTAP、Scale-Out、容灾、诊断、CDC/BR |

## 旧法与劫难

| 修仙称谓 | 技术对应 | 要点 |
| --- | --- | --- |
| 单机巨灵道 | Scale-Up | 追求单体肉身无限壮大 |
| 玄天单机宝鉴 | 单体数据库机器 | 灵石堆内存、堆磁盘、堆 CPU |
| 磁盘告磬之劫 | Disk Full | 写满即死，WAL 与数据文件争盘 |
| 锁心魔 | Deadlock / Lock Timeout | 行锁表锁互噬，事务无法前进 |
| 天火焚神 | CPU 100% 熔断 | 慢查询与全表扫描烧尽算力 |
| 识海漫灌 | Full Table Scan | 无索引盲查 |
| 连接池爆满 | Too Many Connections | 并发连接耗尽，新因果无法入界 |
| 碎玉分身术 | Sharding / 分库分表 | 斩断主灵脉，跨界事务九死一生 |
| 乾坤停机大挪移 | 停机扩容 / reshard | 灵脉变迁必须停机搬迁 |
| 时间漂移 | NTP 抖动 / 物理时钟乱序 | 微秒级乱序即可因果倒置 |
| 因果死锁死海 | 分布式死锁 | 多修士互锁，无人能提交 |
| 虚空绝灵网 | Network Partition | 网络分区，脑裂风险 |
| 焚天热点暴击 | Write Hotspot | 单一 Key / Region 写洪流 |
| 脑裂 | Split-brain | 双主互写，因果分叉 |

## 平凯混元大阵

| 修仙称谓 | 技术对应 | 法则 |
| --- | --- | --- |
| 《平凯玄天录》 | TiDB 真传残卷 | 上古分布式天道 |
| 平凯混元大阵 | TiDB 分布式体系 | 计算、调度、存储、分析、事务一体 |
| 天道识海·TiDB 节点 | TiDB SQL 层 | 无状态计算化身，可瞬息化身成千上百 |
| 法旨解析 | SQL Parsing | Lexer / Parser 将符咒化为可推演结构 |
| 抽象语法树 | AST | 符咒抽丝剥茧后的逻辑骨架 |
| 天机算筹·Explain 破妄诀 | EXPLAIN / 逻辑优化 | 谓词下推、列裁剪、子查询去关联 |
| 移山倒海·Coprocessor 秘术 | Coprocessor 下推 | 过滤、聚合下推后土地脉，减少网络往返 |
| CBO 天道算筹 | Cost-Based Optimizer | 统计信息、基数估算、选物理算子 |
| 聚簇前缀神引法 | Clustered Index + 前缀/复合索引 | 主键聚簇排布，点查取代盲查 |
| 回表之滞 | IndexLookUp | 二级索引需再回聚簇取行 |
| 混元统天盘·PD | Placement Driver | 调度中枢、拓扑、Region 迁移、TSO |
| 太初时序印 | TSO | 全局单调递增逻辑时间，批量预分配 |
| 后土万象界·TiKV | TiKV | 行存 KV，LSM + Raft + Region |
| LSM-Tree 枯荣心法 | LSM-Tree | MemTable → Immutable → SST 分层压缩 |
| 晨露之泉 | MemTable | 内存可写层 |
| 冰心 | Immutable MemTable | 冻结待落盘，不再接受新写 |
| 七层金阶 / 千叶楼 | Leveled Compaction / SST | 写放大、读放大、空间放大互相制衡 |
| 写放大心魔 | Write Stall / Write Amplification | 压缩跟不上写入则停写自保 |
| Raft 三清共识契约 | Raft | 一 Leader 二 Follower，多数派过半提交 |
| 租约神读 | Lease Read | Leader 持有租约，本地读不必每次走 Raft |
| 灵脉胞衣 | Region | 连续 Key-Range，默认约 96MB～144MB 切分 |
| 气满则分裂 | Region Split | 体积或写入过载则切 |
| 战后归并 | Region Merge | 过小 Region 合并 |
| 神念散星诀 | Scatter Region / 打散热点 Key | 把单点写洪流拆到万千星辰 |
| 大日金乌镜·TiFlash | TiFlash | 列式存储，OLAP |
| 破妄真瞳 | OLAP 分析 | 宽表扫描、聚合、实时推演 |
| Learner 契约 | Raft Learner | 异步复制，不参与选举，对 TP 零锁竞争 |
| 阴阳双生 HTAP | HTAP | 行存事务与列存分析同生 |
| 两仪定因锁 | Percolator | Primary Lock 锚定，Secondary Lock 护持 |
| 踏天两步 | 2PC：Prewrite + Commit | 本命印落成则万法皆成 |
| 破执 Resolve | Resolve Lock | 断线残留锁由后来者根据 Primary 判定提交或回滚 |
| 快照隔离金身 | Snapshot Isolation | 按 start_ts 看世界，读写互不脏读 |
| 天道巡天图谱 | TiDB Dashboard | 慢查询、热点、拓扑一图尽览 |
| 万象灵火谱 | Key Visualizer | 以热力观察访问模式 |
| 乾坤化雨术 | TiCDC | 变更数据捕获，流向异构仙朝 |
| 造化神舟 | BR Backup & Restore | 分布式物理备份与极速恢复 |

## 斗法招式与物理算子

| 招式 | 技术 | 适用 |
| --- | --- | --- |
| 索引连环斩 | IndexJoin | 外表小、内表有可用索引 |
| 混元散列绞 | HashJoin | 等值连接，内存可承一侧 |
| 双脉合流斩 | MergeJoin | 两侧有序，可归并 |
| 笛卡尔深渊 | Cartesian Product | 无连接条件的跨表绞杀，必须识破 |

## 扩展之道

| 修仙称谓 | 技术对应 | 法则 |
| --- | --- | --- |
| 单机极道 | Scale-Up | 物理瓶颈与边际成本陡增 |
| 万界混元 / 水平铺开 | Scale-Out | 计算与存储解耦，在线扩缩容 |
| 无状态法身千尊 | TiDB 计算节点水平扩展 | 加节点即加解析与优化能力 |
| 万座龙脉结界 | TiKV 存储水平扩展 | Region 调度迁入新节点，无需停机 |

## 硬性不变量（写作禁区）

1. Raft 提交必须多数派过半；两副本不能在分区时同时称帝，禁止脑裂双写。
2. LSM 必含 MemTable、Immutable MemTable、SST 分层；压缩滞后可写停，不可假装无限写。
3. Percolator 以 Primary Lock 判定事务生死；Commit 只落 Primary，Secondary 可异步决议。
4. TSO 必须全局单调递增；物理时钟不得充当跨节点因果顺序。
5. TiFlash 以 Learner 复制，不抢 Leader、不加 TP 行锁。
6. Region 是连续 Key-Range，不是哈希槽；默认切分线约 96MB～144MB。
7. 计算层无状态，状态只在 PD 与 TiKV；莫寻识海可化千身，肉身不必扛数据。
