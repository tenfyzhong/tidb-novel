# 《平凯仙录：云起分布式》

以掌握 TiDB 核心技术体系为主线的硬核严密修仙中篇。天生单机伪灵根的杂役弟子莫寻，在没落宗门藏经阁得上古《平凯玄天录》残卷，随器灵东旭真君修习分布式天道，将 SQL 优化、CBO、Raft、LSM-Tree、PD/TSO、Percolator、HTAP 与容灾化为斗法神通。

## 阅读顺序

1. [术语对照与设定集](novel/glossary.md)
2. 第一卷 灵台初开与算力破障（炼气·筑基）
   - [第一章 藏经阁的爆仓之灾](novel/01-disk-full-crisis.md)
   - [第二章 聚簇真诀，前缀神行](novel/02-clustered-index.md)
   - [第三章 天机算筹，识海化神](novel/03-compute-and-ast.md)
   - [第四章 移山倒海，算子下推](novel/04-cbo-and-pushdown.md)
3. 第二卷 后土厚德与三清共契（结丹·元婴）
   - [第五章 后土枯荣，七阶千叶楼](novel/05-lsm-tree.md)
   - [第六章 三清同契，落雷不灭](novel/06-raft-consensus.md)
   - [第七章 灵脉胞衣，九天分形](novel/07-region-split-merge.md)
   - [第八章 太初时钟，定鼎时空](novel/08-tso-and-pd.md)
   - [第九章 踏天两步，因果不沾](novel/09-percolator-2pc.md)
4. 第三卷 阴阳相生与万界混元（化神·飞升）
   - [第十章 大日金乌，破妄真瞳](novel/10-htap-and-tiflash.md)
   - [第十一章 巨石之狂，单机终途](novel/11-scale-up-vs-scale-out.md)
   - [第十二章 天裂地陷，混沌天魔](novel/12-network-partition-and-hotspot.md)
   - [第十三章 巡天观象，化险为夷](novel/13-dashboard-and-diagnostics.md)
   - [第十四章 云起平凯，万界飞升](novel/14-pingcap-ascension.md)

## 世界观梗概

数灵界因果皆由数符凝练，宗门功业记于玉简表。旧法单机巨灵道追求单体无限壮大，遭磁盘告磬、锁心魔、天火焚神三绝劫；碎玉分身术（分库分表）则把灵脉斩断，跨界事务九死一生。平凯混元大阵以无状态计算（TiDB）、统天调度（PD/TSO）、后土行存（TiKV：LSM + Raft + Region）、列式金乌（TiFlash Learner）与两仪定因锁（Percolator）开河，取代一口井。

## 主要人物

- **莫寻**：太数门杂役，单机伪灵根，分布式真传传人。
- **东旭真君**：《平凯玄天录》器灵，毒舌学究，讲法不代打。
- **石天霸**：巨石宗少主，Scale-Up 极道。

## 篇幅

十四章正文合计约 4.5 万字（`wc -m`），各章 2800～3600 字；另附术语设定集。
