# 🚀 GitHub 部署指南 / GitHub Deployment Guide

## 📋 准备工作 / Prerequisites

### 1. 确保已安装 Git
打开 PowerShell 检查：
```powershell
git --version
```

如果没有安装，请从 https://git-scm.com/download/win 下载安装。

### 2. GitHub 账号
- 如果没有账号，请访问 https://github.com/ 注册
- 记住你的用户名（例如：caterina-valeo）

---

## 🔧 部署步骤 / Deployment Steps

### 步骤 1: 初始化 Git 仓库

在 PowerShell 中运行：

```powershell
cd "E:\VS code\9.30Caterina_website\Caterina-Valeo-master"

# 初始化 Git 仓库
git init

# 配置用户信息（替换为你的信息）
git config user.name "Caterina Valeo"
git config user.email "valeo@uvic.ca"

# 查看当前状态
git status
```

---

### 步骤 2: 添加所有文件到 Git

```powershell
# 添加所有文件
git add .

# 查看将要提交的文件
git status

# 第一次提交
git commit -m "Initial commit: Caterina Valeo academic website"
```

---

### 步骤 3: 创建 GitHub 仓库

#### 方法 A: 通过网页创建（推荐）

1. 访问 https://github.com/new
2. 填写仓库信息：
   - **Repository name**: `caterina-valeo.github.io` 或 `your-username.github.io`
     - ⚠️ **重要**: 如果仓库名是 `your-username.github.io`，网站会自动发布到 `https://your-username.github.io`
     - 如果使用其他名字（如 `academic-website`），网站会发布到 `https://your-username.github.io/academic-website`
   - **Description**: `Academic website for Prof. Caterina Valeo`
   - **Public** (选择公开)
   - ❌ **不要**勾选 "Add a README file"
   - ❌ **不要**添加 .gitignore
   - ❌ **不要**添加 license

3. 点击 **Create repository**

4. 复制显示的仓库 URL（例如：`https://github.com/your-username/caterina-valeo.github.io.git`）

---

### 步骤 4: 连接到 GitHub 仓库

在 PowerShell 中运行（替换为你的仓库 URL）：

```powershell
# 添加远程仓库（替换 URL）
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# 确认远程仓库已添加
git remote -v

# 重命名分支为 main（GitHub 默认使用 main）
git branch -M main
```

---

### 步骤 5: 推送到 GitHub

```powershell
# 第一次推送（可能需要登录 GitHub）
git push -u origin main
```

**登录提示：**
- 如果弹出登录窗口，输入你的 GitHub 用户名和密码
- 如果需要 token，访问 https://github.com/settings/tokens 创建一个

---

### 步骤 6: 配置 GitHub Pages

1. 访问你的仓库页面：`https://github.com/YOUR-USERNAME/YOUR-REPO-NAME`

2. 点击 **Settings** （设置）

3. 在左侧菜单找到 **Pages**

4. 在 **Source** 部分：
   - **Branch**: 选择 `main`
   - **Folder**: 选择 `/ (root)`
   - 点击 **Save**

5. 等待 2-3 分钟，页面顶部会显示：
   ```
   Your site is live at https://your-username.github.io/repo-name/
   ```

---

## ⚙️ 修改配置文件

在网站发布前，需要修改 `_config.yml` 中的 URL 设置。

### 如果仓库名是 `username.github.io`：

```yaml
url: https://your-username.github.io
baseurl: ""
```

### 如果仓库名是其他名字（如 `academic-website`）：

```yaml
url: https://your-username.github.io
baseurl: "/academic-website"
```

修改后需要提交并推送：

```powershell
git add _config.yml
git commit -m "Update site URL configuration"
git push
```

---

## 🔄 后续更新流程 / Update Workflow

每次修改网站后：

```powershell
cd "E:\VS code\9.30Caterina_website\Caterina-Valeo-master"

# 1. 查看改动
git status

# 2. 添加所有改动
git add .

# 3. 提交改动（写清楚改了什么）
git commit -m "Update publications and fix collaborator links"

# 4. 推送到 GitHub
git push

# 5. 等待 1-2 分钟，网站自动更新
```

---

## 📸 上传赞助商图片后

```powershell
# 添加新图片
git add images/sponsor1.png images/sponsor2.png images/sponsor3.png

# 提交
git commit -m "Add sponsor logos"

# 推送
git push
```

---

## ❗ 常见问题 / Troubleshooting

### Q1: 推送时要求输入用户名和密码？

**A**: 从 2021 年起，GitHub 不再支持密码认证，需要使用 Personal Access Token (PAT)：

