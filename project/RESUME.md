# 个人简历快速生成系统

## 项目背景
无论是刚出来找工作还是工作后换工作，一个好的简历都是进入理想公司的敲门石。
我们这个项目就是要通过一个管理后台添加个人信息后可以自动快速创建出一个好看的pdf简历（只有pdf简历才是合格的简历）。

## 项目需求
### 管理后台
要求建立一个管理后台，管理员通过登录页面登入到管理系统，[登录原型地址](https://www.processon.com/view/link/59eb38cbe4b08b9e917f3f58)。
管理系统初期只需要一个简历管理菜单，进入菜单后可以查看所有的简历列表。
列表要求支持分页，支持按名称、创建时间区间查询，支持单个简历的编辑、删除、预览生成并下载pdf功能，支持选中多个简历的删除功能（删除前要弹框确认）。
列表中还要求有一个创建按钮，用来创建新简历，[简历管理列表原型地址](https://www.processon.com/view/link/59eb40d1e4b08b9e917f410e)。  
创建/编辑简历的表单中要求有如下几个字段（除了非必填字段，其它字段都要做必填校验和相应的字段校验，比如手机号验证）:
  - name 姓名
  - position 职位
  - birth 出生年月
  - about 关于我的描述
  - email 邮箱
  - phone 联系电话
  - city 所在城市
  - street 具体地址 非必填
  - website 个人站点地址 非必填
  - github Github用户名 非必填
  - education 教育经验 [数组] 最多添加3条纪录
    - timeperiod 教育时间
    - degree 学位
    - description 详细说明
  - experience 工作经验 [数组] 最多添加5条，提醒用户添加最近的5条
    - company 公司名称
    - position 工作职位
    - timeperiod 工作时间
    - description 详细描述
  - skills 技能掌握度 [数组]
    - name 技能名称
    - level 掌握程度 0-100
  - skillDescription 技能说明
[新增/编辑的原型地址](https://www.processon.com/view/link/59eb4635e4b012b70ca0f298)
### 前台展示
点击单个纪录的预览按钮将打开对应简历的预览页面，前台展示页面将直接使用开源项目生成，[项目地址](https://github.com/salomonelli/best-resume-ever)

## 实现点说明
管理后台页面可以用bootstrap快速制作页面，使用jQuery进行dom操作。后台使用SpringMVC+MyBatis+MySql实现。
