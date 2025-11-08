下面分三部分：
1. GitHub 版本（国际站）
2. Gitee 镜像（国内站）
3. Obsidian 工作流整合
每个步骤都标注了时间成本，方便你安排。
# ✅ **Part 1：搭建 Quartz + GitHub Pages（海外站）**

## **Step 1：Fork Quartz 模板（1 分钟）**
访问  
👉 [https://github.com/jackyzha0/quartz](https://github.com/jackyzha0/quartz)
点击右上角的 **Fork**。
你的仓库会变成：  
`https://github.com/YOURNAME/quartz`

---
## **Step 2：准备本地工作目录（3–5 分钟）**
在你的电脑上：
```bash
git clone https://github.com/YOURNAME/quartz
cd quartz
```
然后将你的 Obsidian 文档库中的 Markdown 文件（或部分）复制到：
```
quartz/content/
```
Quartz 会自动把这个 content 文件夹变成网站页面。

---
## **Step 3：修改配置文件（3 分钟）**
打开：
```
quartz/quartz.config.ts
```
修改你的名字、网站简介等：
```ts
export const siteConfig = {
  title: "Yi 的技术笔记",
  description: "LLM × Agent × 自动交易 × Python",
  author: "Yi",
  ...
}
```

---
## **Step 4：本地预览网站（5 分钟）**
在项目根目录执行：
```bash
npm install
npx quartz build --serve
```
然后打开浏览器：  
👉 [http://localhost:8080](http://localhost:8080)
你会看到你的笔记已经变成漂亮的网站。

---
## **Step 5：部署到 GitHub Pages（5 分钟）**
1. 打开你的 GitHub 仓库
2. 点击 **Settings → Pages**
3. Source 选择：
    - **GitHub Actions**（默认 Quartz 已经带 actions.yml）
4. 保存
几分钟后你的网站就会生成，例如：  
👉 [https://yourname.github.io/](https://yourname.github.io/)
✅ 海外版成功

---
# ✅ **Part 2：构建 Gitee Pages（国内站）**
确保国内读者也能访问到你的博客。

---
## **Step 6：把 GitHub 仓库同步到 Gitee（3 分钟）**
进入 Gitee：
👉 [https://gitee.com](https://gitee.com)
创建一个仓库，名字可以同样叫 `quartz`。
点击：
**仓库 → 设置 → GitHub → GitHub 同步**
选择：
✅ “自动同步”  
✅ “从 GitHub → 覆盖 Gitee”
这样你后面只需要 push 到 GitHub，Gitee 会自动同步，不需要手动更新。

---
## **Step 7：启用 Gitee Pages（3–5 分钟）**
进入你的 Gitee 仓库：  
点击左侧菜单：
**服务 → Pages 服务**
启用 Pages，部署分支选择 `main`（或 master）。
⚠ Quartz 是静态网站，所以 Pages 支持。
部署完成后，你会得到：
👉 [https://yourname.gitee.io/quartz/](https://yourname.gitee.io/quartz/)
✅ 国内版成功
中国读者可以稳定访问。

---

# ✅ **Part 3：让 Obsidian 与 Quartz 完整结合（你的主要工作流）**

你未来的写作完全在 Obsidian 中进行。

---
## **Step 8：将 Quartz/content/ 设置为 Obsidian Vault（3 分钟）**
只需要：
1. 打开 Obsidian
2. File → Open folder as vault
3. 选择你的本地：
    ```
    quartz/content/
    ```

你之后所有笔记都写在这里。
✅ Obsidian 和 Quartz 无缝融合  
✅ 你写笔记 = 写博客

---

## **Step 9：设置 Git 提交同步（2 分钟）**
你未来的流程是：
```
Obsidian 写笔记  
↓
git add .
git commit -m "update"
git push
↓
GitHub 自动构建网站  
↓
Gitee 自动同步  
↓
✅ 中外双站点同时更新
```
不需要任何额外操作。

---

## **Step 10：在首页添加“中国镜像”按钮（可选，但强烈建议）**

修改：
```
quartz/content/index.md
```
加上：
```md
> 🌏 International version: https://yourname.github.io/
>
> 🇨🇳 国内镜像（推荐中国用户）: https://yourname.gitee.io/quartz/
```
读者就能自己选择入口。

---

# ✅ 你的最终成果（可立即使用）

你完成以上步骤后会得到：
✅ 国际站：  
[https://yourname.github.io/](https://yourname.github.io/)
✅ 国内镜像：  
[https://yourname.gitee.io/quartz/](https://yourname.gitee.io/quartz/)
✅ 内容完全来自 Obsidian  
✅ 文章可随时更新  
✅ 支持内部链接、搜索、图谱  
✅ Github/Gitee 自动同步  
✅ 维护成本极低  
✅ 技术笔记体验极佳
