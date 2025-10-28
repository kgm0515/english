# GitHub Pages 部署指南

本指南将帮助您在 GitHub 上部署这个英语学习应用。

## 📋 前置要求

- 拥有 GitHub 账号
- 已安装 Git
- 项目已推送到 GitHub 仓库

## 🚀 部署步骤

### 第一步：将代码推送到 GitHub

如果您的代码还没有推送到 GitHub，请执行以下命令：

```bash
# 初始化 git 仓库（如果还没有）
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Initial commit: 英语学习应用"

# 添加远程仓库（请将 YOUR_USERNAME 和 YOUR_REPO 替换为您的实际值）
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

### 第二步：启用 GitHub Pages

1. 打开您的 GitHub 仓库页面
2. 点击右上角的 **Settings**（设置）
3. 在左侧菜单中找到并点击 **Pages**
4. 在 **Source** 部分，选择 **GitHub Actions**（而不是 Branch）
5. 保存更改（无需手动操作，系统会自动保存）

### 第三步：触发部署

GitHub Actions 工作流会在以下情况自动触发：

1. 首次推送 `main` 分支的代码
2. 之后每次向 `main` 分支推送代码
3. 手动在 Actions 页面点击 "Run workflow"

如果代码已经推送，部署会自动开始。您可以在仓库的 **Actions** 标签页查看部署进度。

### 第四步：等待部署完成

1. 点击仓库顶部的 **Actions** 标签页
2. 查看工作流运行状态
3. 等待部署完成（通常需要 1-2 分钟）
4. 当看到绿色的勾号 ✅ 时，表示部署成功

### 第五步：访问网站

部署完成后，您的网站地址将是：

```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

例如，如果您的用户名是 `kgm0515`，仓库名是 `english`，那么地址就是：

```
https://kgm0515.github.io/english/
```

## 📝 后续更新

每次您更新代码后，只需：

```bash
git add .
git commit -m "更新内容说明"
git push origin main
```

GitHub Actions 会自动重新部署您的网站。

## 🔧 故障排除

### 问题 1: Pages 页面显示 "GitHub Actions 不是受支持的分支或文件夹"

**解决方案**：

1. 确保 `.github/workflows/deploy.yml` 文件存在且格式正确
2. 检查文件路径是否正确（`.github` 必须在项目根目录）
3. 重新推送到 GitHub

### 问题 2: 部署失败

**解决方案**：

1. 在 Actions 页面查看错误日志
2. 检查 `index.html` 文件是否存在
3. 确保没有语法错误

### 问题 3: 网站显示 404 或空白页

**解决方案**：

1. 确保 `index.html` 在项目根目录
2. 检查资源路径是否正确（使用相对路径）
3. 清除浏览器缓存后重新访问

### 问题 4: 资源文件无法加载

**解决方案**：

1. 确保所有 JavaScript 和 CSS 文件使用相对路径
2. 检查文件大小（GitHub Pages 有文件大小限制）
3. 查看浏览器控制台的具体错误信息

## 📞 获取帮助

如果遇到问题，您可以：

1. 查看 [GitHub Pages 文档](https://docs.github.com/cn/pages)
2. 查看 [GitHub Actions 文档](https://docs.github.com/cn/actions)
3. 在仓库中提交 Issue

## 🎉 完成

部署成功后，您就可以通过 GitHub Pages 的免费域名访问您的英语学习应用了！

---

**提示**: GitHub Pages 提供免费的 `.github.io` 子域名，非常适合部署静态网站。您的网站会自动使用 HTTPS，并且可以自定义域名。
