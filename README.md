# Life Records - 生活记录网站

一个基于 GitHub Pages 的个人生活记录网站，用于记录美食、旅行和各种清单。

## 部署到 GitHub Pages

### 第一步：创建 GitHub 仓库

1. 登录 GitHub，点击右上角 "+" → "New repository"
2. 仓库名建议：`life-records`（网站地址会是 `你的用户名.github.io/life-records`）
3. 设为 Public（GitHub Pages 免费版需要公开仓库）
4. 点击 "Create repository"

### 第二步：上传文件

将整个项目文件夹推送到仓库：

```bash
cd life-records-site
git init
git add .
git commit -m "init: life records site"
git branch -M main
git remote add origin https://github.com/你的用户名/life-records.git
git push -u origin main
```

### 第三步：开启 GitHub Pages

1. 进入仓库 → Settings → Pages
2. Source 选择 "Deploy from a branch"
3. Branch 选择 `main`，目录选 `/ (root)`
4. 点击 Save
5. 等待 1-2 分钟，网站就上线了

网站地址：`https://你的用户名.github.io/life-records`

## 如何添加内容

### 添加美食记录

编辑 `data/food.json`，按照以下格式添加：

```json
{
    "title": "店名或菜品名",
    "date": "2026-05-30",
    "content": "描述和感受",
    "location": "地点",
    "lat": 30.657,
    "lng": 104.066,
    "tags": ["标签1", "标签2"],
    "image": "图片链接（可选）"
}
```

### 添加旅行记录

编辑 `data/travel.json`，格式同上。

### 添加清单

编辑 `data/checklist.json`：

```json
{
    "title": "清单标题",
    "date": "2026-05-30",
    "tags": ["标签"],
    "items": [
        { "text": "待办事项", "done": false },
        { "text": "已完成的事", "done": true }
    ]
}
```

### 添加图片

推荐方式：
1. 在仓库中创建 `images/` 文件夹
2. 上传图片到该文件夹
3. 在 JSON 中引用：`"image": "images/你的图片.jpg"`

## 绑定自定义域名（可选）

1. 在仓库根目录创建 `CNAME` 文件，写入你的域名（如 `records.example.com`）
2. 在域名服务商处添加 CNAME 记录，指向 `你的用户名.github.io`
3. 在 GitHub Pages 设置中勾选 "Enforce HTTPS"

## 项目结构

```
life-records-site/
├── index.html          # 主页面（含所有样式和逻辑）
├── data/
│   ├── food.json       # 美食数据
│   ├── travel.json     # 旅行数据
│   └── checklist.json  # 清单数据
└── README.md           # 本文件
```

## 功能特性

- 时间线视图：按时间倒序展示所有记录
- 地图视图：在地图上标注所有带坐标的记录
- 分类筛选：按美食/旅行/清单分类查看
- 标签筛选：通过标签快速过滤内容
- 搜索功能：全文搜索标题、内容、地点
- 响应式设计：手机/平板/电脑都能用
