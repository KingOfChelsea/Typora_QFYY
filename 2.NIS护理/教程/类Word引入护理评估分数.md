# 类Word引入护理评估分数

## 1.维护类Word元素组件

- 创建新元素勾选`是否保存节点`+`是否护理元素`

![image-20250724162250472](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20250724162250472.png)

- 加载窗体控件`Tpl.Controls`以及弹出控件`Assessment`弹出控件

![image-20250724162339162](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20250724162339162.png)

- 记录下`元素编码`保存并退出系统

## 2.维护XML

打开程序下的Xml文件夹中的`病历与评估配置.xml` 

在XML文档中的`WordRecordItem`标签下维护

```xml
<WordRecordItem>
    <SubItem AssessmentId = "93aeebfc-5d3f-4afa-9519-6da96ae96e40" AssessmentIdContent = "新生儿疼痛评估" AssessmentTempletID = "18ebc630-724e-4d52-805a-965ad522a2c5" AssessmentTempletContent = "" RecordCode = "XinshengerPg" RecordContent = "新生儿疼痛评估"  AssessmentSign="" />
</WordRecordItem>
```

---

1. AssessmentId：需要同步到病历的评估项目Id，由评估系统提供(行业树-总分值id框)

2. AssessmentIdContent：AssessmentId项对应的说明性文字，维护成可看懂的项目名即可。(名字就是让维护人员知道自己维护的是啥)

3. AssessmentTempletID 根据选中病历元素对应评估模板ID (评估模版中ID）

   ```sql
   SELECT a.*, a.ROWID  FROM nis_cbk_nas_hos_template  a where a.name like '%新生儿疼痛%' ;
   ```

   ![image-20250728103645305](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20250728103645305.png)

4. AssessmentTempletContent 根据选中病历元素对应评估模板名 ==可以不填==                  

5. RecordCode：类型：string  word病历元素编码！可自定义  需要此配置与元素编码对应  元素需要维护成护理元素 ==元素编码==

6. RecordContent：RecordCode项对应的说明性文字，维护成可看懂的项目名即可。此配置不会显示在程序里，只是为了维护本配置文件时知道维护的是什么病历项。(名字就是让维护人员知道自己维护的是啥)

![image-20250724165344440](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20250724165344440.png)

![img_v3_02oh_0dac42c8-3665-4f62-b2c7-6b93d050199g](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/img_v3_02oh_0dac42c8-3665-4f62-b2c7-6b93d050199g.jpg)
