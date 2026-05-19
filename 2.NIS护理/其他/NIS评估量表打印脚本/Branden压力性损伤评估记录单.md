# Branden压力性损伤评估记录单

- Branden压力性损伤评估记录单 

```sql
/lb/fs:12/fn:黑体/d: NU-FO-08-211/mg:630,0,0,0;/lb/c/fs:15/fn:楷体/mg:10,-30/d:广东祈福医院;/lb/c/fs:15/mg:40,0,40,20/d:Branden压力性损伤评估记录单;/lb/d:科室:;/lb/il/mg:0,0,60,20/d:{DeptName} ;/lb/il/d:床号:;/lb/il/mg:0,0,60,20/d:{BedNo};/lb/il/d:姓名:;/lb/il/mg:0,0,60,20/d:{Name};/lb/il/d:性别:;/lb/il/mg:0,0,60,20/d:{Sex};/lb/il/d:年龄:;/lb/il/mg:0,0,60,20/d:{Age};/lb/d:住院号:;/lb/il/mg:0,0,30,0/d:{PatientNo};/lb/il/mg:0,0,0,20/d:入院诊断:;/lb/il/d:{Diagnose};/pb/w:450/h:125/fl:1,0/d:{image};
```

## 风险等级

```sql
0,2;低风险|2,5;高风险|5,10;中风险|10,101;极高风险
```

```sql
select dd.*, dd.rowid
  from nis_cbk_nas_print_item_data dd
 where dd.id in (SELECT dd.id
  FROM nis_cbk_nas_print p
  JOIN nis_cbk_nas_print_item it
    ON it.parent_id = p.id
  JOIN nis_cbk_nas_print_item_data dd
    ON dd.id = it.data_id
 WHERE p.nas_id = '549632d8-5eb9-4495-9084-fbbd266aafa4'
   AND it.data_id IS NOT NULL)
```



