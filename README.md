# Nodejs 全栈入门

学习地址：https://www.imooc.com/learn/1199

课程里面的功能都能走通，如果遇到问题可以一起讨论，提issue

## Sequelize 简介

Sequelize.js 是 Node.js ORM（Object-Relational-Mapper）框架，提供对 MySQL，MariaDB，SQLite 和 PostgreSQL 数据库的简单访问，通过映射数据库条目到对象，或者对象到数据库条目。

## 在 Node.js 中集成 Sequelize

官方文档：https://sequelize.org/master/manual/migrations.html

```
# 安装 Node.js mysql 驱动
npm install mysql2 --save

npm install sequelize --save

npm install sequelize-cli --save-dev
```

在mysql终端上创建数据库


```
# 初始化db在工程下的目录结构
npx sequelize-cli init

# 创建表模型
npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string

# 在数据库中实际创建该表
npx sequelize-cli db:migrate
```

#总体回顾 
1.技术栈
  node-->http,异常
  web框架，express、 hapi、koa、egg
  参数校验
  mysql的使用，了解
  ORM, sequelize 使用

2.技术的关键点
  api
  web->webse rver-> router->hander->orm->db

3.注意事项
  需要做详细的模型设计->模型之间的关系()
  api的使用文档-->api文档的使用工具
  测试


## 常见问题

### `ERROR: Please install mysql2 package manually`

报错原因是没有安装 Node.js 的 mysql 驱动，安装即可。

```
npm install mysql2 --save
```

### `UnhandledPromiseRejectionWarning: SequelizeDatabaseError: Incorrect string value`

字符编码问题，修改数据库为 utf8mb4 编码即可。
