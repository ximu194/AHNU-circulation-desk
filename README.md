# AHNU-circulation-desk
php程序设计课程大作业——基于PHP、MySQL的web端借还书系统
# 借还书系统设计思路

## 数据库设计

### 数据库概念结构设计

- 读者实体：**++用户编号++**、姓名、性别、年级、专业、被处罚次数、诚信度
- 图书实体：**++书籍编号++**、书名、作者、出版社、分类、登记日期
- 用户实体：**++用户编号++**、密码

### 数据库逻辑结构设计

- 读者（读者编号、姓名、性别、年级、专业、被处罚次数、诚信度）
- 图书（图书编号、书名、作者、出版社、分类、登记日期）
- 用户（用户编号、密码）
- 图书借还（用户编号、图书编号、借书时间、预期归还时间、实际归还时间）
- 处罚信息（用户编号、图书编号、超期天数、处罚金额）
- 管理员（管理员编号、管理员姓名、管理员电话）

### 数据库物理结构设计

#### 1.读者信息表

| 名字      | 数据类型     | 是否为空 | 键   | 说明    |
| ------- | -------- | ---- | --- | ----- |
| UID     | int      | NO   | PRI | 用户编号  |
| UName   | char(20) | NO   |     | 姓名    |
| USex    | char(4)  | NO   |     | 性别    |
| UGrade  | char(10) | NO   |     | 年级    |
| UPro    | char(50) | NO   |     | 专业    |
| PunTime | int      | NO   |     | 被处罚次数 |
| Inter   | int      | NO   |     | 诚信度   |

#### 2.图书信息表

| 名字      | 数据类型         | 是否为空 | 键   | 说明   |
| ------- | ------------ | ---- | --- | ---- |
| BID     | int          | NO   | PRI | 图书编号 |
| BName   | varchar(255) | NO   |     | 书名   |
| BAuthor | varchar(50)  | NO   |     | 作者   |
| BPub    | varchar(50)  | NO   |     | 出版社  |
| BCate   | varchar(20)  | NO   |     | 分类   |
| BDate   | datetime     | NO   |     | 入库时间 |

#### 3.用户信息表

| 名字     | 数据类型         | 是否为空 | 键   | 说明   |
| ------ | ------------ | ---- | --- | ---- |
| UID    | int          | NO   | PRI | 用户编号 |
| PASSWD | varchar(255) | NO   |     | 密码   |

#### 4.图书借还信息表
| 名字     | 数据类型         | 是否为空 | 键   | 说明   |
| ------ | ------------ | ---- | --- | ---- |
| UID     | int      | NO   | PRI | 用户编号  |
| BID     | int          | NO   | PRI | 图书编号 |
|BrDate|datetime|NO|     |借书时间|
|ExpDate|datetime|NO|     |预期归还时间|
