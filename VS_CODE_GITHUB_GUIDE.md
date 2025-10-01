# 🚀 使用 VS Code 部署到 GitHub 的完整指南

## 方法一：VS Code Git 集成（推荐）⭐

### 步骤 1️⃣: 在 VS Code 中配置 Git

1. **打开 VS Code**
2. **打开你的项目文件夹**：
   - 点击 `文件` → `打开文件夹`
   - 选择：`E:\VS code\9.30Caterina_website\Caterina-Valeo-master`

3. **配置 Git 用户信息**（只需一次）：
   - 按 `Ctrl + `` 打开终端
   - 运行以下命令：
   ```powershell
   git config user.name "Caterina Valeo"
   git config user.email "valeo@uvic.ca"
   ```

---

### 步骤 2️⃣: 在 GitHub 创建仓库

1. **访问**: https://github.com/new

2. **填写信息**：
   - **Repository name**: 
     - 推荐：`your-username.github.io`（如 `caterina-valeo.github.io`）
     - 或：`academic-website`
   - **Description**: `Academic website for Prof. Caterina Valeo`
   - 选择 **Public**
   - ❌ **不要**勾选任何选项（不要添加 README、.gitignore、license）

3. **点击**: `Create repository`

4. **复制仓库 URL**：
   - 复制显示的 HTTPS URL（如：`https://github.com/your-username/your-repo-name.git`）

---

### 步骤 3️⃣: 使用 VS Code 提交和推送

#### A. 初始化和第一次提交

1. **点击左侧的源代码管理图标**（或按 `Ctrl+Shift+G`）

2. **查看变更**：
   - 你会看到所有未跟踪的文件
   - 应该有大约 40-50 个文件

3. **暂存所有文件**：
   - 点击 "Changes" 旁边的 `+` 号
   - 或者点击 `...` → `暂存所有更改`

4. **写提交信息**：
   - 在顶部的消息框输入：`Initial commit: Academic website`
   - 按 `Ctrl+Enter` 或点击 `✓ 提交`

#### B. 连接到 GitHub 仓库

在 VS Code 终端（`Ctrl + ``）运行：

```powershell
# 添加远程仓库（替换为你的 URL）
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# 重命名分支为 main
git branch -M main
```

#### C. 推送到 GitHub

**方法 1: 使用 VS Code 界面**
1. 点击源代码管理面板顶部的 `...`
2. 选择 `推送到...` → `origin`
3. 如果提示登录，输入 GitHub 用户名和密码（或 Token）

**方法 2: 使用终端**
```powershell
git push -u origin main
```

---

### 步骤 4️⃣: GitHub 登录验证

#### 如果弹出登录窗口：

**Windows Credential Manager（推荐）**:
1. 第一次推送时会弹出 "GitHub Login" 窗口
2. 点击 "Sign in with your browser"
3. 在浏览器中完成 GitHub 登录
4. VS Code 会自动保存凭据

#### 如果需要 Personal Access Token:

1. **创建 Token**：
   - 访问：https://github.com/settings/tokens
   - 点击 `Generate new token (classic)`
   - **Note**: `VS Code Git Access`
   - **Expiration**: `No expiration` 或选择时间
   - **勾选权限**: `repo`（全选）
   - 点击 `Generate token`
   - **⚠️ 立即复制 token（只显示一次！）**

2. **使用 Token**：
   - 当 VS Code 要求输入密码时
   - **用户名**: 你的 GitHub 用户名
   - **密码**: 粘贴刚才复制的 token

---

## 方法二：GitHub Desktop（最简单）🎯

如果 VS Code 推送遇到问题，可以使用 GitHub Desktop：

### 安装 GitHub Desktop

1. 下载：https://desktop.github.com/
2. 安装并登录你的 GitHub 账号

### 使用 GitHub Desktop 推送

1. **添加本地仓库**：
   - 点击 `File` → `Add Local Repository`
   - 选择：`E:\VS code\9.30Caterina_website\Caterina-Valeo-master`

2. **发布到 GitHub**：
   - 点击顶部的 `Publish repository`
   - **Name**: 填写仓库名（如 `caterina-valeo.github.io`）
   - **Description**: `Academic website for Prof. Caterina Valeo`
   - ❌ 取消勾选 "Keep this code private"（保持公开）
   - 点击 `Publish Repository`

3. **完成！**
   - GitHub Desktop 会自动处理所有文件
   - 没有 100 个文件的限制
   - 推送完成后会显示成功消息

---

## 方法三：命令行分批推送（备选）

如果确实遇到限制，可以分批推送：

```powershell
# 1. 提交配置文件
git add _config.yml Gemfile* .gitignore
git commit -m "Add configuration files"
git push -u origin main

# 2. 提交页面文件
git add _pages/ _includes/ _layouts/
git commit -m "Add page templates"
git push

