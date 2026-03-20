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

### 📚 题库管理
- 题目增删改查
- 支持 Excel 批量导入
- 题目分类（题型 / 难度 / 知识点）

### 🧠 自动组卷（核心功能🔥）
- 支持按题型、分值、难度生成试卷
- 提供两种组题算法：
  - 贪心算法
  - 遗传算法（优化题目组合）

### 📄 试卷导出
- 自动生成 Word 格式试卷
- 包含题目与答案

### 📊 历史记录
- 保存组卷历史
- 支持试卷回溯与复用

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

## 📦 项目运行

### 后端启动
```bash
mvn spring-boot:run
前端启动
npm install
npm run dev

## 🚀 快速体验（推荐）

1. 下载 exe 文件（见 Releases）
2. 双击运行程序
3. 打开浏览器访问：http://localhost:8080
