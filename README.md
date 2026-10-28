# GSC 练习站：从上线到被收录

这个文件夹里是一个可以直接上传的静态网站，共 4 个页面 + 样式 + sitemap + robots。

目标：让 Google Search Console 真的收录你的站点，并且你能在后台看到数据。

---

## 第 0 步：先改一个地方

把下面两个文件里的 `YOURNAME` 换成你的 GitHub 用户名（注意是**用户名**，不是昵称）：

- `robots.txt`
- `sitemap.xml`

例如用户名是 `Chiltin`，就改成：

```
https://Chiltin.github.io/gsc-practice/
```

用记事本或 VS Code 的「全部替换」即可。

---

## 第 1 步：上传到 GitHub

1. 注册/登录 GitHub。
2. 新建一个 **Public** 仓库，名字必须是 `gsc-practice`。
3. 进入仓库，点 `Add file` → `Upload files`，把本文件夹里的**所有文件**拖进去（不要上传外层文件夹）。
4. 点 `Commit changes`。

---

## 第 2 步：开启 GitHub Pages

1. 进入仓库的 `Settings` → 左侧 `Pages`。
2. `Source` 选 `Deploy from a branch`。
3. Branch 选 `main`，目录选 `/ (root)`，点 `Save`。
4. 等 1–2 分钟，刷新页面，会看到站点地址：

```
https://你的用户名.github.io/gsc-practice/
```

5. 用浏览器打开，确认四个页面都能点开。

---

## 第 3 步：在 GSC 里添加站点

1. 打开 `https://search.google.com/search-console`。
2. 左上角 `添加资源` → 选 **网址前缀**（不是「网域」）。
3. 输入完整地址，**结尾带斜杠**：

```
https://你的用户名.github.io/gsc-practice/
```

4. 验证方式选 **HTML 文件**。
5. 下载 Google 给你的那个 `googleXXXXXXXX.html` 文件。
6. 把它上传到仓库**根目录**（和 `index.html` 同一层），提交。
7. 等 GitHub Pages 重新部署（1–2 分钟），回到 GSC 点「验证」。

验证通过后会显示「所有权已验证」。

---

## 第 4 步：提交 sitemap

1. GSC 左侧菜单 → `索引` → `站点地图`。
2. 在「添加新的站点地图」里输入：

```
sitemap.xml
```

3. 点提交。状态显示「成功」就说明读到了。

如果显示「无法读取」，先直接在浏览器打开
`https://你的用户名.github.io/gsc-practice/sitemap.xml`，确认能看到 XML 内容。

---

## 第 5 步：请求收录

1. 顶部搜索框输入首页地址，回车。
2. 点 `请求编入索引`。
3. 对另外三个页面也各做一次。

这不是保证收录，只是告诉 Google「这里有新页面」。

---

## 第 6 步：等，然后看数据

- 新站通常需要 **几天到两三周** 才会出现在搜索结果里。
- GSC 的 `性能` 报告一般要等 2–3 天才有数据。
- 检查收录情况：在 Google 搜索框输入 `site:你的用户名.github.io/gsc-practice`
- GSC → `索引` → `网页`，可以看到「已编入索引」和「未编入索引」的原因。

---

## 你可以观察到的四个真实现象

1. **提交了 sitemap 不等于被收录**：它只是让 Google 知道这些网址存在。
2. **收录有延迟**：新域名/新站点要等爬虫来抓，几天到几周都正常。
3. **改了内容，收录不会立刻更新**：GSC 里会显示上次抓取时间。
4. **`site:` 查不到，不代表一定没收录**：可能是索引还没更新完。

---

## 常见问题

**Q：GitHub Pages 打开是 404？**
等几分钟再看；确认 `index.html` 在仓库根目录，不是在子文件夹里。

**Q：GSC 验证失败？**
确认验证文件也上传到了根目录，并且 GitHub Pages 已经重新部署完成。

**Q：没有域名可以吗？**
可以。URL 前缀资源支持 `github.io` 这种子域名，用 HTML 文件验证即可。

**Q：想用自己的域名？**
在仓库 Settings → Pages 里绑定自定义域名，再到域名服务商加 CNAME 解析。这一步不是必须的。
