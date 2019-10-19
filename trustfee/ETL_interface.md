# 1.查询列表数据接口

dpquartz/list
method GET
parameters
offset  偏移数  string  0
limit   列表数  string  10
page    页面数  string  1

example:

request:
http://127.0.0.1:8396/dpquartz/list?page=1&limit=10&offset=0
http://11.53.62.56:8769/dpquartz/list?page=1&limit=20&offset=0
http://127.0.0.1:8396/dpquartz/list?page=1&limit=10&offset=0&jobStatus=0
response:
{"msg":"success","code":0,"page":{"totalCount":8,"pageSize":0,"totalPage":0,"currPage":0,"list":[{"id":18,"cronExpression":"0/10 * * * * ?","methodName":"run1","description":"指标监控","beanClass":"com.rf.cloud.annuity.quartz.task.MonitorJob","jobStatus":"0","jobGroup":"group1","jobName":"MonitorJob","finalFireTime":"2019-08-28T16:47:30.000+0800"},{"id":15,"cronExpression":"0 0 1 * * ? *","methodName":"","description":"用户常用菜单统计任务","beanClass":"com.rf.cloud.annuity.quartz.task.MenuClickTopManaJob","jobStatus":"0","jobGroup":"group1","jobName":"userMenuClickTop","finalFireTime":"2019-06-12T01:10:00.000+0800"},{"id":14,"cronExpression":"0/15 * 15 * * ?","methodName":"","description":"合同到期提醒","beanClass":"com.rf.cloud.annuity.quartz.task.ContractJob","jobStatus":"0","jobGroup":"group1","jobName":"contractJob","finalFireTime":"2019-06-26T02:10:30.000+0800"},{"id":13,"cronExpression":"0 0 16 * * ?","methodName":"execute","description":"","beanClass":"com.rf.cloud.annuity.quartz.task.TrusteeInterfaceTableJob","jobStatus":"0","jobGroup":"","jobName":"trusteeInterfaceTableJob"},{"id":12,"cronExpression":"0 0/5 7-23 * * ?","methodName":"execute","description":"托管系统定时遍历文件数据入库","beanClass":"com.rf.cloud.annuity.quartz.task.TrusteeInterfaceJob","jobStatus":"0","jobGroup":"","jobName":"trusteeInterfaceJob"},{"id":9,"cronExpression":"0 */1 * * * ?","methodName":"excute","description":"定时收邮件","beanClass":"com.rf.cloud.annuity.quartz.task.MailJob","jobStatus":"0","jobGroup":"group1","jobName":"mailJob"},{"id":2,"cronExpression":"0 0/10 * * * ?","methodName":"run1","isConcurrent":"1","description":"定时任务例子","updateBy":"4028ea815a3d2a8c015a3d2f8d2a0002","beanClass":"com.rf.cloud.annuity.quartz.task.WelcomeJob","createDate":"2017-05-19T18:30:56.000+0800","jobStatus":"0","jobGroup":"group1","updateDate":"2017-05-19T18:31:07.000+0800","jobName":"welcomJob","finalFireTime":"2019-08-29T09:20:00.000+0800"}],"page":0,"limit":0}}
# 2.查询或者编辑schema配置信息接口

dpquartz/getJobSchemaIds
http://11.53.62.56:8769/dpquartz/getJobSchemaIds?jobId=29
http://127.0.0.1:8396/dpquartz/getJobSchemaIds?jobId=29

