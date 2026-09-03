# LIS常用SQL

## 1.1常规检验样本信息(核收)

样本核收过程：
    1、样本基本信息插入此表中
    2、项目核收信息插入LAS_COM_SAMPLEITEM表中
    3、将要收费项目信息插入LAS_SAP_ITEMCHARGE(如果没登记,就向该表插入)

```sql
SELECT a.*, a.ROWID  FROM las_sap_samplereg a

select 
a.state2 as "PDF生成状态（第5位外送接口、第10位是否生成PDF）",
a.lsptestform as 是否上传平台,
a.*,a.rowid 
from las_sap_samplereg a
where a.barcode = '2000692886'
```

## 1.2 一管血维护

- 在医学检验中，“一管血”通常指的是采集到**一根真空采血管**中的血液样本。

## 1.3 检验设备测试项目信息维护

```sql
select a.*,a.rowid from las_com_machineitem  a where a.itemname like '%☆%' 
```

## 1.4 检验样本核收

`汕头中医医院，样本类型没有自动带出来`

```sql
select  a.ordertime,a.sampletype,a.hisitemname,a.* from las_sap_barcodereg  a 
where 1=1
-- and  a. SAMPLETYPE is null 
and a.hisitemname is NOT  null 
and  a.hisitemname LIKE '%常规药敏%'
order by a.ordertime desc 
  -- 条码登记表 
```

## 1.5 危急值

```sql
select * from winlis.las_sap_lifealert a 
```

## 1.6仪器传入结果

```sql
-- ======================== 用户信息表分割线 =========================
select * from las_rt_result a 
where a.barcode = '2000569536';
-- ======================== 用户信息表分割线 =========================
SELECT a.*, a.ROWID  FROM Las_Gm_Result a 
where a.barcode = '2000569536'
```

## 1.7微生物相关信息

```sql
select a.confirmstate, a.*, a.rowid  from las_gm_samplereg a  -- 样本核收 las_gm_samplereg
where a.barcode = '2000595915' 

SELECT a.*, a.ROWID  FROM Las_Gm_Resultanti a -- 微生物检验结果表（抗生素表） 
where a.barcode = '2000595915'

SELECT a.*, a.ROWID  FROM Las_Gm_Resultgerm  a -- 微生物检验结果表（细菌表） 
where a.barcode = '2000595915'

SELECT a.*, a.ROWID  FROM las_gm_resultproc a  -- 微生物检验结果表（过程记录）
where a.barcode = '2000595915'
```

## 1.8 危机值维护对照关系

```sql
SELECT
    T.ITEMID                        AS item_code,        -- 项目ID
    T.DEPTID                        AS dept_code,        -- 适用科室
    MAX(T.SEX)                      AS gender,           -- 性别限制
    MAX(T.SAMPLETYPE)               AS sample_type,      -- 样本类型限制
    MAX(T.AGEDOWN)                  AS age_min,          -- 年龄下限
    MAX(T.AGEUP)                    AS age_max,          -- 年龄上限
    SUBSTR(T.rangeinfo, 1, INSTR(T.rangeinfo, '--') - 1)   AS ref_min,     -- 参考下限
    SUBSTR(T.rangeinfo, INSTR(T.rangeinfo, '--') + 2)      AS ref_max,     -- 参考上限
    SUBSTR(T.LIMITRANGE, 1, INSTR(T.LIMITRANGE, ',') - 1)  AS critical_min, -- 危急值下限
    SUBSTR(T.LIMITRANGE, INSTR(T.LIMITRANGE, ',') + 1)     AS critical_max, -- 危急值上限
    CAST('' AS VARCHAR2(64))        AS is_default,       -- 默认标记（预留字段）
    MAX(T.OPERTIME)                 AS update_time       -- 更新时间
FROM winlis.LAS_COM_ITEMRANGE T
GROUP BY 
    T.ITEMID,
    T.DEPTID,
    T.rangeinfo,
    T.MENSTRUALCYCLE,
    T.LIMITRANGE
```

## 1.9 TAT运转

## 1.10 报告描述表

```sql
SELECT t.barcode,
       t.machineid,
       t.testdate,
       t.sampleid,
       t.patientid,
       t.descvalue,
       t.desc1,
       t.desc2,
       t.desc3,
       t.descinternal,
       t.morphologydesc1,
       t.morphologydesc2,
       t.morphologydesc3,
       t.morphologydesc4
        FROM LAS_RT_DESCRESULT T  --检验单的描述性结果 
        WHERE T.SAMPLEID = '100050'
        AND T.MACHINEID = 'MY_CCC602'
        AND T.TESTDATE = '20260720'
```



<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/20260721145318868.png" alt="image-20260721145318652" style="zoom:50%;" /> 

## 1.11 金域报告回传

![image-20260806102414617](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/20260806102414650.png)

```sql
SELECT a.state2,a.lsptestform, a.*, a.ROWID  FROM las_sap_samplereg a
where a.barcode = '2000669123'
```

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/20260727163816715.png" alt="image-20260727163816602" style="zoom:250%;" />

## 1.12 数据字典相关

```sql
 SELECT a.*, a.ROWID  FROM  LAS_SYS_DICTIONARY a
 where  a.TYPEID   = 'WJZBBWFZJSL'

SELECT T.*,DECODE(T.DICCLASS, '1', '公用字典', '2', '特殊字典', '3', '系统字典') AS DC,t.rowid FROM LAS_SYS_DICTIONARY T
        WHERE TYPEID = 'DICTYPE' and t.dicname like '%危急值报表5分钟接受率参数%'
        ORDER BY SHOWORDER
