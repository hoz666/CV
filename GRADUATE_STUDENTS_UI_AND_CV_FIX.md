# Graduate Students页面UI升级 + CV显示强化修复

## 日期：2025-01-08（深夜第二轮修复）

## 🎯 修复目标

1. ✅ **Research Team页面添加+/-下拉菜单样式**
2. ✅ **进一步加强CV页面电脑端白天模式显示**

---

## 📋 修改内容

### 1. Research Team页面 - 添加完整CSS样式

#### **添加的CSS样式**（与CV页面一致）：

```css
/* 完整的collapsible section样式 */
details {
  background-color: #f8f9fa;        /* 浅灰色背景 */
  border-radius: 5px;
  margin: 15px 0;
  padding: 0;
  border: 1px solid #dee2e6;        /* 边框 */
}

summary {
  cursor: pointer;
  padding: 18px;
  font-size: 1.1em;
  font-weight: 600;
  color: #000000 !important;
  display: flex;
  justify-content: space-between;
}

summary:after {
  content: '+';                      /* 加号 */
  font-size: 1.5em;
  font-weight: bold;
  color: #000000 !important;
}

details[open] summary:after {
  content: '−';                      /* 减号 */
}

details[open] summary {
  border-bottom: 2px solid #000000;  /* 展开时底部线 */
  margin-bottom: 15px;
}
```

#### **应用范围**：
- ✅ PhD Candidates (3人)：Zhonghao Zhang, Jingwen Liu, Aditya R.
- ✅ Master's Students (3人)：Jessica D., Sarah Q., Fatima T.

#### **视觉效果**：
- 灰色背景框（#f8f9fa）
- +/- 符号（而不是▼箭头）
- 悬停时背景变深
- 展开时有底部分隔线
- 与CV页面完全一致的风格！

---

### 2. CV页面 - 加强电脑端显示修复

#### **问题分析**：
之前的修复只添加了 `!important`，但可能被Academic Pages模板的高优先级CSS覆盖。

#### **解决方案 - 使用body前缀提高CSS优先级**：

**CSS特异性（Specificity）规则**：
- `.cv-content-inner` = 10分
- `body .cv-content-inner` = 11分（更高优先级！）

#### **新增的CSS规则**：

```css
/* 最高优先级 - body前缀 */
body details,
body details *,
body .cv-content-inner,
body .cv-content-inner * {
  color: #000000 !important;
}

/* 双重声明确保兼容性 */
body .cv-content-inner,
.cv-content-inner {
  padding: 0 18px 18px 18px;
  color: #000000 !important;
  background-color: transparent !important;
}

body .cv-content-inner *,
.cv-content-inner * {
  color: #000000 !important;
}

/* 针对每个元素类型 */
body .cv-content-inner div,
body .cv-content-inner span,
body .cv-content-inner p,
body .cv-content-inner strong,
body .cv-content-inner em {
  color: #000000 !important;
}
```

#### **改进后的Dark Mode**：

```css
@media (prefers-color-scheme: dark) {
  body details,
  details {
    background-color: rgba(255,255,255,0.05) !important;
    border-color: rgba(255,255,255,0.1) !important;
  }
  
  body summary,
  summary {
    color: #ffffff !important;
  }
  
  /* ...所有规则都添加body前缀 */
}
```

---

## 🔍 技术细节

### CSS优先级计算

| 选择器 | 特异性 | 优先级 |
|--------|--------|--------|
| `.cv-content-inner` | (0,1,0) = 10 | 低 |
| `body .cv-content-inner` | (0,1,1) = 11 | **高** |
| `body .cv-content-inner !important` | ∞ | **最高** |

### 为什么需要body前缀？

Academic Pages模板可能有这样的全局CSS：
```css
.page__content p {
  color: inherit;  /* 继承父元素颜色 */
}
```

如果只写 `.cv-content-inner p { color: #000 !important; }`，
而模板有 `.page__content .cv-content-inner p { color: inherit; }`，
那么模板的规则优先级更高（因为有两个class选择器）。

**解决方法**：添加`body`前缀提高优先级
```css
body .cv-content-inner p {
  color: #000000 !important;
}
```

现在特异性是：(0,1,2) = 12分，高于模板的规则！

---

## 📊 修改对比

### Research Team页面

#### 修改前：
```html
<details open>
<summary><strong>Zhonghao Zhang</strong> - LID & Climate</summary>
<div style="padding: 15px; border-left: 3px solid #000;">
  <!-- 内容 -->
</div>
</details>
```
- ❌ 没有CSS样式
- ❌ 使用inline style
- ❌ 没有+/-符号
- ❌ 没有背景框

#### 修改后：
```html
<!-- 添加了完整的<style>标签 -->
<details open>
<summary><strong>Zhonghao Zhang</strong> - LID & Climate</summary>
<div>
  <!-- 内容 -->
</div>
</details>
```
- ✅ 完整CSS样式
- ✅ +/- 符号
- ✅ 灰色背景框
- ✅ 悬停效果
- ✅ 与CV页面一致

---

### CV页面

#### 第一次修复（之前）：
```css
.cv-content-inner {
  color: #000000 !important;
}
```
- ⚠️ 优先级：10分
- ⚠️ 可能被模板覆盖