# 3. 提交内容
git add _publications/ _teaching/ _data/
git commit -m "Add publications and teaching"
git push

# 4. 提交资源
git add assets/ images/ files/
git commit -m "Add assets and images"
git push

# 5. 提交文档
git add *.md LICENSE
git commit -m "Add documentation"
git push
```

---

## 配置 GitHub Pages

推送成功后：

### 1. 访问仓库设置
- 进入：`https://github.com/YOUR-USERNAME/YOUR-REPO-NAME`
- 点击 `Settings`

### 2. 配置 Pages
- 左侧菜单找到 `Pages`
- **Source**: 
  - Branch: `main`
  - Folder: `/ (root)`
- 点击 `Save`

### 3. 等待部署
- 等待 2-3 分钟
- 页面顶部会显示网站地址：
  - 如果仓库名是 `username.github.io`：`https://username.github.io`
  - 其他名字：`https://username.github.io/repo-name`

---

## ⚙️ 修改 _config.yml

在推送后，需要更新网站 URL：

### 在 VS Code 中编辑

1. 打开 `_config.yml`
2. 找到这两行并修改：

**如果仓库名是 `username.github.io`**:
```yaml
url: https://your-username.github.io
baseurl: ""
```

**如果仓库名是其他（如 `academic-website`）**:
```yaml
url: https://your-username.github.io
baseurl: "/academic-website"
```

3. 保存后推送更新：
   - `Ctrl+Shift+G` 打开源代码管理
   - 暂存更改
   - 提交消息：`Update site URL configuration`
   - 推送

---

## 🔄 日常更新工作流程

### 使用 VS Code（推荐）

1. **修改文件**（如更新出版物、添加课程等）

2. **查看更改**：
   - 按 `Ctrl+Shift+G` 打开源代码管理
   - 查看修改的文件列表

3. **暂存更改**：
   - 点击文件旁的 `+` 号暂存单个文件
   - 或点击顶部 `+` 暂存所有更改

4. **提交**：
   - 输入提交信息（如 "Update publications"）
   - 点击 `✓ 提交`

5. **推送**：
   - 点击 `...` → `推送`
   - 或点击底部状态栏的 `↑` 按钮

6. **等待**：
   - 1-2 分钟后网站自动更新

---

## 📱 VS Code 快捷键

| 功能 | 快捷键 |
|------|--------|
| 打开源代码管理 | `Ctrl+Shift+G` |
| 打开终端 | Ctrl + ` |
| 暂存所有更改 | `Ctrl+K Ctrl+S` |
| 提交 | `Ctrl+Enter` |
| 同步（拉取+推送）| 点击底部状态栏 ↻ |

---

## ❗ 常见问题解决

### Q1: 推送时提示 "authentication failed"？

**解决方案**：
1. 创建 Personal Access Token（见上面步骤）
2. 在 VS Code 中使用 token 作为密码

### Q2: 推送一直卡住不动？

**解决方案**：
1. 检查网络连接
2. 尝试关闭 VPN（如果有）
3. 使用 GitHub Desktop 替代

### Q3: 显示 "fatal: not a git repository"？

**解决方案**：
确保已经初始化 Git：
```powershell
git init
```

### Q4: 文件太多推送失败？

**解决方案**：
使用 GitHub Desktop（推荐）或分批推送（见上面方法三）

### Q5: 推送后网站 404？

**解决方案**：
1. 检查 GitHub Pages 是否已启用（Settings → Pages）
2. 检查 `_config.yml` 中的 `url` 和 `baseurl` 是否正确
3. 等待 3-5 分钟让部署完成

---

## 🎯 推荐的工作流程

### 对于初次部署（现在）：

```
1. GitHub Desktop 发布仓库（最简单）✅
   或
2. VS Code 源代码管理 + 推送
```

### 对于日常更新（以后）：

```
1. 在 VS Code 中修改文件
2. Ctrl+Shift+G 查看更改
3. 暂存 → 提交 → 推送
4. 等待 1-2 分钟自动部署
```

---

## ✅ 验证部署成功

访问你的网站后检查：

- [ ] 主页加载正常
- [ ] Publications 页面显示
- [ ] 书籍链接可点击
- [ ] Research Team 合作者链接正常
- [ ] Teaching 页面显示课程
- [ ] CV 页面正常
- [ ] 样式显示正确
- [ ] 图片加载（如已上传）
- [ ] 手机端访问正常

---

## 🎉 完成！

现在你可以：

1. **使用 GitHub Desktop**（推荐给初学者）
   - 最简单，无需命令行
   - 可视化界面
   - 自动处理认证

2. **使用 VS Code**（推荐给日常使用）
   - 集成在编辑器中
   - 快捷键操作
   - 适合频繁更新

3. **使用命令行**（高级用户）
   - 最灵活
   - 适合自动化

---

**选择最适合你的方法，有任何问题随时问我！** 🚀