1. 访问 https://github.com/settings/tokens
2. 点击 **Generate new token (classic)**
3. 勾选 `repo` 权限
4. 点击 **Generate token**
5. **复制 token**（只显示一次！）
6. 推送时用 token 替代密码

**或者使用 SSH**（更方便）：
```powershell
# 生成 SSH 密钥
ssh-keygen -t ed25519 -C "valeo@uvic.ca"

# 复制公钥内容
cat ~/.ssh/id_ed25519.pub

# 访问 https://github.com/settings/keys 添加 SSH key
# 然后修改远程 URL
git remote set-url origin git@github.com:YOUR-USERNAME/YOUR-REPO-NAME.git
```

---

### Q2: 网站显示 404 Not Found？

**A**: 可能的原因：
1. ⏳ **等待时间不够**：首次部署需要 3-5 分钟
2. ❌ **_config.yml 配置错误**：检查 `url` 和 `baseurl` 是否正确
3. ❌ **GitHub Pages 未启用**：确认在 Settings → Pages 中已选择 `main` 分支

---

### Q3: 网站样式错乱？

**A**: 通常是 `baseurl` 配置问题：

**如果仓库名是 `username.github.io`**:
```yaml
baseurl: ""  # 留空！
```

**如果仓库名是其他**:
```yaml
baseurl: "/repo-name"  # 必须加斜杠！
```

---

### Q4: 图片不显示？

**A**: 检查：
1. 图片文件确实在 `images/` 文件夹
2. 文件名完全匹配（区分大小写）
3. 已经 `git add` 并 `git push`

---

### Q5: 修改后网站没更新？

**A**: 
1. 确认已 `git push` 成功
2. 清空浏览器缓存（Ctrl+Shift+R）
3. 等待 1-2 分钟（GitHub Actions 构建时间）
4. 检查 Actions 页面：`https://github.com/YOUR-USERNAME/YOUR-REPO-NAME/actions`

---

## 🎯 推荐的仓库名

### 方案 1: 个人主站（推荐）
- **仓库名**: `your-username.github.io`
- **网址**: `https://your-username.github.io`
- **优点**: 
  - ✅ URL 最简洁
  - ✅ 不需要 baseurl 配置
  - ✅ 容易记忆

### 方案 2: 项目网站
- **仓库名**: `academic-website` 或 `caterina-valeo`
- **网址**: `https://your-username.github.io/academic-website`
- **优点**: 
  - ✅ 可以有多个项目网站
  - ✅ 仓库名更灵活

---

## 📝 完整命令清单 / Complete Command List

```powershell
# 1. 进入项目目录
cd "E:\VS code\9.30Caterina_website\Caterina-Valeo-master"

# 2. 初始化 Git
git init

# 3. 配置用户信息
git config user.name "Your Name"
git config user.email "your.email@example.com"

# 4. 添加所有文件
git add .

# 5. 第一次提交
git commit -m "Initial commit: Academic website"

# 6. 添加远程仓库（替换为你的 URL）
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# 7. 重命名分支
git branch -M main

# 8. 推送到 GitHub
git push -u origin main

# 9. 之后每次更新只需要三条命令
git add .
git commit -m "Describe your changes"
git push
```

---

## 🌐 访问你的网站

部署成功后，访问：
- 方案 1: `https://your-username.github.io`
- 方案 2: `https://your-username.github.io/repo-name`

**第一次访问可能需要等待 3-5 分钟！**

---

## ✅ 验证清单

部署后检查以下项目：

- [ ] 主页加载正常
- [ ] Publications 页面显示所有书籍和论文
- [ ] 书籍标题链接可点击（跳转到 Google Books/ResearchGate）
- [ ] Research Team 页面合作者链接正常
- [ ] Teaching 页面显示所有课程
- [ ] CV 页面格式正确
- [ ] 侧边栏头像显示
- [ ] 页脚显示 "Powered by Zhonghao"
- [ ] 赞助商图标显示（如已上传）
- [ ] 所有页面样式正常
- [ ] 手机端访问正常

---

## 📱 移动端测试

部署后用手机访问测试响应式设计：
- Safari (iOS)
- Chrome (Android)

或在电脑浏览器按 F12 → 切换设备模拟

---

## 🎉 恭喜！

你的学术网站现在已经在全球可访问了！

**分享你的网站：**
- 📧 Email 签名
- 💼 LinkedIn 个人资料
- 📄 简历/CV
- 🎓 学术论文作者信息
- 🐦 社交媒体

---

**需要帮助？** 如果遇到任何问题，随时告诉我！🚀
