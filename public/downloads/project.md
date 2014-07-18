# ics

## Login 

#### user login 

> 用户登录时的验证方法 

``` 
Method: POST, URI: /login 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
name | string | | 登录用户名 
password | string | | 登录密码 
#### get login user info 

> 获取登录用户的信息 

``` 
Method: GET, URI: /user_info 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### user logout 

> 用户登出 

``` 
Method: POST, URI: /logout 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### user signup 

> 用户注册 

``` 
Method: POST, URI: /signup 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
code | string | | 学号/工号 
password | string | | 密码 
re_password | string | | 重复密码 
email | string | | 邮箱 
name | string | | 姓名 
user_type | int | | 用户类型（1：管理员，2：教职工，3：学生） 
role_id | int | | 角色ID，默认和用户类型对应 
#### search password 

> 找回密码 

``` 
Method: POST, URI: /search_pass 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
login_name | string | | 登录用户名 
#### reset password 

> 重置密码 

``` 
Method: POST, URI: /reset_pass 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
token | string | | Token 
login_name | string | | 登录用户名 
password | string | | 密码 
re_password | string | | 重复密码 
#### valid token 

> 重置密码验证 

``` 
Method: POST, URI: /valid_token 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
login_name | string | | 登录用户名 
token | string | | 登录用户名 
## Users 

#### get users 

> 获取所有用户 

``` 
Method: GET, URI: /users 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### get users for type 

> 获取指定类型的用户 

``` 
Method: GET, URI: /users/:type 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 3| 用户类型（1：管理员，2：教职工，3：学生） 
#### search users for type 

> 获取指定类型的用户 

``` 
Method: GET, URI: /users/:type/search 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 3| 用户类型（1：管理员，2：教职工，3：学生） 
keyword | string | | 搜索关键字 
currentPage | int | 1| 当前页 
pageSize | int | 20| 每页大小 
sortFields | string | | 排序字段 
sortDirections | string | | 排序方式 
#### import users for type 

> excel导入指定类型的用户 

``` 
Method: POST, URI: /users/:type/import 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 3| 用户类型（1：管理员，2：教职工，3：学生） 
results | string | | 用户列表json 
#### import users preview for type 

> excel导入指定类型的用户进行预览 

``` 
Method: POST, URI: /users/:type/import 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 3| 用户类型（1：管理员，2：教职工，3：学生） 
excel | file | | 上传按钮 
#### exports users for type 

> 导出指定类型的用户到excel 

``` 
Method: GET, URI: /users/:type/export 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 3| 用户类型（1：管理员，2：教职工，3：学生） 
keyword | string | | 搜索关键字，作为过滤条件 
#### disable/enable user 

> 启用禁用用户 

``` 
Method: POST, URI: /users/:id/enable 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | 3| user id 
is_disable | int | 0| 是否禁用 
#### reset password for user 

> 重置用户密码 

``` 
Method: POST, URI: /users/:id/reset_password 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | 3| user id 
login_name | string | | 登录用户名 
password | string | | 登录密码 
#### delete user 

> 删除用户 

``` 
Method: POST, URI: /users/:id/delete 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | 3| user id 
#### update user 

> 修改用户信息 

``` 
Method: POST, URI: /users/:id/update 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | 3| user id 
name | string | | 姓名 
mobile | string | | 手机号 
gender | string | | 性别 
employed_date | int | | 雇佣/入学时间 
political_status | string | | 政治面貌 
id_card | string | | 身份证号 
birthday | int | | 生日 
dormitory | string | | 宿舍 
class | string | | 班级 
nation | string | | 民族 
title | string | | 职称 
part | string | | 单位 
## Org 

#### get org for type 

> 获取指定类型的用户 

``` 
Method: GET, URI: /org/:type 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
#### add or update org for type 

> 添加/更新组织机构项 

``` 
Method: POST, URI: /org/:type/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
name | string | | 名称 
parent | int | | parent id 
id | int | | org id 
#### delete item 

> 删除一项组织机构 

``` 
Method: POST, URI: /org/delete/:id 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | org id 
#### download org template 

> 下载组织机构模板 

``` 
Method: GET, URI: /org/:type/template 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
#### import org 

> 根据模板，导入组织机构 

``` 
Method: POST, URI: /org/:type/import 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
results | string | | org list json 
#### import preview org 

> 导入预览组织机构 

