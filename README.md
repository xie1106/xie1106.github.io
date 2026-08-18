# 网页集合

自动收集 GitHub Pages 网页，支持分类筛选、回收站、置顶、拖拽排序。

## 密码保护设置

1. 在浏览器控制台运行以下代码生成密码hash：

```javascript
crypto.subtle.digest('SHA-256', new TextEncoder().encode('你的密码'))
  .then(h => console.log(Array.from(new Uint8Array(h)).map(b => b.toString(16).padStart(2,'0')).join('')))
```

2. 复制输出的hash字符串

3. 编辑 `index.html`，找到这一行：

```javascript
const PASSWORD_HASH = "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855";
```

4. 替换为你的hash，提交推送

**示例**：
- 密码 `hello123` 的 hash：`a665a45920422f9d417e4867efdc4fb8a04a1f3fff1fa07e998e86f7f7a27ae3`

## 功能说明

- **自动同步**：打开页面时自动从GitHub拉取最新仓库列表
- **回收站**：删除的页面可恢复，数据存储在 `_prefs.json` 中
- **置顶**：常用页面置顶，跨设备同步（需设置GitHub Token）
- **拖拽排序**：桌面按住拖动，手机长按350ms后拖动
- **分类筛选**：工具系统 / 分析报告 / 项目页面
- **跨设备同步**：设置Token后，置顶、排序、回收站在所有设备共享