返回：
{"msg":"success","code":0,"page":{"totalCount":37,"pageSize":0,"totalPage":0,"currPage":0,"list":[{"name":"ckJob.kjb","type":"job","grade":2,"describe":"存款表","id":1,"selected":false},{"name":"deletejob.kjb","type":"job","grade":3,"describe":"归档处理","id":2,"selected":false},{"name":"fengbijijinjob.kjb","type":"job","grade":2,"describe":"封闭式基金表","id":3,"selected":false},{"name":"GroupDayFrequencyProfitService","type":"service","grade":2,"describe":"组合日频收益","id":4,"selected":false},{"name":"gubanhangyejob.kjb","type":"job","grade":2,"describe":"行业股板对照表","id":5,"selected":false},{"name":"gupiaojob_s.kjb","type":"job","grade":2,"describe":"股票交易表","id":6,"selected":false},{"name":"gzhJob.kjb","type":"job","grade":2,"describe":"估值表","id":7,"selected":false},{"name":"hangyefenleijob.kjb","type":"job","grade":2,"describe":"财汇_行业分类变动","id":8,"selected":false},{"name":"jigoupingjijob.kjb","type":"job","grade":2,"describe":"财汇_机构信用评级","id":9,"selected":false},{"name":"jigouziliaojob.kjb","type":"job","grade":2,"describe":"公司基本资料表","id":10,"selected":false},{"name":"jijinjob_s.kjb","type":"job","grade":2,"describe":"基金交易表","id":11,"selected":false},{"name":"kaifangjijinjob.kjb","type":"job","grade":2,"describe":"开放式基金表","id":12,"selected":false},{"name":"kmyeJob.kjb","type":"job","grade":2,"describe":"科目余额表","id":13,"selected":false},{"name":"ssgsjob.kjb","type":"job","grade":2,"describe":"上市公司财务指标表","id":14,"selected":false},{"name":"wtyeJob.kjb","type":"job","grade":2,"describe":"委托资产余额表","id":15,"selected":false},{"name":"zhaijuanguzhijob_s.kjb","type":"job","grade":2,"describe":"债券估值表","id":16,"selected":false},{"name":"zhaijuanpingjijob.kjb","type":"job","grade":2,"describe":"债券信用评级变动表","id":17,"selected":false},{"name":"zhaijuanziliaojob.kjb","type":"job","grade":2,"describe":"债券基本资料表","id":18,"selected":false},{"name":"zhaiquanjob_s.kjb","type":"job","grade":2,"describe":"债券交易表","id":19,"selected":false},{"name":"zhengquancodejob.kjb","type":"job","grade":2,"describe":"财汇_证券代码表","id":20,"selected":false},{"name":"zhishu.kjb","type":"job","grade":2,"describe":"财汇_指数表","id":21,"selected":false},{"name":"zhishuquanzhongjob.kjb","type":"job","grade":2,"describe":"财汇_指数样本权重表","id":22,"selected":false},{"name":"SecurityBasicInfoService","type":"service","grade":4,"describe":"个券基本信息更新","id":23,"selected":false},{"name":"gupiaojob.kjb","type":"job","grade":5,"describe":"股票交易表2","id":24,"selected":false},{"name":"jijinjob.kjb","type":"job","grade":5,"describe":"基金交易表2","id":25,"selected":false},{"name":"zhaiquanjob.kjb","type":"job","grade":5,"describe":"债券交易表2","id":26,"selected":false},{"name":"zhaijuanguzhijob.kjb","type":"job","grade":5,"describe":"债券估值表2","id":27,"selected":false},{"name":"TradeDetailService","type":"service","grade":6,"describe":"交易明细抽取","id":28,"selected":false},{"name":"StockDayFrequencyProfitService","type":"service","grade":7,"describe":"个券日频收益计算","id":29,"selected":false},{"name":"SecurityHoldBasicInfoService","type":"service","grade":7,"describe":"估值表个券持有信息更新","id":30,"selected":false},{"name":"StockMonthFrequencyProfitService","type":"service","grade":8,"describe":"个券月频收益计算","id":31,"selected":false},{"name":"StockYearFrequencyProfitService","type":"service","grade":8,"describe":"个券年频收益计算","id":32,"selected":false},{"name":"GroupDayFrequencyProfitService","type":"service","grade":8,"describe":"组合日频收益&平均委托资产余额计算","id":33,"selected":false},{"name":"GroupMonthFrequencyProfitService","type":"service","grade":9,"describe":"组合月频收益&平均委托资产余额计算","id":34,"selected":false},{"name":"GroupYearFrequencyProfitService","type":"service","grade":9,"describe":"组合年频收益&平均委托资产余额计算","id":35,"selected":false},{"name":"GroupCurrentMonthProfitService","type":"service","grade":9,"describe":"组合本月收益&平均委托资产余额计算","id":36,"selected":false},{"name":"GroupCurrentYearProfitService","type":"service","grade":9,"describe":"组合本年收益&平均委托资产余额计算","id":37,"selected":false}],"page":0,"limit":0}}
前台需要出一个页面来选择，并回传给后台，调用接口7.设置schemaid给后台。前台根据"selected":false/true来判断是否之前有选中。编辑和查看页面可以属于一个。页面下方需要有两个按钮，“确认” “取消” 用户点击确认保存，点击取消不保存。

# 3.立即执行接口

根据JobId来获取状态

