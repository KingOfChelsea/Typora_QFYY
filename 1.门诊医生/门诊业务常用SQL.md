# 门诊数据SQL梳理

## 1.患者信息

患者主表

```sql
--患者信息
select t.idcardtype, t.idenno, t.birthday, t.is_valid, t.*, t.rowid
  from com_patientinfo t
 where t.name like '%徐振宇%';'
```

## 2.患者预约

预约主表

```sql
--预约
select t.*, t.rowid
  from fin_opr_booking t
 where t.card_no in 
       (select t.card_no from com_patientinfo t where t.name like '%徐振宇%');
```

## 3.挂号

```sql
select t.*, t.rowid
  from fin_opr_register t --where t.name like '%钟桂棠%' = '2141010'
 where t.card_no in 
       (select t.card_no from com_patientinfo t where t.name like '%徐振宇%');
```

## 4.
