# 产品介绍

为便捷孕妇、产妇预约月嫂而打造的网上预测平台，月嫂中心。用户可实现浏览月嫂列表、月嫂详细信息、包括基本信息、图片信息、往日评论（可图文并茂）、待签约册、签约册、服务订单、小程序支付、点赞、

# 产品结构

图片

# 产品功能说明

## 用户

### 查询月嫂列表

### 预定月嫂

### 加入预定册

### 浏览订单

### 评论签约月嫂

### 查看我的评论

## 月嫂

## 管理员

# 数据库设计

## 用户

### 用户表

(tb_users)

| 字段       | 类型       | 说明       |
| ---------- | ---------- | ---------- |
| id         | int        | 用户ID     |
| mobile     | vachar(10) | 用户手机号 |
| openID     | vachar(20) | 用户openid |
| crate_time | date       | 创建时间   |

### 用户评论表

(tb_user_comment)

| 字段        | 类型   | 说明       |
| ----------- | ------ | ---------- |
| id          | int    | 评论id     |
| matron_id   | int    | 月嫂id     |
| user_id     | int    | 用户id     |
| type_img    | int    | 是否有图片 |
| comment     | string | 评论内容   |
| catate_time | date   | 评论时间   |

## 月嫂

### 月嫂表

（tb_sku_matron）

| 字段          | 类型    | 说明         |
| ------------- | ------- | ------------ |
| id            | int     | 月嫂id       |
| serve_type    | boolean | 服务状态     |
| image_defualt | string  | 形象图片地址 |
| price         | int     | 价格         |
| lever         | int     | 月嫂水平     |
| hight         | int     | 身高cm       |
| wight         | int     | 体重kg       |
| educations    | string  | 学历         |
| marriage      | string  | 婚姻         |
| zodiac        | string  | 属相         |
| age           | int     | 年龄         |
| addres_id     | int     | 地址id       |
| natiion       | string  | 民族         |
| starsign      | string  | 星座         |

### 月嫂表工作经历表

（tb_matron_record）

| 字段      | 类型   | 说明         |
| --------- | ------ | ------------ |
| id        | int    | 记录id       |
| matron_id | int    | 月嫂id       |
| date      | string | 工作时间     |
| unit      | string | 工作单位内容 |
| pay       | string | 薪资         |

### 月嫂家庭关系表

(tb_matron_relations)

| 字段      | 类型   | 说明     |
| --------- | ------ | -------- |
| id        | int    | 关系id   |
| matron_id | int    | 月嫂id   |
| name      | string | 成员姓名 |
| relation  | string | 成员关系 |
| job       | string | 成员工作 |
| unit      | string | 单位名称 |

### 月嫂图片作品表

（tb_show_img）

| 字段      | 类型   | 说明     |
| --------- | ------ | -------- |
| id        | int    | 图片id   |
| matron_id | int    | 月嫂id   |
| img       | string | 图片地址 |

### 月嫂相关证书图片表

(tb_certificate_img)

| 字段       | 类型    | 说明     |
| ---------- | ------- | -------- |
| id         | int     | 图片id   |
| type       | boolean | 证书类型 |
| matron _id | int     | 月嫂id   |
| img        | string  | 图片地址 |

### 月嫂评论表

（tb_matron_comment）

| 字段      | 类型   | 说明     |
| --------- | ------ | -------- |
| id        | int    | 评论id   |
| matron_id | int    | 月嫂id   |
| tyoe      | int    | 评论类型 |
| comment   | string | 评论     |

## 管理员