/dpquartz/runETLJobNowById
method: GET
parameter：
jobId     调度任务ID        string  	
startTime 调度任务开始时间  string
endTime   调度任务结束时间  string
return status：
    code:0  msg:Etl Job 正在运行
	code:0  success
	code:998 msg:立即执行任务失败
	
example:

request:
http://127.0.0.1:8396/dpquartz/runETLJobNowById?jobId=19&startTime=20190112&endTime=20190113
http://127.0.0.1:8396/dpquartz/runETLJobNowById?jobId=19&startTime=20190112&endTime=20190212
http://11.53.62.56:8769/dpquartz/runETLJobNowById?jobId=19&startTime=20190112&endTime=20190212
http://11.11.15.20:8396/dpquartz/runETLJobNowById?jobId=19&startTime=20190906&endTime=20190906
http://11.11.15.20:8396/dpquartz/runETLJobNowById?jobId=23&startTime=20190101&endTime=20190924

curl 127.0.0.1:8396/dpquartz/runETLJobNowById -X GET -d "jobId=19&startTime=20190112&endTime=20190212"
curl 11.53.62.56:8769/dpquartz/runETLJobNowById -X GET -d "jobId=19&startTime=20190112&endTime=20190212"
curl 11.53.62.56:8396/dpquartz/runETLJobNowById -X GET -d "jobId=19&startTime=20190112&endTime=20190212"
response:
{"msg":"success","code":0}

# 4.设置定时任务的开启接口

dpquartz/changeTheJobStatus

method：get
http://127.0.0.1:8396/dpquartz/changeTheJobStatus?jobId=19&cmd=start
http://11.53.62.56:8769/dpquartz/changeTheJobStatus?jobId=19&cmd=start

# 5.设置定时任务的关闭接口

dpquartz/changeTheJobStatus

method：get
http://127.0.0.1:8396/dpquartz/changeTheJobStatus?jobId=19&cmd=stop
http://11.53.62.56:8769/dpquartz/changeTheJobStatus?jobId=19&cmd=stop

# 6.设置定时器接口

dpquartz/updateJobCron

method：get

http://127.0.0.1:8396/dpquartz/updateJobCron?jobName=ETLJOB&cron=0 0 03 * * ?
http://11.53.62.56:8769/dpquartz/updateJobCron?jobName=ETLJOB&cron=0 47 15 * * ?

# 7.下发设置schemaid接口


/dpquartz/updateJobSchemaIds

**method:post**

Headers:application/json 

param:

{"jobId":"29","schemaId":"1,2,3,4,5,6","runNow":"false"}
example：
http://127.0.0.1:8396/dpquartz/updateJobSchemaIds
{"jobId":"29","schemaId":"1,2,3,4,5,6","runNow":"false"}

# 8.查询执行日志记录接口

/dpquartz/logList
method: GET
参数 ： jobId

example:

