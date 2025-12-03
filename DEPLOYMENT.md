# GitHub Pages 部署步骤

## 前提条件
- 已安装 Quarto: https://quarto.org/docs/get-started/
- 已安装 R 和必要的包
- 有 GitHub 账号

## 步骤 1: 准备文件

1. 将所有文件放在一个文件夹中：
   - index.qmd
   - _quarto.yml
   - styles.css
   - .nojekyll
   - README.md
   - 所有的 miniproj_*.csv 文件

## 步骤 2: 安装 R 包

打开 R 或 RStudio，运行：

```r
install.packages(c("tidyverse", "plotly", "DT", "scales", "knitr"))
```

## 步骤 3: 渲染 Quarto 网站

在项目文件夹中打开终端/命令提示符，运行：

```bash
quarto render
```

这会创建一个 `docs` 文件夹，里面包含你的网站文件。

## 步骤 4: 创建 GitHub 仓库

1. 登录 GitHub
2. 点击右上角的 "+" -> "New repository"
3. 给仓库命名，例如：`faa-flight-analysis`
4. 选择 "Public"（必须是公开的才能用免费的 GitHub Pages）
5. 不要勾选 "Initialize this repository with a README"
6. 点击 "Create repository"

## 步骤 5: 上传文件到 GitHub

在你的项目文件夹中打开终端/命令提示符，运行以下命令：

```bash
# 初始化 git 仓库
git init

# 添加所有文件
git add .

# 创建第一次提交
git commit -m "Initial commit: FAA flight analysis"

# 连接到你的 GitHub 仓库（替换 YOUR-USERNAME 和 YOUR-REPO-NAME）
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

## 步骤 6: 启用 GitHub Pages

1. 在 GitHub 上打开你的仓库
2. 点击 "Settings"（设置）
3. 在左侧菜单中找到 "Pages"
4. 在 "Build and deployment" 下：
   - Source: 选择 "Deploy from a branch"
   - Branch: 选择 "main"
   - Folder: 选择 "/docs"
5. 点击 "Save"

## 步骤 7: 等待部署完成

- GitHub 会自动构建和部署你的网站
- 这可能需要几分钟
- 完成后，你会在 Pages 设置页面看到一个绿色的链接
- 链接格式：`https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

## 步骤 8: 更新 README

在 README.md 中，将 "Your GitHub Pages URL will go here" 替换为你的实际网址。

然后推送更新：

```bash
git add README.md
git commit -m "Update README with live site URL"
git push
```

## 故障排除

### 如果网站显示不正确：

1. 检查 `docs` 文件夹是否已创建且包含 `index.html`
2. 确保 `.nojekyll` 文件在根目录
3. 在 GitHub Pages 设置中确认选择了 `/docs` 文件夹
4. 清除浏览器缓存后重新访问

### 如果 R 图表不显示：

1. 确保所有 R 包都已安装
2. 检查 CSV 文件路径是否正确
3. 在本地先测试：`quarto preview index.qmd`

### 如果遇到 Git 错误：

如果你在推送时遇到身份验证问题，你可能需要：
1. 使用 Personal Access Token (PAT) 而不是密码
2. 在 GitHub 设置中创建 PAT：Settings -> Developer settings -> Personal access tokens
3. 使用 PAT 作为密码

## 更新网站

每次修改后：

```bash
# 渲染新版本
quarto render

# 提交并推送更改
git add .
git commit -m "Update analysis"
git push
```

GitHub Pages 会自动更新网站（可能需要几分钟）。

## 需要帮助？

- Quarto 文档：https://quarto.org/docs/websites/
- GitHub Pages 文档：https://docs.github.com/en/pages
- 如果有问题，可以在仓库中创建 Issue
