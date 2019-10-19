

## zhaijuanpingjijob.kjb

ods_market_bond_credit_chg

SELECT * FROM ods_market_bond_credit_chg where id in(SELECT max(id) from ods_market_bond_credit_chg);

SELECT * from ods_market_bond_credit_chg where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s'); 23860

### jigoupingjijob.kjb

SELECT * FROM ods_market_institution_credit where id in(SELECT max(id) from ods_market_institution_credit);

2019-09-25 17:55:26

SELECT * from ods_market_institution_credit where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s'); 14402

### gupiaojob.kjb

输出至股票交易表 ods_market_stock_trade 

id=ffffc830-a411-41da-bc0f-9a123a259431

SELECT * FROM ods_market_stock_trade where id='ffffc830-a411-41da-bc0f-9a123a259431'

SELECT * from ods_market_stock_trade  where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s');

514305

### jijinjob.kjb

输出至金融基金表 ods_market_fund_trade

???? modify_time null

SELECT * from ods_market_fund_trade where business_date='20190924'

SELECT * from ods_market_fund_trade where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s'); 41002

### zhaiquanjob.kjb

输出至债券表数据 ods_market_bond_trade

FFFFE07F3BCA40D5B38EC9C757C6495E

SELECT * FROM ods_market_bond_trade where id in(SELECT max(id) from ods_market_bond_trade);

SELECT * from ods_market_bond_trade where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s'); 182330

### zhaijuanguzhijob.kjb

输出至债券估值表 ods_market_bond_value

FFFFF85831A648C29B322B7B8844AFED

SELECT * FROM ods_market_bond_value where id in(SELECT max(id) from ods_market_bond_value);

SELECT * from ods_market_bond_value where create_time>STR_TO_DATE('2019-09-25 17:30:00','%Y-%m-%d %H:%i:%s'); 



测试命令

http://11.11.15.20:8396/dpquartz/runETLJobNowById?jobId=23&startTime=20190101&endTime=20190924

