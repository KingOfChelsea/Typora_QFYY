---
title: 医生无法签名护士文书（手册）
author: 徐振宇
date: 2026-05-07
---

# 医生无法签名护士文书

## 1.打开CA维护界面中的地址

- 地址如下

`http://10.161.211.166:8095/sign`

### 1.1 步骤如图1所示

1. 打开CA维护地址
2. 选择签名图片设置
3. 输入工号 如`CH9252`

![image-20251112195916919](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112195916919.png)

<center>图1</center>

1. 选择图片签名预览

![image-20251112200241777](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112200241777.png)

<center>图2</center>

1. 保存图片为png格式
2. 截图工具推荐`https://dl.snipaste.com/win-x64-cn ` `F1` 进行截图
3. 保存图片为==JPG==格式  注意：一定是==JPG==格式！！！

![image-20251112200437872](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112200437872.png)

<center>图3</center>

## 2.登录护士系统

登录核心护士工号 ==一定是核心护士工号==

账号：==11235==

密码：==888==

1. 登录NIS2.0_admin 初始科室即可

![image-20251112200917508](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112200917508.png)

<center>图4</center>

1. 选择RON签名图片维护

![image-20251112201034664](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112201034664.png)

<center>图5</center>

1. 输入护士工号并回车查询

![image-20251112201159504](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112201159504.png)

<center>图6</center>

1. 选择图片并打开

![image-20251112201302892](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112201302892.png)

<center>图7</center>

![image-20251112201336337](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251112201336337.png)

<center>图8</center>

验证是否成功 执行此`sql`

```sql
select * from nsr_org_employee_sign_data a where a.id = (select o.sign_data_id from nsr_org_employee_sign_info o where o.empl_code = 'CH6739')  -- 输入工号查询
```

