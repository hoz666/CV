# 🎠 研究亮点轮播 - 快速使用指南

## ✅ 已完成的内容

### 1. **轮播组件**
- 文件：`_includes/swiper-carousel.html`
- 包含：完整HTML + CSS + JavaScript
- 功能：自动播放、循环、悬停暂停、响应式

### 2. **集成到首页**
- 位置：`_pages/about.md` (首页)
- 插入点：Welcome段落后，Featured Research Project前
- 标题：🌟 Research Highlights

### 3. **图片目录**
- 路径：`/images/lab/`
- 说明：`images/lab/README.md`

### 4. **使用指南**
- 文档：`CAROUSEL_IMAGE_GUIDE.md`（根目录）
- 内容：详细的图片要求、修改方法、故障排查

---

## 🎯 轮播特性

### ✨ 核心功能
- ✅ **自动播放**：3秒/张，循环播放
- ✅ **悬停暂停**：鼠标悬停时停止
- ✅ **左右箭头**：手动切换
- ✅ **分页圆点**：显示当前位置，可点击跳转
- ✅ **键盘控制**：左右箭头键切换
- ✅ **触摸滑动**：移动端手势支持

### 📱 响应式设计
- **移动端** (< 768px)：每屏1张
- **平板** (≥ 768px)：每屏2张
- **桌面** (≥ 1200px)：每屏3张

### 🎨 视觉效果
- **卡片悬停**：上浮 + 阴影增强
- **标题链接**：颜色变化 + 下划线
- **暗黑模式**：自动适配
- **流畅动画**：600ms过渡

---

## 📸 当前展示的6个项目

1. **Urban Forestry & Climate Change**
   - 链接：Chatelaine Magazine文章
   - 图片：rainwater-tree-trench.jpg

2. **Bioretention Systems Review**
   - 链接：2020年论文页
   - 图片：bioretention-cell.jpg

3. **Permeable Pavements Book**
   - 链接：2018年书籍页
   - 图片：permeable-pavement.jpg

4. **Custom Flow Measurement Device**
   - 链接：2020年论文页
   - 图片：velocity-meter.jpg

5. **Urbanization & Climate Impacts**
   - 链接：2021年论文页
   - 图片：climate-modeling.jpg

6. **Environmental Hydraulics Lab**
   - 链接：Research Team页面
   - 图片：lab-facilities.jpg

---

## 🚀 下一步：添加真实图片

### 方法1：本地上传
```bash
# 1. 准备6张图片（见CAROUSEL_IMAGE_GUIDE.md）
# 2. 放入images/lab/目录
# 3. 提交
git add images/lab/*.jpg
git commit -m "Add research carousel images"
git push origin 8:main
```

### 方法2：GitHub网页
1. 访问 https://github.com/hoz666/CV/tree/main/images/lab
2. 点击 "Add file" → "Upload files"
3. 上传6张图片
4. 提交

---

## 🎨 自定义调整

### 修改轮播速度
编辑 `_includes/swiper-carousel.html` 第316行：
```javascript
autoplay: {
  delay: 3000,  // 改为 4000 = 4秒
}
```

### 修改幻灯片数量
编辑 `_includes/swiper-carousel.html` 第330-338行：
```javascript
breakpoints: {
  768: {
    slidesPerView: 2,  // 改为1或3
  },
  1200: {
    slidesPerView: 3,  // 改为2或4
  },
}
```

### 禁用自动播放
删除或注释掉第316-320行的autoplay配置

### 添加新幻灯片
复制第149-171行的一个 `<div class="swiper-slide">` 块，修改内容

---

## 📋 技术细节

### CDN引用
- **Swiper CSS**：https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css
- **Swiper JS**：https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js
- **版本**：Swiper 11（最新稳定版）

### 浏览器兼容性
- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ iOS Safari 14+
- ✅ Android Chrome 90+

### 性能优化
- 懒加载图片（onerror fallback）
- 硬件加速动画（transform/opacity）
- 响应式图片加载
- 移动端触摸优化

---

## 🎯 预期效果

### 首页浏览体验
1. 用户打开首页
2. 看到Welcome介绍
3. **立即看到6个研究亮点轮播** 👈 新增
4. 可以手动/自动浏览代表作
5. 点击标题链接查看详情
6. 继续向下浏览Featured Project等内容

### 提升指标
- ✅ **停留时长**：增加视觉吸引力
- ✅ **跳出率**：降低，更多内容可探索
- ✅ **点击率**：直接链接到论文/项目页
- ✅ **移动体验**：友好的滑动交互
- ✅ **专业度**：展示研究实力

---

## ✅ 部署状态

- **Commit**: "Add Swiper.js responsive carousel for research highlights on homepage"
- **文件**：
  - ✅ `_includes/swiper-carousel.html`（轮播组件）
  - ✅ `_pages/about.md`（首页集成）
  - ✅ `images/lab/README.md`（图片目录说明）
  - ✅ `CAROUSEL_IMAGE_GUIDE.md`（使用指南）
- **状态**: ✅ 已推送到GitHub
- **部署**: 🚀 GitHub Actions正在构建中

---

## 📞 需要帮助？

查看 `CAROUSEL_IMAGE_GUIDE.md` 获取：
- 详细图片要求
- 内容修改方法
- 故障排查指南
- 常见问题解答

---

## 🎉 现在可以：

1. ⏱️ **等待1-2分钟** GitHub Actions完成构建
2. 🌐 **访问网站首页** https://hoz666.github.io/CV/
3. 📸 **上传真实图片** 到 `/images/lab/`
4. ✨ **享受专业的研究展示效果！**
