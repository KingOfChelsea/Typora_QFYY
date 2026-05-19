# LIS常用SQL

## 1.1

样本核收过程：
    1、样本基本信息插入此表中
    2、项目核收信息插入LAS_COM_SAMPLEITEM表中
    3、将要收费项目信息插入LAS_SAP_ITEMCHARGE(如果没登记,就向该表插入)

```sql
SELECT a.*, a.ROWID  FROM las_sap_samplereg a
```

## 1.2 一管血维护

- 在医学检验中，“一管血”通常指的是采集到**一根真空采血管**中的血液样本。

## 1.3 检验设备测试项目信息维护

```sql
select a.*,a.rowid from las_com_machineitem  a where a.itemname like '%☆%' 
```

## 1.4 
