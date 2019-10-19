etl主要讲下面几个有特殊处理的。你们先提前熟悉一下吧。
估值表gzhJob.kjb
委托资产余额表wtyeJob.kjb
存款表ckJob.kjb
债券信用评级变动表zhaijuanpingjijob.kjb
指数表zhishu.kjb

## 1.估值表gzhJob.kjb

删除估值表数据 ${Internal.Job.Filename.Directory}/gzh_delete.kjb

删除估值历史表数据${Internal.Job.Filename.Directory}/gzh_delete.kjb

清空估值表中间表数据 truncate table tmp_ods_port_value

同步估值中间表 ${Internal.Job.Filename.Directory}/gzhTabletemp.ktr

同步估值表${Internal.Job.Filename.Directory}/gzhTable_sharding.ktr

同步科目对照表${Internal.Job.Filename.Directory}/kmzqdzTable.ktr



## 2.委托资产余额表wtyeJob.kjb

删除委托资产余额表数据${Internal.Job.Filename.Directory}/comjb_delete_table.kjb

同步委托资产余额补全数据${Internal.Job.Filename.Directory}/wtye_buquan.ktr



## 3.存款表ckJob.kjb



## 4.债券信用评级变动表zhaijuanpingjijob.kjb



## 5.指数表zhishu.kjb

ETL抽取说明文档，数据库设计文档portfolio数据表.xlsx

中石油数据库初期配置参照表