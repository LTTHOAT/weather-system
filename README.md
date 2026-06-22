# 🌤️ 天气分析系统 - 部署指南

## 项目简介

天气分析系统是一个纯前端的数据可视化应用，包含以下功能：
- 用户登录界面
- 天气数据仪表盘
- 数据筛选与搜索
- CSV导入/导出
- 数据清洗功能

## 📁 项目结构

```
deploy/
├── index.html          # 登录页面
├── dashboard.html      # 数据仪表盘
└── README.md           # 部署说明
```

## 🚀 快速开始

### 方法1：直接打开（离线使用）

1. 在浏览器中直接打开 `index.html`
2. 使用测试账号登录：
   - 用户名：admin
   - 密码：admin123

### 方法2：本地开发服务器

```bash
# 使用Python启动本地服务器
python -m http.server 8000

# 访问地址
http://localhost:8000/index.html
```

## ☁️ 公网部署

### 部署到静态网站托管

#### 方案A：GitHub Pages

1. 创建GitHub仓库
2. 将deploy目录内容推送到仓库
3. 在仓库设置中启用GitHub Pages
4. 访问地址：`https://username.github.io/repo-name/`

#### 方案B：Netlify/Vercel

1. 注册账号并创建新项目
2. 上传deploy目录或连接GitHub仓库
3. 自动部署完成

#### 方案C：传统Web服务器（Nginx/Apache）

**Nginx配置示例：**

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /path/to/deploy;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /dashboard.html {
        add_header Cache-Control "no-cache, no-store, must-revalidate";
    }
}
```

**Apache配置示例：**

```apache
<VirtualHost *:80>
    ServerName your-domain.com
    DocumentRoot /path/to/deploy
    DirectoryIndex index.html

    <Directory /path/to/deploy>
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

## 🔧 配置说明

### 登录凭证
- **用户名**: admin
- **密码**: admin123

### 数据存储
- 数据存储在浏览器内存中
- 刷新页面后恢复初始数据
- 导入的CSV数据在会话期间有效

## ✨ 功能特性

| 功能 | 说明 |
|------|------|
| 🔐 用户登录 | 简单的账号密码验证 |
| 📊 数据统计 | 平均气温、湿度、降雨量统计 |
| 🔍 搜索筛选 | 按城市、天气类型、季节筛选 |
| 📥 CSV导入 | 支持上传CSV文件导入数据 |
| 📤 CSV导出 | 导出当前数据为CSV文件 |
| 🧹 数据清洗 | 检测并处理重复、缺失、异常数据 |
| 📱 响应式设计 | 支持移动端访问 |

## 🖥️ 浏览器兼容性

- ✅ Chrome (推荐)
- ✅ Firefox
- ✅ Safari
- ✅ Edge

## 📝 更新日志

### v1.0.0
- 初始版本
- 登录功能
- 天气数据展示
- CSV导入导出
- 数据清洗功能

---

**开发团队**: Trae AI Assistant  
**版本**: 1.0.0  
**License**: MIT