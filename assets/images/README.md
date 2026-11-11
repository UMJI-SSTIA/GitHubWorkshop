# GitHub 趣味案例截图

截图日期：2026-11-05。图片为 GitHub 实际页面截图，Star 数随时间变化。

| 案例 | 截图 | 来源 | 展示角度 |
| --- | --- | --- | --- |
| 免费电子书资源 | [github-free-programming-books.jpg](github-free-programming-books.jpg) | [EbookFoundation/free-programming-books](https://github.com/EbookFoundation/free-programming-books) | 社区共同整理免费编程书籍和学习资源，GitHub 也能成为图书导航。 |
| 程序员做饭指南 | [github-howtocook.jpg](github-howtocook.jpg) | [Anduin2017/HowToCook](https://github.com/Anduin2017/HowToCook) | 用清晰、准确的步骤编写菜谱，还能通过 PR 一起完善。 |
| 做饭指南正文 | [github-howtocook-readme.jpg](github-howtocook-readme.jpg) | [HowToCook README](https://github.com/Anduin2017/HowToCook#readme-ov-file) | 展示项目动机、菜谱入口及社区贡献方式。 |
| 高 Star 的“空仓库” | [github-nocode.jpg](github-nocode.jpg) | [kelseyhightower/nocode](https://github.com/kelseyhightower/nocode) | 约 66k Star：以“不写代码、不部署”为笑点。它并非真正没有文件，仍有 README、许可证等；适合说明 Star 不等于代码量或实用性。 |
| 科技爱好者周刊 | [github-weekly.jpg](github-weekly.jpg) | [ruanyf/weekly](https://github.com/ruanyf/weekly) | 用仓库归档周刊，用 Issue 接收读者投稿，用 PR 修订内容。 |
| 自学一套计算机课程 | [github-ossu-computer-science.jpg](github-ossu-computer-science.jpg) | [ossu/computer-science](https://github.com/ossu/computer-science) | 社区组织计算机科学自学课程，GitHub 也能承载学习路线。 |

推荐讲解顺序：电子书 → 菜谱 → no-code → 周刊 → 自学课程。

## 在文档中引用

这些图片按要求存放于项目根目录 `assets/images/`。
从 `docs/en/github-introduction/what-is-github.md` 等页面在本地 Markdown 预览中引用，例如：

```markdown
![程序员做饭指南](../../../assets/images/github-howtocook.jpg)
```

如果要随当前 MkDocs 网站发布，需要将选用图片复制到 `docs/assets/images/`，再使用 `../../assets/images/文件名.jpg` 引用；根目录的 `assets/` 不会由默认 MkDocs 文档构建自动收录。

## 平台介绍配图

截图日期：2026-11-05。已裁去浏览器栏及登录账户区域，并清除 EXIF/XMP 等元数据。网站使用的副本位于 `docs/assets/images/`。

| 截图 | 来源 |
| --- | --- |
| [GitHub Trending](platform-github.jpg) | https://github.com/trending |
| [Gitee 开源项目](platform-gitee.jpg) | https://gitee.com/explore |
| [Hugging Face 模型库](platform-huggingface.jpg) | https://huggingface.co/models |