``` 
Method: POST, URI: /org/:type/import_preview 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
excel | file | | 上传按钮 
#### search org users 

> 搜索组织机构下得用户 

``` 
Method: GET, URI: /org/:type/users 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 用户类型（1：教职工，2：学生） 
keyword | string | | 关键字（学(工)号/姓名/手机） 
#### get org members 

> 获取组织机构下得用户 

``` 
Method: GET, URI: /org/:id/members 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | 组织机构id 
## Permission 

#### get premission 

> 获取权限 

``` 
Method: GET, URI: /permission/:type 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 角色（1：管理员，2：教职工,3:学生） 
#### update premission 

> 设置用户权限 

``` 
Method: POST, URI: /permission/:type 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
type | int | 1| 角色（1：管理员，2：教职工,3:学生） 
config | string | | 用户配置的权限item 
## System Config 

#### config sms 

> 配置sms 

``` 
Method: GET, URI: /sys_config/sms 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### config email 

> 配置email 

``` 
Method: GET, URI: /sys_config/email 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### config check update 

> 配置更新检查 

``` 
Method: GET, URI: /sys_config/check_update 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### config sms 

> 配置sms 

``` 
Method: POST, URI: /sys_config/sms 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
provider | string | | 服务提供商 
user | string | | 用户名 
password | string | | 密码 
status | int | 1| 状态(0:禁用，1：启用) 
#### config email 

> 配置email 

``` 
Method: POST, URI: /sys_config/email 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
nickname | string | | 昵称 
user | string | | 用户名 
password | string | | 密码 
status | int | 1| 状态(0:禁用，1：启用) 
#### config check update 

> 配置更新检查 

``` 
Method: POST, URI: /sys_config/check_update 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
status | int | 1| 状态(0:禁用，1：启用) 
## Notification 

#### notify list 

> 通知列表 

``` 
Method: GET, URI: /notify/:user/:status/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
status | int | 0| 状态(0:未读，1：已读) 
#### notify count 

> 通知列表 

``` 
Method: GET, URI: /notify/:user/:status/count 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
status | int | 0| 状态(0:未读，1：已读) 
## UserConfig 

#### user config 

> 更新用户信息 

``` 
Method: POST, URI: /user/:id/config 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | 3| user id 
name | string | | 姓名 
mobile | string | | 手机号 
gender | string | | 性别 
employed_date | int | | 雇佣/入学时间 
political_status | string | | 政治面貌 
id_card | string | | 身份证号 
qq | string | | qq 
contact | string | | 联系方式 
birthday | int | | 生日 
dormitory | string | | 宿舍 
class | string | | 班级 
nation | string | | 民族 
title | string | | 职称 
part | string | | 单位 
#### bind config 

> 绑定手机邮箱 

``` 
Method: POST, URI: /user/:id/config/bind 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | user id 
mobile | string | | 手机号 
email | string | | email 
#### modify password 

> 修改密码 

``` 
Method: POST, URI: /user/:id/config/password 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | user id 
password | string | | 原密码 
new_password | string | | 新密码 
re_new_password | string | | 重复新密码 
#### user config 

> 用户信息 

``` 
Method: GET, URI: /user/:id/config 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | user id 
#### bind config 

> 用户信息 

``` 
Method: GET, URI: /user/:id/config/bind 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | user id 
## Templates 

#### recently use templates 

> 最近使用的模板 

``` 
Method: GET, URI: /templates/:user/recently 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### I created templates 

> 我创建的模板 

``` 
Method: GET, URI: /templates/:user/my 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### public templates 

> 公开的模板 

``` 
Method: GET, URI: /templates/public 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### new template 

> 新建模板 

``` 
Method: POST, URI: /templates/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
name | string | | 模板名称 
desc | string | | 描述 
owner | string | | 拥有者 
property | string | | 配置的属性 
stat | string | | 统计的规则 
theme_id | string | | theme id 
theme_name | string | | theme name 
type | int | | 模板类型(1：通用模板，2：定制模板) 
is_public | int | | 模板是否公开(0：私有，1：公开) 
## Themes 

#### get themes 

> public themes list 

``` 
Method: GET, URI: /themes 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
  | 
#### get theme for id 

> 根据ID获取Theme 

``` 
Method: GET, URI: /themes/:id 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | theme id 
## Tasks 

#### I created tasks 

> 我创建的任务 

``` 
Method: GET, URI: /tasks/:user/my 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### I created tasks 

> 我创建的任务 

``` 
Method: GET, URI: /tasks/:user/my 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### I created tasks for id 

> 我创建的单个任务 

