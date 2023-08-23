# 产品介绍

为便捷孕妇、产妇预约月嫂而打造的网上预测平台，月嫂中心。用户可实现浏览月嫂列表、月嫂详细信息、包括基本信息、图片信息、往日评论（可图文并茂）、待签约册、签约册、服务订单、小程序支付、点赞、

# 产品结构

图片

# 产品功能说明

## 用户

查询月嫂列表

预定月嫂

加入预定册

浏览订单

# 数据库设计

## 用户

### 用户表(tb_users)

| 字段       | 类型       | 说明       |
| ---------- | ---------- | ---------- |
| id         | int        | 用户ID     |
| mobile     | vachar(10) | 用户手机号 |
| openID     | vachar(20) | 用户openid |
| crate_time | date       | 创建时间   |



## 月嫂

### 月嫂表（tb_sku_matron）

| 字段          | 类型    | 说明         |
| ------------- | ------- | ------------ |
| id            | int     | 月嫂id       |
| serve_type    | boolean | 服务状态     |
| image_defualt | string  | 形象图片地址 |
|               |         |              |
