# 产品介绍

为便捷孕妇、产妇预约月嫂而打造的网上预测平台，月嫂中心。用户可实现浏览月嫂列表、月嫂详细信息、包括基本信息、图片信息、往日评论（可图文并茂）、待签约册、签约册、服务订单、小程序支付、点赞、

# 产品结构

图片

# 产品功能说明与接口设计

## 用户

### 查询月嫂列表

通过前端传送不同的level数值，返回不同级别的月嫂列表

请求方式

| 选项     | 方式             |
| -------- | ---------------- |
| 请求放法 | get              |
| 路由     | /list/<lever_id> |

请求参数

| 参数名    | 类型   | 是否必传 | 说明         |
| --------- | ------ | -------- | ------------ |
| lever_id  | int    | true     | 月嫂等级     |
| page_num  | string | true     | 当前页面     |
| page_size | string | true     | 每页显示个数 |

响应参数

| 响应结果 | 响应类容 |
| -------- | -------- |
| code     | 状态码   |
| errmsg   | 错误内容 |
| list     | 列表内容 |
| count    | 总页数   |

list参数

| 字段        | 说明             |
| ----------- | ---------------- |
| id          | 月嫂id           |
| defualt_img | 默认月嫂形象图片 |
| name        | 月嫂姓名         |
| serve_type  | 服务状态         |
| price       | 价格             |

数据库

| 表名          | 备注                                       |
| ------------- | ------------------------------------------ |
| tb_sku_matron | 根据该表查询出对应数据进行分页返回相应数据 |

### 查询月嫂详情

通过前端传送不同的matron_id，返回相应月嫂详情信息

请求方式

| 选项     | 方式                |
| -------- | ------------------- |
| 请求放法 | get                 |
| 路由     | /detail/<matron_id> |

请求参数

| 参数名    | 类型 | 是否必传 | 说明   |
| --------- | ---- | -------- | ------ |
| matron_id | int  | true     | 月嫂id |

响应参数

| 响应结果 | 响应类容 |
| -------- | -------- |
| code     | 状态码   |
| errmsg   | 错误内容 |
| list     | 列表内容 |

list参数

| 字段             | 说明     |
| ---------------- | -------- |
| id               | 月嫂id   |
| head_list        | 头部信息 |
| certificate_list | 相关证书 |
| basic_list       | 基本信息 |
| work_list        | 工作经历 |
| family_list      | 家庭成员 |
| display_list     | 作品展示 |

头部信息 head_list

| 字段        | 说明             |
| :---------- | ---------------- |
| defualt_img | 默认月嫂形象图片 |
| serve_date  | 服务天数         |
| serve_type  | 服务状态         |
| serve_num   | 服务天数         |
| price       | 价格             |
| earnest     | 定金             |

相关证书certificate_list

| 字段 | 说明       |
| ---- | ---------- |
| id   | 证书类型id |
| src  | 图片地址   |

类型id说明

| id   | 类型     |
| ---- | -------- |
| 1    | 健康证   |
| 2    | 体检表   |
| 3    | 育婴证书 |

基本信息basic_list

| 字段       | 说明       |
| ---------- | ---------- |
| name       | 姓名       |
| age        | 年龄       |
| nation     | 民族       |
| home_type  | 住家情况   |
| education  | 学历       |
| marriage   | 婚姻状况   |
| id_card    | 身份证号码 |
| zodiac     | 属相       |
| startsign  | 星座       |
| height     | 身高       |
| weight     | 体重       |
| department | 所属门店   |
| domicile   | 户籍地址   |
| permanent  | 常住地址   |
| training   | 培训评价   |
| synthesis  | 综合评价   |

工作经历

家庭成员

作品展示

数据库

| 表名          | 备注                                       |
| ------------- | ------------------------------------------ |
| tb_sku_matron | 根据该表查询出对应数据进行分页返回相应数据 |

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
| serve_num     | int     | 服务数量     |
| server_date   | int     | 服务天数     |
| image_defualt | string  | 形象图片地址 |
| price         | int     | 价格         |
| earnest       | int     | 定金         |
| lever_id      | int     | 月嫂水平     |
| height        | int     | 身高cm       |
| weight        | int     | 体重kg       |
| educations    | string  | 学历         |
| marriage      | string  | 婚姻         |
| zodiac        | string  | 属相         |
| age           | int     | 年龄         |
| addres_id     | int     | 地址id       |
| natiion       | string  | 民族         |
| starsign      | string  | 星座         |

### 月嫂水平对应表

tb_matron_lever

| id   | lever    |
| ---- | -------- |
| 1    | 首席月嫂 |
| 2    | 金牌月嫂 |
| 3    | 资深月嫂 |
| 4    | 核心月嫂 |
| 5    | 骨干月嫂 |

### 月嫂服务状态对应表

tb_matron_type

| id   | type   |
| ---- | ------ |
| 1    | 休息   |
| 0    | 服务中 |

###  月嫂地址表

| 字段    | 类型    | 说明     |
| ------- | ------- | -------- |
| id      | int     | 地址id   |
| type    | boolean | 地址类型 |
| address | string  | 地址     |

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
| type      | int    | 评论类型 |
| comment   | string | 评论     |

## 管理员