``` 
Method: GET, URI: /tasks/:user/my/:id 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
id | int | | task id 
#### show my created tasks list 

> 我创建的任务列表 

``` 
Method: GET, URI: /tasks/:user/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### search tasks 

> 搜索任务 

``` 
Method: GET, URI: /tasks/search/:status/:begin_time/:end_time/:name 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
status | int | | 任务状态（0：待启动，1：进行中，2：已完成，3：已禁用） 
begin_time | int | | 开始时间 
end_time | int | | 结束时间 
name | string | | 任务名称 
#### show my tasks list for status 

> 根据状态展示我的任务列表 

``` 
Method: GET, URI: /tasks/:user/list/:status 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
status | int | | 任务状态（0：待启动，1：进行中，2：已完成，3：已禁用） 
#### user process task 

> 用户做任务 

``` 
Method: POST, URI: /tasks/:user/process/:id 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
id | int | | task id 
answer | string | | answer 
#### create task 

> 创建任务 

``` 
Method: POST, URI: /tasks/:user/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
creator_name | string | | 创建者姓名 
creator_depart | string | | 创建者单位 
name | string | | 任务名称 
type | string | | 类型（1：匿名，2：有指派对象，3：有指派对象，但不记名） 
tpl_id | int | | 模板id 
start_time | int | | 有效开始时间 
end_time | int | | 有效结束时间 
is_repeat | int | | 是否是重复任务（0：不是，1：是） 
rules | string | | 任务规则 
receivers | string | | 接收对象 
#### get task details 

> 任务详细 

``` 
Method: GET, URI: /tasks/:id/detail 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
#### delete task 

> 删除任务 

``` 
Method: GET, URI: /tasks/:id/delete 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
#### update task status 

> 更新任务状态 

``` 
Method: POST, URI: /tasks/:id/status/:is_enabled 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
is_enabled | int | | 启用禁用任务（1：进行中，3：禁用） 
#### update valid datetime 

> 更新有效时间 

``` 
Method: POST, URI: /tasks/:id/info/update 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
start_time | int | | 开始时间 
end_time | int | | 结束时间 
#### task receivers add 

> 添加任务接受者 

``` 
Method: POST, URI: /tasks/:id/receiver/add 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
receivers | string | | 任务接收者 
#### task receivers delete 

> 删除任务接收者 

``` 
Method: POST, URI: /tasks/:id/receiver/delete 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | task id 
receivers | string | | 任务接收者 
## Comments 

#### get task comments 

> 获取任务评论 

``` 
Method: GET, URI: /comments/:task_id 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
task_id | int | | task id 
#### new task comment 

> 新建任务评论 

``` 
Method: POST, URI: /comments/:task_id/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
task_id | int | | task id 
author_id | int | | 评论人id 
author_name | string | | 评论人名称 
reply_id | int | | 回复的评论ID（0：直接给任务评论，1：回复某条评论） 
content | string | | 评论内容 
ip | string | | 客户端ip 
## Files 

#### user collect files 

> 用户收集的文件 

``` 
Method: GET, URI: /files/:user/collect/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
task_id | int | | task id 
#### user upload files 

> 用户上传的文件 

``` 
Method: GET, URI: /files/:user/upload/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
task_id | int | | task id 
#### user collect files 

> 用户创建的文件 

``` 
Method: GET, URI: /files/:user/folder/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
parent_id | int | | folder id 
#### user create folder 

> 用户新建目录 

``` 
Method: POST, URI: /files/:user/folder/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
parent_id | int | | folder id 
name | string | | 目录名 
#### user upload file 

> 用户上传文件 

``` 
Method: POST, URI: /files/:user/upload 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
parent_id | int | | folder id 
#### user upload file in task 

> 用户在任务中上传文件 

``` 
Method: POST, URI: /files/:user/task/:user_task_id/upload 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
user_task_id | int | | user task id 
## Tags 

#### new tag 

> 新建标签 

``` 
Method: POST, URI: /tags/:user/new 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
tag | string | | tag name 
#### get user tag list 

> 获取用户标签 

``` 
Method: GET, URI: /tags/:user/list 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
#### get tag relation user info 

> 获取标签关联的用户信息 

``` 
Method: GET, URI: /tags/:user/:id/user_info 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
user | int | | user id 
id | int | | tag id 
#### add tag relation user 

> 添加标签关联的用户 

``` 
Method: POST, URI: /tags/:id/relation/user_tasks 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
id | int | | tag id 
user_tasks | string | | 用户标签json 
