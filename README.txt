??? 天气分析系统 - 部署指南

项目结构：
deploy/
├── index.html      # 登录页面
├── dashboard.html  # 数据仪表盘
└── README.txt      # 部署说明

快速开始：
1. 直接打开index.html即可离线使用
2. 测试账号：admin / admin123

公网部署方案：

方案A：GitHub Pages
1. 创建GitHub仓库
2. 上传deploy目录内容
3. 启用GitHub Pages
4. 访问：https://username.github.io/repo/

方案B：Netlify/Vercel
1. 注册账号创建项目
2. 上传deploy目录或连接GitHub
3. 自动部署完成

方案C：Nginx服务器
server {
    listen 80;
    server_name your-domain.com;
    root /path/to/deploy;
    index index.html;
}

功能特性：
- 用户登录验证
- 数据统计展示
- 城市/天气/季节筛选
- CSV导入导出
- 数据清洗（去重、缺失值处理）
- 响应式设计

浏览器兼容：Chrome、Firefox、Safari、Edge
