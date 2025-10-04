# 研究亮点轮播图片指南

## 📸 图片要求

### 位置
所有轮播图片应放在：`/images/lab/` 目录下

### 推荐尺寸
- **分辨率**：1200×800px（或相似比例）
- **宽高比**：3:2 或 16:9
- **文件大小**：< 500KB（优化后）
- **格式**：JPG 或 PNG

---

## 🖼️ 需要的6张图片

### 1. `rainwater-tree-trench.jpg`
**内容**：城市雨水树沟系统
- 展示街道树木与地下渗透系统
- 可以是施工现场或完成效果图
- 最好有树木和城市背景

### 2. `bioretention-cell.jpg`
**内容**：生物滞留池/过滤池
- 现场实验装置或研究设施
- 植被、土壤层次可见
- 实验室或野外场景

### 3. `permeable-pavement.jpg`
**内容**：透水铺装测试
- 透水路面材料特写
- 水流测试场景
- 可以展示对比效果

### 4. `velocity-meter.jpg`
**内容**：自制流速仪
- Arduino控制的测量设备
- 现场部署场景
- 技术细节展示

### 5. `climate-modeling.jpg`
**内容**：气候模拟研究
- 电脑建模界面截图
- PCSWMM软件界面
- 数据可视化图表
- 研究团队讨论场景

### 6. `lab-facilities.jpg`
**内容**：实验室设施
- 环境水力学实验室全景
- 研究团队工作场景
- 实验设备与仪器

---

## 🎨 图片优化建议

### 在线工具：
- **压缩**：[TinyPNG](https://tinypng.com/) - 保持质量的同时减小文件大小
- **编辑**：[Photopea](https://www.photopea.com/) - 免费在线Photoshop
- **裁剪**：确保图片中心是主要内容

### 命名规范：
```
images/lab/
├── rainwater-tree-trench.jpg
├── bioretention-cell.jpg
├── permeable-pavement.jpg
├── velocity-meter.jpg
├── climate-modeling.jpg
└── lab-facilities.jpg
```

---

## 🔄 如何替换/添加图片

### 方法1：通过Git
```bash
# 1. 将图片复制到正确位置
cp your-image.jpg images/lab/rainwater-tree-trench.jpg

# 2. 添加到Git
git add images/lab/

# 3. 提交
git commit -m "Add carousel images for research highlights"

# 4. 推送
git push origin 8:main
```

### 方法2：通过GitHub网页
1. 访问 https://github.com/hoz666/CV
2. 进入 `images/lab/` 目录
3. 点击 "Add file" → "Upload files"
4. 拖拽你的6张图片
5. 填写commit信息并提交

---

## 📝 修改轮播内容

编辑文件：`_includes/swiper-carousel.html`

### 修改标题/链接：
```html
<a href="YOUR_LINK" class="slide-title">
  Your Title Here
</a>
```

### 修改描述文字：
```html
<p class="slide-description">
  Your description text here...
</p>
```

### 修改底部元数据：
```html
<div class="slide-meta">
  Journal Name, Year | Additional Info
</div>
```

### 添加新的轮播项：
复制一个完整的 `<div class="swiper-slide">...</div>` 块，粘贴到轮播容器中，然后修改内容。

---

## ⚙️ 轮播设置调整

编辑 `_includes/swiper-carousel.html` 底部的JavaScript：

### 修改自动播放速度：
```javascript
autoplay: {
  delay: 3000,  // 改为 4000 = 4秒
  ...
}
```

### 修改响应式断点：
```javascript
breakpoints: {
  768: {
    slidesPerView: 2,  // 中等屏幕显示2张
  },
  1200: {
    slidesPerView: 3,  // 大屏幕显示3张
  },
}
```

### 禁用自动播放：
```javascript
autoplay: false,  // 或直接删除autoplay配置
```

---

## 🎯 后备图片

如果某张图片缺失，系统会自动显示占位图：
- 占位图路径：`/images/500x300.png`
- 你可以创建一个通用的占位图放在这个位置

---

## ✅ 检查清单

部署前确认：
- [ ] 6张图片已上传到 `/images/lab/`
- [ ] 图片文件名与代码中一致
- [ ] 图片大小已优化（< 500KB each）
- [ ] 图片比例统一（建议3:2）
- [ ] 在本地预览正常
- [ ] 提交并推送到GitHub
- [ ] 等待GitHub Actions构建完成（1-2分钟）
- [ ] 刷新网站查看效果

---

## 🐛 故障排查

### 轮播不显示：
1. 检查浏览器控制台错误
2. 确认Swiper CDN可访问
3. 清除浏览器缓存（Ctrl+F5）

### 图片不显示：
1. 检查图片路径是否正确
2. 确认图片已上传到正确位置
3. 检查文件名大小写（区分大小写）

### 移动端显示问题：
1. 检查响应式断点设置
2. 测试不同屏幕尺寸
3. 确认触摸滑动功能正常

---

## 📞 需要帮助？

如有问题，请提供：
1. 错误截图
2. 浏览器控制台信息
3. 具体的问题描述
