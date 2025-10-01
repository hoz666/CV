# 如何更换头像照片 📸

## 当前状态
- ✅ 临时使用默认的 `profile.png` 
- 🎯 需要替换为你的真实照片

## 更换步骤

### 方法 1：替换现有文件（推荐）
1. 找到你想使用的照片（建议是图片3那张专业照）
2. 将照片重命名为 `profile.png`
3. 复制到这个位置，覆盖现有文件：
   ```
   E:\VS code\9.30Caterina_website\Caterina-Valeo-master\images\profile.png
   ```
4. 刷新网站浏览器页面

### 方法 2：使用新文件名
1. 将你的照片保存到 `images` 文件夹，例如命名为 `Caterina_Valeo.jpg`
2. 打开 `_config.yml` 文件
3. 找到这一行：
   ```yaml
   avatar           : "profile.png"
   ```
4. 改为：
   ```yaml
   avatar           : "Caterina_Valeo.jpg"
   ```
5. **重启 Jekyll 服务器**（Ctrl+C 停止，然后重新运行 `bundle exec jekyll serve`）

## 照片要求
- ✅ 格式：JPG 或 PNG
- ✅ 尺寸：建议至少 300x300 像素
- ✅ 类型：正方形或圆形构图最佳（会自动裁剪为圆形）
- ✅ 背景：纯色背景或简洁背景效果最好

## 当前配置
```yaml
avatar           : "profile.png"
```

位于文件：`_config.yml` 第 26 行

---

**提示**：更换照片后，清除浏览器缓存（Ctrl+Shift+R）以确保看到新照片。