request:
http://127.0.0.1:8396/dpquartz/logList?jobId=19&page=1&limit=10
http://11.53.62.56:8769/dpquartz/logList?jobId=19&page=1&limit=10
response:
{"msg":"success","code":0,"page":{"totalCount":0,"pageSize":0,"totalPage":0,"currPage":0,"list":[{"id":12202,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:40:50.000+0800","endTime":"2019-08-31T10:40:50.000+0800","executeResult":"1"},{"id":12201,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:40:09.000+0800","endTime":"2019-08-31T10:40:09.000+0800","executeResult":"1"},{"id":12200,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:39:54.000+0800","endTime":"2019-08-31T10:39:54.000+0800","executeResult":"1"},{"id":12199,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:39:23.000+0800","endTime":"2019-08-31T10:39:24.000+0800","executeResult":"1"},{"id":12198,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:38:05.000+0800","endTime":"2019-08-31T10:38:06.000+0800","executeResult":"1"},{"id":12197,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:29:49.000+0800","endTime":"2019-08-31T10:29:49.000+0800","executeResult":"1"},{"id":12196,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T10:25:15.000+0800","endTime":"2019-08-31T10:25:15.000+0800","executeResult":"1"},{"id":12195,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-31T09:24:23.000+0800","endTime":"2019-08-31T09:24:23.000+0800","executeResult":"1"},{"id":12194,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T21:01:21.000+0800","endTime":"2019-08-30T21:01:21.000+0800","executeResult":"1"},{"id":12193,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T20:28:34.000+0800","endTime":"2019-08-30T20:28:35.000+0800","executeResult":"1"},{"id":12192,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T20:28:00.000+0800","endTime":"2019-08-30T20:28:01.000+0800","executeResult":"1"},{"id":12191,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T20:24:57.000+0800","endTime":"2019-08-30T20:24:58.000+0800","executeResult":"1"},{"id":12190,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T19:48:52.000+0800"},{"id":12189,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T19:37:04.000+0800"},{"id":12188,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T19:31:08.000+0800","endTime":"2019-08-30T19:31:14.000+0800","executeResult":"1"},{"id":12187,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T19:24:53.000+0800","endTime":"2019-08-30T19:30:51.000+0800","executeResult":"1"},{"id":12186,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T19:01:32.000+0800"},{"id":12185,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T19:00:05.000+0800","endTime":"2019-08-30T19:00:49.000+0800","executeResult":"1"},{"id":12184,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T18:42:53.000+0800"},{"id":12183,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T17:20:06.000+0800"},{"id":12182,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T17:11:39.000+0800"},{"id":12181,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T17:02:35.000+0800","endTime":"2019-08-30T17:02:41.000+0800","executeResult":"1"},{"id":12180,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:58:28.000+0800"},{"id":12179,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:45:54.000+0800"},{"id":12178,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:34:06.000+0800"},{"id":12177,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T16:29:50.000+0800","endTime":"2019-08-30T16:30:28.000+0800","executeResult":"1"},{"id":12176,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:25:26.000+0800"},{"id":12175,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:22:55.000+0800"},{"id":12174,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T16:19:21.000+0800","endTime":"2019-08-30T16:19:47.000+0800","executeResult":"1"},{"id":12173,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T16:17:08.000+0800","endTime":"2019-08-30T16:17:28.000+0800","executeResult":"1"},{"id":12172,"jobId":19,"jobName":"ETLJOB","executeStatus":"NORMAL","startTime":"2019-08-30T16:15:37.000+0800"},{"id":12171,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T16:13:18.000+0800","endTime":"2019-08-30T16:14:05.000+0800","executeResult":"1"},{"id":12170,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T16:00:59.000+0800","endTime":"2019-08-30T16:01:49.000+0800","executeResult":"1"},{"id":12169,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T15:59:22.000+0800","endTime":"2019-08-30T16:00:19.000+0800","executeResult":"1"},{"id":12168,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T15:55:31.000+0800","endTime":"2019-08-30T15:56:11.000+0800","executeResult":"1"},{"id":12167,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T15:54:59.000+0800","endTime":"2019-08-30T15:55:00.000+0800","executeResult":"1"},{"id":12166,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T15:38:59.000+0800","endTime":"2019-08-30T15:39:01.000+0800","executeResult":"1"},{"id":12165,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T15:35:56.000+0800","endTime":"2019-08-30T15:35:57.000+0800","executeResult":"1"},{"id":12163,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T13:15:00.000+0800","endTime":"2019-08-30T13:15:00.000+0800","executeResult":"1"},{"id":12164,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T13:15:00.000+0800","endTime":"2019-08-30T13:15:01.000+0800","executeResult":"1"},{"id":12162,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-30T01:00:00.000+0800","endTime":"2019-08-30T01:00:00.000+0800","executeResult":"2","expInfo":"org.quartz.JobExecutionException: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams] [See nested exception: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]]\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:218)\n\tat org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)\nCaused by: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:213)\n\t... 1 more\nCaused by: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams\n\tat org.apache.ibatis.binding.MapperMethod$SqlCommand.(MapperMethod.java:227)\n\tat org.apache.ibatis.binding.MapperMethod.(MapperMethod.java:49)\n\tat org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:65)\n\tat org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:58)\n\tat com.sun.proxy.$Proxy153.queryEtlsDateParams(Unknown Source)\n\tat com.rf.cloud.annuity.quartz.task.ETLJob.execute(ETLJob.java:76)\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:202)\n\t... 1 more"},{"id":12161,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-29T10:50:00.000+0800","endTime":"2019-08-29T10:50:01.000+0800","executeResult":"2","expInfo":"org.quartz.JobExecutionException: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams] [See nested exception: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:218)\r\n\tat org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)\r\nCaused by: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:213)\r\n\t... 1 more\r\nCaused by: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams\r\n\tat org.apache.ibatis.binding.MapperMethod$SqlCommand.(MapperMethod.java:227)\r\n\tat org.apache.ibatis.binding.MapperMethod.(MapperMethod.java:49)\r\n\tat org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:65)\r\n\tat org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:58)\r\n\tat com.sun.proxy.$Proxy152.queryEtlsDateParams(Unknown Source)\r\n\tat com.rf.cloud.annuity.quartz.task.ETLJob.execute(ETLJob.java:76)\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:202)\r\n\t... 1 more"},{"id":12160,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-29T10:12:00.000+0800","endTime":"2019-08-29T10:12:01.000+0800","executeResult":"2","expInfo":"org.quartz.JobExecutionException: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams] [See nested exception: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:218)\r\n\tat org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)\r\nCaused by: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:213)\r\n\t... 1 more\r\nCaused by: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams\r\n\tat org.apache.ibatis.binding.MapperMethod$SqlCommand.(MapperMethod.java:227)\r\n\tat org.apache.ibatis.binding.MapperMethod.(MapperMethod.java:49)\r\n\tat org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:65)\r\n\tat org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:58)\r\n\tat com.sun.proxy.$Proxy152.queryEtlsDateParams(Unknown Source)\r\n\tat com.rf.cloud.annuity.quartz.task.ETLJob.execute(ETLJob.java:76)\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:202)\r\n\t... 1 more"},{"id":12107,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-29T01:00:00.000+0800","endTime":"2019-08-29T01:00:00.000+0800","executeResult":"2","expInfo":"org.quartz.JobExecutionException: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams] [See nested exception: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]]\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:218)\n\tat org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)\nCaused by: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:213)\n\t... 1 more\nCaused by: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams\n\tat org.apache.ibatis.binding.MapperMethod$SqlCommand.(MapperMethod.java:227)\n\tat org.apache.ibatis.binding.MapperMethod.(MapperMethod.java:49)\n\tat org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:65)\n\tat org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:58)\n\tat com.sun.proxy.$Proxy153.queryEtlsDateParams(Unknown Source)\n\tat com.rf.cloud.annuity.quartz.task.ETLJob.execute(ETLJob.java:76)\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:202)\n\t... 1 more"},{"id":12108,"jobId":19,"jobName":"ETLJOB","executeStatus":"COMPLETE","startTime":"2019-08-29T01:00:00.000+0800","endTime":"2019-08-29T01:00:00.000+0800","executeResult":"2","expInfo":"org.quartz.JobExecutionException: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams] [See nested exception: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:218)\r\n\tat org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)\r\nCaused by: org.quartz.SchedulerException: Job threw an unhandled exception. [See nested exception: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams]\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:213)\r\n\t... 1 more\r\nCaused by: org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.rf.cloud.annuity.dataintegration.dao.second.EtlMapper.queryEtlsDateParams\r\n\tat org.apache.ibatis.binding.MapperMethod$SqlCommand.(MapperMethod.java:227)\r\n\tat org.apache.ibatis.binding.MapperMethod.(MapperMethod.java:49)\r\n\tat org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:65)\r\n\tat org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:58)\r\n\tat com.sun.proxy.$Proxy152.queryEtlsDateParams(Unknown Source)\r\n\tat com.rf.cloud.annuity.quartz.task.ETLJob.execute(ETLJob.java:76)\r\n\tat org.quartz.core.JobRunShell.run(JobRunShell.java:202)\r\n\t... 1 more"}],"page":0,"limit":0}}
{"msg":"success","code":0,"page":{"totalCount":0,"pageSize":0,"totalPage":0,"currPage":0,"list":[],"page":0,"limit":0}}

# 9.查看job信息接口

/dpquartz/info/{id}

method：GET
example:

request:
http://127.0.0.1:8396/dpquartz/info/19
http://11.53.62.56:8769/dpquartz/info/19
response：
{"msg":"success","schedule":{"id":19,"cronExpression":"0 15 13 * * ?","methodName":"excute","description":"ETL JOB","updateBy":"","beanClass":"com.rf.cloud.annuity.quartz.task.ETLJob","jobStatus":"1","jobGroup":"group1","updateDate":"2019-08-26T13:59:59.000+0800","jobName":"ETLJOB","finalFireTime":"2019-08-31T10:40:50.000+0800"},"code":0}
{"msg":"success","code":0}

# 10.swagger-ui地址

method:GET
http://127.0.0.1:8396/swagger-ui.html

（目前提供认证服务是启动的功能）