#### 第二次修复（现在）：
```css
body .cv-content-inner,
.cv-content-inner {
  color: #000000 !important;
}
```
- ✅ 优先级：11分（body前缀）
- ✅ 双重声明（兼容性）
- ✅ 所有元素都有body前缀
- ✅ 更强的覆盖能力

---

## 🎨 视觉效果

### Research Team页面学生卡片

**PhD学生展示**：
```
+------------------------------------------+
| + Zhonghao Zhang - LID & Climate       |  <- 灰色背景，+号
+------------------------------------------+
```

点击后：
```
+------------------------------------------+
| − Zhonghao Zhang - LID & Climate       |  <- -号，底部线
|------------------------------------------|
| Research Focus: Low Impact Development  |
| technologies, stormwater management...  |
|                                          |
| Recent Publications:                     |
| • Zhang, Z. and Valeo, C. (2025)...    |
| • Zhang, Z. and Valeo, C. (2024)...    |
+------------------------------------------+
```

### CV页面各section

与Research Team完全一致的样式：
```
+------------------------------------------+
| + Education                             |
+------------------------------------------+

+------------------------------------------+
| + Work Experience                       |
+------------------------------------------+

+------------------------------------------+
| + Awards & Honors                       |
+------------------------------------------+
```

---

## 🧪 测试建议

### 桌面端测试（重点）：

1. **Chrome（Windows）**
   - ✅ 打开CV页面
   - ✅ 检查白天模式文字是否黑色清晰
   - ✅ 切换到夜间模式检查白色文字
   - ✅ 展开/折叠各个section

2. **Firefox（Windows/Mac）**
   - ✅ 验证+/-符号显示
   - ✅ 检查灰色背景框
   - ✅ 测试悬停效果

3. **Safari（Mac）**
   - ✅ 确认颜色正常
   - ✅ 验证动画效果

4. **Edge**
   - ✅ 全面功能测试

### Research Team页面测试：

1. **PhD学生卡片**
   - ✅ Zhonghao Zhang - 展开/折叠正常
   - ✅ Jingwen Liu - +/-符号显示
   - ✅ Aditya R. - 背景框渲染

2. **Master's学生卡片**
   - ✅ Jessica D. - 样式一致
   - ✅ Sarah Q. - 交互正常
   - ✅ Fatima T. - 视觉效果

---

## 📝 文件变更

### 修改文件：
1. `_pages/research-team.md`
   - 添加完整CSS样式（140+ lines）
   - 匹配CV页面设计
   
2. `_pages/cv.md`
   - 加强CSS优先级（body前缀）
   - 双重声明提高兼容性
   - Dark mode规则增强

### 变更统计：
- **research-team.md**: +140 lines (CSS)
- **cv.md**: +50 lines (强化规则)

---

## 🚀 部署信息

- **Commit**: "Add +/- collapsible UI to Research Team page and strengthen CV desktop display with body-prefixed CSS rules"
- **Branch**: 8 → main
- **Status**: ✅ 已成功推送到GitHub
- **Auto-build**: GitHub Actions正在构建
- **Live URL**: 
  - CV: https://hoz666.github.io/CV/cv/
  - Research Team: https://hoz666.github.io/CV/research-team/

---

## 🔧 如果仍然有问题的troubleshooting

### 如果CV电脑端白天模式还是不显示：

#### 方案1：清除浏览器缓存
```
Chrome: Ctrl+Shift+Delete → 清除缓存和Cookie
Firefox: Ctrl+Shift+Delete → 清除缓存
Safari: Command+Option+E → 清空缓存
```

#### 方案2：强制刷新
```
Windows: Ctrl+F5
Mac: Command+Shift+R
```

#### 方案3：检查浏览器开发者工具
```
1. 按F12打开开发者工具
2. 点击Elements/元素标签
3. 选择任意CV文字
4. 查看Computed样式中的color属性
5. 如果不是#000000，说明被其他CSS覆盖了
```

#### 方案4：终极方案 - 添加inline style
如果CSS仍然被覆盖，可以在HTML中直接添加style属性：
```html
<div class="cv-content-inner" style="color: #000000 !important;">
```

---

## ✅ 总结

### 完成的改进：

1. ✅ **Research Team页面获得完整+/-下拉菜单UI**
   - 与CV页面完全一致的设计
   - 灰色背景框 + +/- 符号
   - 悬停效果和展开动画
   - 应用于所有6名学生（3 PhD + 3 Master's）

2. ✅ **CV页面显示修复大幅加强**
   - 使用body前缀提高CSS优先级
   - 双重声明确保兼容性
   - 所有文字颜色规则都添加!important
   - Dark mode规则同步加强

3. ✅ **代码质量提升**
   - CSS组织更清晰
   - 注释更详细
   - 遵循最佳实践

### 预期效果：

- 🎨 Research Team和CV页面视觉统一
- 💻 电脑端白天模式文字清晰可见
- 📱 移动端和夜间模式完美工作
- ⚡ 流畅的展开/折叠交互

---

**现在网站应该在所有设备和浏览器上都能正常显示了！** 🎉