```sql
SELECT  
    Re.Id As Id,
    Re.Inpatient_Code As Inpatient_Code,
    Re.Dept_Code As Dept_Code,
    Re.Common_Tree_Id As Template_Id,
    '' as Sub_Template_Id,
    Re.Activity_Id As Activity_Id,
    Ac.Create_Date As Create_Time,
    max(case when It.Common_tree_Id='42bc81a8-7e10-469d-a6a4-3b3a9eaae0c4' then '√' else '' end) as Mitem01,
    max(case when It.Common_tree_Id='e6268c9a-c094-4741-8bc5-0ee3b6f1ee5e' then '√' else '' end) as Mitem02,
    max(case when It.Common_tree_Id='ca16aa63-39ca-4bbf-b302-789fc28432b7' then '√' else '' end) as Mitem03,
    max(case when It.Common_tree_Id='ce4ffb28-2b78-40cd-ab86-053f82f8190f' then '√' else '' end) as Mitem04,
    max(case when It.Common_tree_Id='e39d598d-68fc-43ea-a9d4-319f01c2ecba' then '√' else '' end) as Mitem05,
    max(case when It.Common_tree_Id='7d0e3e0e-80fe-4686-ba69-bd046f6f99e1' then '√' else '' end) as Mitem06,
    max(case when It.Common_tree_Id='08d87cac-ca14-4eaa-97ae-c1b514776416' then '√' else '' end) as Mitem07,
    max(case when It.Common_tree_Id='d5736387-57d5-4ee3-8cd0-b5b1bdc8fc9c' then '√' else '' end) as Mitem08,
    max(case when It.Common_tree_Id='14ad6bbe-a09d-4c79-abc3-b48f0d1ec2db' then '√' else '' end) as Mitem09,
    max(case when It.Common_tree_Id='c4e47fb0-169d-444a-a6f6-9376cb9d8b42' then '√' else '' end) as Mitem10,
    max(case when It.Common_tree_Id='9016cbac-a15e-4653-8f75-4b1e6c72b07c' then '√' else '' end) as Mitem11,
    max(case when It.Common_tree_Id='b4a39783-a16c-4b07-bc6b-48425d748ee3' then '√' else '' end) as Mitem12,
    max(case when It.Common_tree_Id='3fb9cfc6-6ba3-4034-bc37-4eec1ffb3f04' then '√' else '' end) as Mitem13,
    max(case when It.Common_tree_Id='8055bdc9-639a-49ab-bffd-7c35a6951a70' then '√' else '' end) as Mitem14,
    max(case when It.Common_tree_Id='d554782d-b8e5-4f0c-ae31-930746a5ffe7' then '√' else '' end) as Mitem15,
    max(case when It.Common_tree_Id='ecb1946c-d423-48c5-9d0e-ebfdb38690fa' then '√' else '' end) as Mitem16,
    max(case when It.Common_tree_Id='2b61a11e-4a4c-4554-84c2-d07113419e22' then '√' else '' end) as Mitem17,
    max(case when It.Common_tree_Id='1a260dcc-d47d-43f3-90b1-7f2379738cb5' then '√' else '' end) as Mitem18,
    max(case when It.Common_tree_Id='2e5f1d5a-2a16-44d1-b70c-d22e5c938168' then '√' else '' end) as Mitem19,
    max(case when It.Common_tree_Id='a68a5b86-08e7-4ac7-b1ca-fff3dc2dd2b7' then '√' else '' end) as Mitem20,
    max(case when It.Common_tree_Id='df2427d9-d433-486c-98c6-8d0d73aedb3f' then '√' else '' end) as Mitem21,
    max(case when It.Common_tree_Id='85cc88f3-2221-4d40-a16e-39fadc6e8b66' then '√' else '' end) as Mitem22,
    max(case when It.Common_tree_Id='c53fa9cb-878c-4cb1-ab2f-19e32e467913' then '√' else '' end) as Mitem23,
    NVL((SELECT LISTAGG(nsi.item_content,',')  
         FROM Nis_Nas_Record_Item nsi
         WHERE nsi.record_id = Re.id
         AND nsi.common_tree_id in('5bed6611-acf9-42de-905e-147ba4ae6c9c','d2bdc405-986f-4c44-bf31-f548c6f95701')
         GROUP BY nsi.record_id), '/') as Mitem24,
    max(case when It.Common_tree_Id='fb914c56-5dee-4ae6-9cae-e48996c6aeb7' then '√' else '/' end) as Mitem25,
    max(case when It.Common_tree_Id='4245b52f-8797-4bdb-8b56-72f993e3f328' then It.item_content else '/' end) as Mitem26,
NVL(
        (      select X.MITEM27 from (
                SELECT  
                Re.Id As Id,
                Re.Inpatient_Code As Inpatient_Code,
                Re.Dept_Code As Dept_Code,
                Re.Common_Tree_Id As Template_Id,
                '' as Sub_Template_Id,
                Re.Activity_Id As Activity_Id,
                Ac.Create_Date As Create_Time,
    
    NVL((
        SELECT LISTAGG(Ct.Abbre_Name, ', ') 
        WITHIN GROUP (ORDER BY Ct.id) 
        FROM NIS_CBK_NAS_COMMON_TREE Ct 
        JOIN NIS_NAS_Record_Item It2 ON It2.Common_Tree_Id = Ct.id WHERE 1=1
        and It2.Record_Id = Re.Id
        AND Ct.parent_id IN (
             SELECT t1.id 
             FROM NIS_CBK_NAS_COMMON_TREE t1 
             WHERE t1.parent_id = '549632d8-5eb9-4495-9084-fbbd266aafa4'
             AND t1.id <> '4ef3a2fd-e49e-4dfe-9c21-d1b50f5456bb'
         )
    	), '/') as Mitem27
    FROM NIS_NAS_Record_Item It, NIS_NAS_Record Re, NIS_NAS_Activity Ac
    WHERE 1=1 
    AND Ac.Id = Re.Activity_Id 
    AND Ac.Activity_State = '1' 
    AND Re.Id = It.Record_Id  
    AND Re.Valid_State = '1'
    AND Re.Common_Tree_Id  IN ('9afa1a1a-857d-4535-9795-f1b31b86ee70','dcbbb58f-ea0d-4884-971b-e155d8494961')
    GROUP BY Re.Id, Re.Inpatient_Code, Re.Dept_Code, Re.Common_Tree_Id, Re.Activity_Id, Ac.Create_Date) X
    where x.MITEM27 <> '/'
    and  X.ACTIVITY_ID = Re.Activity_Id
    ), '/' ) as Mitem27,
    '' as Mitem28,'' as Mitem29,'' as Mitem30,'' as Mitem31,'' as Mitem32,
    '' as Mitem33,'' as Mitem34,'' as Mitem35,'' as Mitem36,'' as Mitem37,
    '' as Mitem38,'' as Mitem39,'' as Mitem40,'' as Mitem41,'' as Mitem42,
    '' as Mitem43,'' as Mitem44,'' as Mitem45  
FROM NIS_NAS_Record_Item It, NIS_NAS_Record Re, NIS_NAS_Activity Ac
WHERE AC.INPATIENT_CODE = :Inpatient_Code 
AND Ac.Id = Re.Activity_Id 
AND Ac.Activity_State = '1' 
AND Re.Id = It.Record_Id  
AND Re.Valid_State = '1'
AND Re.Common_Tree_Id in( '9afa1a1a-857d-4535-9795-f1b31b86ee70')
GROUP BY Re.Id, Re.Inpatient_Code, Re.Dept_Code, Re.Common_Tree_Id, Re.Activity_Id, Ac.Create_Date


```



