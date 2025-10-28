# English Learning - 英语单词学习

一个基于 Vue 3 和 Tailwind CSS 开发的英语单词学习应用，支持单词分类、发音、例句学习等功能。

## ✨ 功能特性

- 📚 **多词汇表支持**：初中词汇、高中词汇、大学词汇、考研词汇
- 🎯 **学习状态分类**：不会、模糊、掌握三种状态
- 🔊 **语音播放**：支持单词发音
- 📝 **详细释义**：包含音标、词性、例句
- 💾 **本地存储**：自动保存学习进度
- 📱 **响应式设计**：支持各种设备

## 🚀 快速开始

### 方式一：直接在 GitHub Pages 上访问

项目已配置自动部署，访问地址：

```
https://你的用户名.github.io/仓库名/
```

### 方式二：本地运行

1. 克隆项目

```bash
git clone https://github.com/你的用户名/仓库名.git
cd 仓库名
```

2. 直接用浏览器打开 `index.html` 即可

## 📖 使用说明

1. **选择词汇表**：在顶部选择要学习的词汇表（初中/高中/大学/考研）
2. **标记学习状态**：
   - 🔴 **不会**：需要重点学习的单词
   - 🟡 **模糊**：有一定印象但不熟练
   - 🟢 **掌握**：完全掌握的单词
3. **筛选查看**：点击筛选按钮查看不同状态的单词
4. **发音学习**：点击单词或例句可以播放发音
5. **分页浏览**：支持分页，每页显示 20 个单词

## 🛠️ 技术栈

- **前端框架**：Vue 3
- **UI 框架**：Tailwind CSS
- **语音合成**：Web Speech API
- **数据存储**：LocalStorage

## 📦 项目结构

```
endlish/
├── index.html                      # 主页面
├── api/
│   └── middle-school-vocabulary.js # 初中词汇数据
├── .github/
│   └── workflows/
│       └── deploy.yml             # GitHub Pages部署配置
└── README.md                      # 项目说明
```

## 🌐 部署到 GitHub Pages

项目已配置 GitHub Actions 自动部署，按以下步骤操作：

### 1. 准备工作

确保项目已推送到 GitHub 仓库。

### 2. 启用 GitHub Pages

1. 进入 GitHub 仓库页面
2. 点击 **Settings**（设置）
3. 在左侧菜单找到 **Pages**
4. 在 **Source** 中选择 **GitHub Actions**

### 3. 推送代码触发部署

```bash
git add .
git commit -m "添加GitHub Pages部署配置"
git push origin main
```

GitHub Actions 会自动部署项目，完成后访问地址：

```
https://你的用户名.github.io/仓库名/
```

### 4. 查看部署状态

在仓库的 **Actions** 标签页可以查看部署进度和状态。

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License

## 🙏 致谢

感谢 Vue.js、Tailwind CSS 等开源项目。
