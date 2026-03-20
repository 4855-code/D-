# 📄 试卷自动生成系统（Paper Generation System）

## 📌 项目简介
本项目是一个基于前后端分离架构的试卷自动生成系统，支持题库管理、自动组卷、试卷导出等功能，旨在提升教师出题效率与试卷管理能力。

系统支持根据题型、难度、知识点等多维条件，自动生成符合要求的试卷，并支持导出为 Word 文档。

---

## 🚀 技术栈

### 前端
- React / Umi.js
- HTML5 / CSS3 / JavaScript
- Axios（数据请求）

### 后端
- Spring Boot
- MyBatis
- Java

### 数据库
- MySQL

### 其他
- 拦截器（登录校验）
- CORS 跨域配置
- Word 文档导出

---

## 🧩 核心功能
<img width="729" height="483" alt="image" src="https://github.com/user-attachments/assets/c5ea1a73-e629-4d5b-a38f-4a03d693d37d" />


### 👤 用户模块
- 用户注册 / 登录
- 权限控制（管理员 / 教师）
- 密码修改
<img width="520" height="466" alt="image" src="https://github.com/user-attachments/assets/1a13e1d6-e237-4a3c-91cc-1db269fc4d9a" />

  
### 📚管理员界面
管理员可以进行对注册人员申请的审核，也可以删除现有人员。
<img width="911" height="639" alt="image" src="https://github.com/user-attachments/assets/a3ccacad-fba6-4019-9fe1-9cc4c1fe659e" />
<img width="864" height="663" alt="image" src="https://github.com/user-attachments/assets/12a34955-0842-4d9c-bb90-3be298ccbbbf" />


### 📚 题库管理
- 题目增删改查
- <img width="864" height="604" alt="image" src="https://github.com/user-attachments/assets/294c889c-c48c-4d8d-b21e-c1c6ba389987" />


- 支持 Excel 批量导入
<img width="865" height="533" alt="image" src="https://github.com/user-attachments/assets/e6a3ce77-ac27-42b0-bd09-49a0ad0a2c08" />


- 题目分类（题型 / 难度 / 知识点）
<img width="864" height="568" alt="image" src="https://github.com/user-attachments/assets/a98f5a73-7779-4f28-b56a-ee355d88554f" />


- 重复题目警告
<img width="864" height="387" alt="image" src="https://github.com/user-attachments/assets/0485f649-05ea-4b08-aecd-4e2883924042" />

  

### 🧠 自动组卷（核心功能🔥）
- 支持按题型、分值、难度生成试卷
- 提供两种组题算法：
  - 贪心算法
  - 遗传算法（优化题目组合）
<img width="864" height="612" alt="image" src="https://github.com/user-attachments/assets/96825d8a-cd81-4522-b348-8b6629509e9c" />


### 📄 试卷导出
- 自动生成 Word 格式试卷
- 包含题目与答案
<img width="863" height="623" alt="image" src="https://github.com/user-attachments/assets/da26e248-584f-4133-a454-9edfd4be12ac" />
<img width="864" height="255" alt="image" src="https://github.com/user-attachments/assets/01be4af6-82fa-490b-b44f-d84fade49321" />
<img width="864" height="693" alt="image" src="https://github.com/user-attachments/assets/e3a6de23-7e91-455d-b261-02a09992d0df" />



### 📊 历史记录
- 保存组卷历史
- 支持试卷回溯与复用
<img width="863" height="474" alt="image" src="https://github.com/user-attachments/assets/d8e7539b-ebed-4cb7-98b2-661277c7d476" />


---

## 🏗️ 系统架构
前端（React / Umi）
↓
HTTP 请求（Axios）
↓
后端（Spring Boot）
↓
业务逻辑层（Service）
↓
数据访问层（MyBatis）
↓
数据库（MySQL）


---

## ⚙️ 核心实现原理

### 1️⃣ 登录认证
使用 Spring MVC 拦截器（Interceptor）实现登录状态校验：
- 未登录用户请求被拦截
- 登录成功后放行接口访问

---

### 2️⃣ 自动组卷算法（核心🔥）

系统根据用户输入条件：
- 题型
- 难度
- 分值

执行流程：
1. 从题库筛选符合条件的题目
2. 使用贪心或遗传算法进行组合
3. 生成完整试卷结构
4. 返回前端展示并支持导出

---

### 3️⃣ 数据存储设计

主要数据表：
- `User`（用户表）
- `QuestionBank`（题库）
- `QuestionLabels`（标签）
- `TestPaperHistory`（试卷历史）

---

### 4️⃣ 前后端分离

- 前端负责页面展示与交互
- 后端提供 RESTful API
- 使用 CORS 解决跨域问题

---

---
### 🚀 快速体验（推荐）

1. 下载 exe 文件（见 Releases）
<img width="824" height="687" alt="image" src="https://github.com/user-attachments/assets/3e41889e-430d-40fb-b2db-28a4030edbd6" />

2. 双击运行程序
3. 打开浏览器访问：http://localhost:81
<img width="911" height="639" alt="image" src="https://github.com/user-attachments/assets/ca630959-181d-4677-b9d6-5c0b256a6423" />


## 📦 项目运行

### 后端启动
```bash
mvn spring-boot:run
前端启动
npm install
npm run dev
```


## 🚀 快速体验（推荐）

1. 下载 exe 文件（见 Releases）
<img width="824" height="687" alt="image" src="https://github.com/user-attachments/assets/3e41889e-430d-40fb-b2db-28a4030edbd6" />

2. 双击运行程序
3. 打开浏览器访问：http://localhost:8080
<img width="911" height="639" alt="image" src="https://github.com/user-attachments/assets/ca630959-181d-4677-b9d6-5c0b256a6423" />

