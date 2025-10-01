# 📸 图片上传指南 / Image Upload Guide

## 1. 🖼️ 头像照片 / Profile Avatar

### 上传步骤：
1. **准备照片**：选择清晰的正方形照片（推荐尺寸：300x300px 或更大）
2. **重命名照片**：将照片命名为 `profile.png`
3. **上传位置**：将照片复制到以下文件夹
   ```
   E:\VS code\9.30Caterina_website\Caterina-Valeo-master\images\
   ```
4. **覆盖现有文件**：直接覆盖现有的 `profile.png` 文件
5. **刷新浏览器**：使用 Ctrl+Shift+R 强制刷新查看效果

### 支持的格式：
- ✅ PNG（推荐）- 透明背景效果更好
- ✅ JPG/JPEG - 文件更小
- ✅ GIF - 如果需要动画效果

### 注意事项：
- 照片会自动显示为圆形（边框为蓝色）
- 建议使用正方形照片避免裁剪变形
- 文件大小建议不超过 500KB

---

## 2. 🏢 赞助商图标 / Sponsor Logos

您提到需要在每个页面底部显示三个赞助商图标。我已经为您准备好了配置。

### 上传步骤：

#### 第一步：准备图标文件
1. 准备三个赞助商的图标文件
2. 推荐尺寸：200x80px 或类似比例（宽度大于高度）
3. 建议使用 PNG 格式（支持透明背景）

#### 第二步：命名和上传
将三个图标文件按以下命名保存到 `images/` 文件夹：
```
E:\VS code\9.30Caterina_website\Caterina-Valeo-master\images\
├── sponsor1.png  (第一个赞助商)
├── sponsor2.png  (第二个赞助商)
└── sponsor3.png  (第三个赞助商)
```

#### 第三步：配置链接（可选）
如果赞助商需要点击跳转到他们的网站，请告诉我三个链接地址，我会添加到配置中。

### 显示效果：
- ✨ 三个图标会在页面底部水平排列
- 💫 自动适配移动设备（手机上会垂直堆叠）
- 🎨 灰度滤镜效果，鼠标悬停时显示彩色
- 📐 自动调整大小保持一致

---

## 3. 📂 其他图片上传

### 如果需要在页面中添加其他图片：

1. **上传到 images 文件夹**：
   ```
   E:\VS code\9.30Caterina_website\Caterina-Valeo-master\images\
   ```

2. **在 Markdown 文件中引用**：
   ```markdown
   ![图片描述]({{ site.url }}{{ site.baseurl }}/images/your-image.png)
   ```

3. **或使用 HTML**：
   ```html
   <img src="/images/your-image.png" alt="图片描述" width="600">
   ```

---

## 4. 🔧 常见问题

### Q: 上传后图片不显示？
A: 尝试以下步骤：
1. 清空浏览器缓存（Ctrl+Shift+Delete）
2. 强制刷新页面（Ctrl+Shift+R）
3. 重启 Jekyll 服务器
4. 检查文件名是否完全匹配（区分大小写）

### Q: 图片显示模糊？
A: 使用更高分辨率的原图，至少 2x 实际显示尺寸

### Q: 图片文件太大？
A: 使用在线压缩工具：
- TinyPNG (https://tinypng.com/) - PNG 压缩
- Squoosh (https://squoosh.app/) - 各种格式

### Q: 需要修改赞助商图标？
A: 直接替换 images 文件夹中的对应文件即可

---

## 5. ✅ 文件结构参考

```
Caterina-Valeo-master/
└── images/
    ├── profile.png          ← 您的头像照片（已配置）
    ├── sponsor1.png         ← 赞助商1图标（待上传）
    ├── sponsor2.png         ← 赞助商2图标（待上传）
    ├── sponsor3.png         ← 赞助商3图标（待上传）
    ├── bio-photo.jpg        ← 原有文件
    └── ...                  ← 其他图片
```

---

## 📞 需要帮助？

如果您：
- 已准备好赞助商图标但不确定如何命名
- 需要调整图标的显示位置或样式
- 遇到任何图片上传问题

请随时告诉我，我会立即帮您解决！🚀
