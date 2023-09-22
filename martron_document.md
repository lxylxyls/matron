#  产品介绍

为便捷孕妇、产妇预约月嫂而打造的网上预测平台，月嫂中心。用户可实现浏览月嫂列表、月嫂详细信息、包括基本信息、图片信息、往日评论（可图文并茂）、待签约册、签约册、服务订单、小程序支付、点赞、

# 产品结构

图片

# 产品功能

## 首页

图片

### 导航栏

自定义导航栏，实现样式的设置，以及搜索框的实现。搜索算法采用成熟的搜索引擎，Docker实现

### 通告栏

图片

可进行相关活动通知与公告说明 可滚动 文本可按时更换 ，管理员可替换

### 轮播图

可放置若干张宣传图片，自动轮播，管理员可替换

### 推荐功能

可显示不同功能图标，用户点击跳转到指定页面，可自定义推荐功能，如：资深月嫂、金牌月嫂等。

### 好评榜

随机推荐月嫂卡片、与评论卡片。

## 待订册

（类似商品中购物车的功能）显示待定月嫂卡片信息，选中（仅可选择一位月嫂）对应月嫂可进行支付结算。

## 我的

### 用户头像

可更改用户头像，昵称等 未登录时可进入登录页面

### 我的评论

点击我的评论 ，可查看自己所有评论，可以更改文字和图片，以及删除评论。

### 我的订单

点击我的订单，可查看预定的订单信息

### 我的投诉

点击我的投诉可以查看当前投诉的进度，以及处理结果

### 退出登录

点击退出登录，可退出用户当前账号

### 我的客户

仅限月嫂 点击即可查看 客户订单 以及用户地址、档期、联系方式等

### 月嫂日报

仅限月嫂 月嫂每日上传日报 未完成会显示相应图标

### 关于我们

点击查看公司相应信息

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
| depaetment  | 所属门店         |

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

工作经历work_list

| 字段 | 说明     |
| ---- | -------- |
| date | 工作时间 |
| work | 工作内容 |
| pay  | 薪资     |

家庭成员family_list

| 字段      | 说明     |
| --------- | -------- |
| name      | 姓名     |
| relations | 关系     |
| unit      | 单位名称 |
| job       | 职位名称 |

作品展示display_list

| 字段 | 说明     |
| ---- | -------- |
| id   | 图片id   |
| src  | 图片地址 |

数据库

| 表名                | 备注                                  |
| ------------------- | ------------------------------------- |
| tb_sku_matron       | 根据该表查询出对应月嫂的基本数据      |
| tb_matron_address   | 根据matron_id查询对应地址             |
| tb_matron_record    | 根据matron_id查询对应工作经历         |
| tb_matron_relations | 根据matron_id查询对应家庭关系         |
| tb_show_img         | 根据matron_id查询对应作品展示图片地址 |
| tb_certificate_img  | 根据matron_id查询对应证书图片地址     |

### 查询月嫂评论

通过前端传送不同的matron_id，返回对应月嫂评论

请求方式

| 选项     | 方式                        |
| -------- | --------------------------- |
| 请求放法 | get                         |
| 路由     | /comment/matron/<matron_id> |

请求参数

| 参数名    | 类型   | 是否必传 | 说明         |
| --------- | ------ | -------- | ------------ |
| matron_id | int    | true     | 月嫂id       |
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

| 字段        | 说明         |
| ----------- | ------------ |
| id          | 评论id       |
| img         | 图片地址列表 |
| user_img    | 用户头像     |
| user_name   | 用户名       |
| comment     | 评论内容     |
| create_date | 评论时间     |

数据库

| 表名            | 备注                                                         |
| --------------- | ------------------------------------------------------------ |
| tb_user_comment | 根据该表查询找到对应评论，得到user_id,type_img,评论内容和时间 |
| tb_users        | 根据user_id查询用户名和头像                                  |
| tb_comment_img  | 根据comment_id查询图片地址                                   |

### 预定月嫂



### 加入月嫂预定册

### 浏览订单

### 评论签约月嫂

### 查看我的评论

通过前端传送不同的user_id，返回对应用户评论

请求方式

| 选项     | 方式                      |
| -------- | ------------------------- |
| 请求放法 | get                       |
| 路由     | /comment/user/<matron_id> |

请求参数

| 参数名    | 类型   | 是否必传 | 说明         |
| --------- | ------ | -------- | ------------ |
| matron_id | int    | true     | 月嫂等级     |
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

| 字段        | 说明         |
| ----------- | ------------ |
| id          | 评论id       |
| img         | 图片地址列表 |
| user_img    | 用户头像     |
| user_name   | 用户名       |
| comment     | 评论内容     |
| create_date | 评论时间     |

数据库

| 表名            | 备注                                                         |
| --------------- | ------------------------------------------------------------ |
| tb_user_comment | 根据该表查询找到对应评论，得到user_id,type_img,评论内容和时间 |
| tb_users        | 根据user_id查询用户名和头像                                  |
| tb_comment_img  | 根据comment_id查询图片地址                                   |

### 

## 月嫂

## 管理员

# 数据库设计

## 用户

### 用户表

(tb_users)

| 字段        | 类型       | 说明         |
| ----------- | ---------- | ------------ |
| id          | int        | 用户ID       |
| mobile      | vachar(10) | 用户手机号   |
| openID      | vachar(20) | 用户openid   |
| defualt_img | string     | 用户头像地址 |
| crate_time  | date       | 创建时间     |

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

type_img

| id   | type   |
| ---- | ------ |
| 1    | 有图片 |
| 0    | 无图片 |

### 用户评论图片表

tb_comment_img

| 字段      | 说明     |
| --------- | -------- |
| id        | 图片id   |
| coment_id | 评论id   |
| src       | 图片地址 |

### 用户订单表

tb_user_order

| 字段      | 说明         |
| --------- | ------------ |
| id        | 订单id       |
| user_id   | 用户id       |
| total_num | 预定月嫂总数 |
| create_id | 创建时间     |
| pay       | 支付金额     |
|           |              |
|           |              |
|           |              |

### 用户订单月嫂表

tb_order_matron

| 字段      | 说明   |
| --------- | ------ |
| id        | 表id   |
| order_id  | 订单id |
| matron_id | 月嫂id |
|           |        |



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

tb_matron_address

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
| user_id   | int    | 用户id   |
| type      | int    | 评论类型 |
| comment   | string | 评论     |

### 月嫂档期表

（tb_matron_schedule）

| 字段       | 类型 | 说明     |
| ---------- | ---- | -------- |
| id         | int  | 档期id   |
| martron_id | int  | 月嫂id   |
| user_id    | int  | 用户id   |
| start_date | date | 起始日期 |
| end_date   | date | 结束日期 |

## 管理员