```sql
with y1 as (
SELECT  
    Re.Id As Id,
    Re.Inpatient_Code As Inpatient_Code,
    Re.Dept_Code As Dept_Code,
    Re.Common_Tree_Id As Template_Id,
    '' as Sub_Template_Id,
    Re.Activity_Id As Activity_Id,
    Ac.Create_Date As Create_Time,
    max(case when It.Common_tree_Id='42bc81a8-7e10-469d-a6a4-3b3a9eaae0c4' then '√' else '' end) as Mitem01,
    max(case when It.Common_tree_Id='e6268c9a-c094-4741-8bc5-0ee3b6f1ee5e' then '√' else '' end) as Mitem02,
    max(case when It.Common_tree_Id='ca16aa63-39ca-4bbf-b302-789fc28432b7' then '√' else '' end) as Mitem03,
    max(case when It.Common_tree_Id='ce4ffb28-2b78-40cd-ab86-053f82f8190f' then '√' else '' end) as Mitem04,
    max(case when It.Common_tree_Id='e39d598d-68fc-43ea-a9d4-319f01c2ecba' then '√' else '' end) as Mitem05,
    max(case when It.Common_tree_Id='7d0e3e0e-80fe-4686-ba69-bd046f6f99e1' then '√' else '' end) as Mitem06,
    max(case when It.Common_tree_Id='08d87cac-ca14-4eaa-97ae-c1b514776416' then '√' else '' end) as Mitem07,
    max(case when It.Common_tree_Id='d5736387-57d5-4ee3-8cd0-b5b1bdc8fc9c' then '√' else '' end) as Mitem08,
    max(case when It.Common_tree_Id='14ad6bbe-a09d-4c79-abc3-b48f0d1ec2db' then '√' else '' end) as Mitem09,
    max(case when It.Common_tree_Id='c4e47fb0-169d-444a-a6f6-9376cb9d8b42' then '√' else '' end) as Mitem10,
    max(case when It.Common_tree_Id='9016cbac-a15e-4653-8f75-4b1e6c72b07c' then '√' else '' end) as Mitem11,
    max(case when It.Common_tree_Id='b4a39783-a16c-4b07-bc6b-48425d748ee3' then '√' else '' end) as Mitem12,
    max(case when It.Common_tree_Id='3fb9cfc6-6ba3-4034-bc37-4eec1ffb3f04' then '√' else '' end) as Mitem13,
    max(case when It.Common_tree_Id='8055bdc9-639a-49ab-bffd-7c35a6951a70' then '√' else '' end) as Mitem14,
    max(case when It.Common_tree_Id='d554782d-b8e5-4f0c-ae31-930746a5ffe7' then '√' else '' end) as Mitem15,
    max(case when It.Common_tree_Id='ecb1946c-d423-48c5-9d0e-ebfdb38690fa' then '√' else '' end) as Mitem16,
    max(case when It.Common_tree_Id='2b61a11e-4a4c-4554-84c2-d07113419e22' then '√' else '' end) as Mitem17,
    max(case when It.Common_tree_Id='1a260dcc-d47d-43f3-90b1-7f2379738cb5' then '√' else '' end) as Mitem18,
    max(case when It.Common_tree_Id='2e5f1d5a-2a16-44d1-b70c-d22e5c938168' then '√' else '' end) as Mitem19,
    max(case when It.Common_tree_Id='a68a5b86-08e7-4ac7-b1ca-fff3dc2dd2b7' then '√' else '' end) as Mitem20,
    max(case when It.Common_tree_Id='df2427d9-d433-486c-98c6-8d0d73aedb3f' then '√' else '' end) as Mitem21,
    max(case when It.Common_tree_Id='85cc88f3-2221-4d40-a16e-39fadc6e8b66' then '√' else '' end) as Mitem22,
    max(case when It.Common_tree_Id='c53fa9cb-878c-4cb1-ab2f-19e32e467913' then '√' else '' end) as Mitem23,
    NVL((SELECT LISTAGG(nsi.item_content,',')  
         FROM Nis_Nas_Record_Item nsi
         WHERE nsi.record_id = Re.id
         AND nsi.common_tree_id in('5bed6611-acf9-42de-905e-147ba4ae6c9c','d2bdc405-986f-4c44-bf31-f548c6f95701')
         GROUP BY nsi.record_id), '/') as Mitem24,
    max(case when It.Common_tree_Id='fb914c56-5dee-4ae6-9cae-e48996c6aeb7' then '√' else '/' end) as Mitem25,
    max(case when It.Common_tree_Id='4245b52f-8797-4bdb-8b56-72f993e3f328' then It.item_content else '/' end) as Mitem26,
    NVL(
        (SELECT LISTAGG(Ct.Abbre_Name, ', ') WITHIN GROUP (ORDER BY Ct.id)
         FROM NIS_CBK_NAS_COMMON_TREE Ct
         JOIN NIS_NAS_Record_Item It2 ON It2.Common_Tree_Id = Ct.id
         WHERE It2.Record_Id = Re.Id
         AND Ct.parent_id IN (
             SELECT t1.id 
             FROM NIS_CBK_NAS_COMMON_TREE t1 
             WHERE t1.parent_id = '549632d8-5eb9-4495-9084-fbbd266aafa4'
             AND t1.id <> '4ef3a2fd-e49e-4dfe-9c21-d1b50f5456bb'
         )
        ), '/'
    ) as Mitem27,
    '' as Mitem28,'' as Mitem29,'' as Mitem30,'' as Mitem31,'' as Mitem32,
    '' as Mitem33,'' as Mitem34,'' as Mitem35,'' as Mitem36,'' as Mitem37,
    '' as Mitem38,'' as Mitem39,'' as Mitem40,'' as Mitem41,'' as Mitem42,
    '' as Mitem43,'' as Mitem44,'' as Mitem45,
    max(Re.Common_Tree_Id) as Mitem46
FROM NIS_NAS_Record_Item It, NIS_NAS_Record Re, NIS_NAS_Activity Ac
WHERE 1=1
--AC.INPATIENT_CODE = :Inpatient_Code 
AND Ac.Id = Re.Activity_Id 
AND Ac.Activity_State = '1' 
AND Re.Id = It.Record_Id  
AND Re.Valid_State = '1'
AND Re.Common_Tree_Id in( '9afa1a1a-857d-4535-9795-f1b31b86ee70')
GROUP BY Re.Id, Re.Inpatient_Code, Re.Dept_Code, Re.Common_Tree_Id, Re.Activity_Id, Ac.Create_Date),
y2 as (
SELECT  
    Re.Id As Id,
    Re.Inpatient_Code As Inpatient_Code,
    Re.Dept_Code As Dept_Code,
    Re.Common_Tree_Id As Template_Id,
    '' as Sub_Template_Id,
    Re.Activity_Id As Activity_Id,
    Ac.Create_Date As Create_Time,
    max(case when It.Common_tree_Id='42bc81a8-7e10-469d-a6a4-3b3a9eaae0c4' then '√' else '' end) as Mitem01,
    max(case when It.Common_tree_Id='e6268c9a-c094-4741-8bc5-0ee3b6f1ee5e' then '√' else '' end) as Mitem02,
    max(case when It.Common_tree_Id='ca16aa63-39ca-4bbf-b302-789fc28432b7' then '√' else '' end) as Mitem03,
    max(case when It.Common_tree_Id='ce4ffb28-2b78-40cd-ab86-053f82f8190f' then '√' else '' end) as Mitem04,
    max(case when It.Common_tree_Id='e39d598d-68fc-43ea-a9d4-319f01c2ecba' then '√' else '' end) as Mitem05,
    max(case when It.Common_tree_Id='7d0e3e0e-80fe-4686-ba69-bd046f6f99e1' then '√' else '' end) as Mitem06,
    max(case when It.Common_tree_Id='08d87cac-ca14-4eaa-97ae-c1b514776416' then '√' else '' end) as Mitem07,
    max(case when It.Common_tree_Id='d5736387-57d5-4ee3-8cd0-b5b1bdc8fc9c' then '√' else '' end) as Mitem08,
    max(case when It.Common_tree_Id='14ad6bbe-a09d-4c79-abc3-b48f0d1ec2db' then '√' else '' end) as Mitem09,
    max(case when It.Common_tree_Id='c4e47fb0-169d-444a-a6f6-9376cb9d8b42' then '√' else '' end) as Mitem10,
    max(case when It.Common_tree_Id='9016cbac-a15e-4653-8f75-4b1e6c72b07c' then '√' else '' end) as Mitem11,
    max(case when It.Common_tree_Id='b4a39783-a16c-4b07-bc6b-48425d748ee3' then '√' else '' end) as Mitem12,
    max(case when It.Common_tree_Id='3fb9cfc6-6ba3-4034-bc37-4eec1ffb3f04' then '√' else '' end) as Mitem13,
    max(case when It.Common_tree_Id='8055bdc9-639a-49ab-bffd-7c35a6951a70' then '√' else '' end) as Mitem14,
    max(case when It.Common_tree_Id='d554782d-b8e5-4f0c-ae31-930746a5ffe7' then '√' else '' end) as Mitem15,
    max(case when It.Common_tree_Id='ecb1946c-d423-48c5-9d0e-ebfdb38690fa' then '√' else '' end) as Mitem16,
    max(case when It.Common_tree_Id='2b61a11e-4a4c-4554-84c2-d07113419e22' then '√' else '' end) as Mitem17,
    max(case when It.Common_tree_Id='1a260dcc-d47d-43f3-90b1-7f2379738cb5' then '√' else '' end) as Mitem18,
    max(case when It.Common_tree_Id='2e5f1d5a-2a16-44d1-b70c-d22e5c938168' then '√' else '' end) as Mitem19,
    max(case when It.Common_tree_Id='a68a5b86-08e7-4ac7-b1ca-fff3dc2dd2b7' then '√' else '' end) as Mitem20,
    max(case when It.Common_tree_Id='df2427d9-d433-486c-98c6-8d0d73aedb3f' then '√' else '' end) as Mitem21,
    max(case when It.Common_tree_Id='85cc88f3-2221-4d40-a16e-39fadc6e8b66' then '√' else '' end) as Mitem22,
    max(case when It.Common_tree_Id='c53fa9cb-878c-4cb1-ab2f-19e32e467913' then '√' else '' end) as Mitem23,
    NVL((SELECT LISTAGG(nsi.item_content,',')  
         FROM Nis_Nas_Record_Item nsi
         WHERE nsi.record_id = Re.id
         AND nsi.common_tree_id in('5bed6611-acf9-42de-905e-147ba4ae6c9c','d2bdc405-986f-4c44-bf31-f548c6f95701')
         GROUP BY nsi.record_id), '/') as Mitem24,
    max(case when It.Common_tree_Id='fb914c56-5dee-4ae6-9cae-e48996c6aeb7' then '√' else '/' end) as Mitem25,
    max(case when It.Common_tree_Id='4245b52f-8797-4bdb-8b56-72f993e3f328' then It.item_content else '/' end) as Mitem26,
    NVL(
        (SELECT LISTAGG(Ct.Abbre_Name, ', ') WITHIN GROUP (ORDER BY Ct.id)
         FROM NIS_CBK_NAS_COMMON_TREE Ct
         JOIN NIS_NAS_Record_Item It2 ON It2.Common_Tree_Id = Ct.id
         WHERE It2.Record_Id = Re.Id
         AND Ct.parent_id IN (
             SELECT t1.id 
             FROM NIS_CBK_NAS_COMMON_TREE t1 
             WHERE t1.parent_id = '549632d8-5eb9-4495-9084-fbbd266aafa4'
             AND t1.id <> '4ef3a2fd-e49e-4dfe-9c21-d1b50f5456bb'
         )
        ), '/'
    ) as Mitem27,
    '' as Mitem28,'' as Mitem29,'' as Mitem30,'' as Mitem31,'' as Mitem32,
    '' as Mitem33,'' as Mitem34,'' as Mitem35,'' as Mitem36,'' as Mitem37,
    '' as Mitem38,'' as Mitem39,'' as Mitem40,'' as Mitem41,'' as Mitem42,
    '' as Mitem43,'' as Mitem44,'' as Mitem45,
    max(Re.Common_Tree_Id) as Mitem46    
FROM NIS_NAS_Record_Item It, NIS_NAS_Record Re, NIS_NAS_Activity Ac
WHERE 1=1
--AC.INPATIENT_CODE = :Inpatient_Code 
AND Ac.Id = Re.Activity_Id 
AND Ac.Activity_State = '1' 
AND Re.Id = It.Record_Id  
AND Re.Valid_State = '1'
AND Re.Common_Tree_Id in('dcbbb58f-ea0d-4884-971b-e155d8494961')
GROUP BY Re.Id, Re.Inpatient_Code, Re.Dept_Code, Re.Common_Tree_Id, Re.Activity_Id, Ac.Create_Date)

select 
y1.ID,
y1.INPATIENT_CODE,
y1.DEPT_CODE,
y1.TEMPLATE_ID,
y1.SUB_TEMPLATE_ID,
y1.ACTIVITY_ID,
y1.CREATE_TIME,
y1.MITEM01,
y1.MITEM02,
y1.MITEM03,
y1.MITEM04,
y1.MITEM05,
y1.MITEM06,
y1.MITEM07,
y1.MITEM08,
y1.MITEM09,
y1.MITEM10,
y1.MITEM11,
y1.MITEM12,
y1.MITEM13,
y1.MITEM14,
y1.MITEM15,
y1.MITEM16,
y1.MITEM17,
y1.MITEM18,
y1.MITEM19,
y1.MITEM20,
y1.MITEM21,
y1.MITEM22,
y1.MITEM23,
y1.MITEM24,
y1.MITEM25,
y1.MITEM26,
case when y1.Mitem46 = '9afa1a1a-857d-4535-9795-f1b31b86ee70'
  then z1.MITEM27
    else y1.MITEM27
    end as MITEM27,
y1.MITEM28,
y1.MITEM29,
y1.MITEM30,
y1.MITEM31,
y1.MITEM32,
y1.MITEM33,
y1.MITEM34,
y1.MITEM35,
y1.MITEM36,
y1.MITEM37,
y1.MITEM38,
y1.MITEM39,
y1.MITEM40,
y1.MITEM41,
y1.MITEM42,
y1.MITEM43,
y1.MITEM44,
y1.MITEM45
 from y1
left join (select * from y2 where  y2.MITEM27 <> '/') z1 on y1.ACTIVITY_ID = z1.ACTIVITY_ID
                                                

```

