<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses the MIT license.
-->

[English](https://github.com/skills/publish-packages) | 中文

> 本课程翻译自 Github Skills，全部课程请点击 [这里查看](https://www.github-zh.com/getting-started)

# 发布包到 GitHub Packages

_本节课我们将使用 GitHub Actions 将你的项目发布为 Docker 镜像。_

</header>

<!--
  <<< Author notes: Course start >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
-->

## Welcome

GitHub Packages 是一个托管和管理包的平台，支持多种包类型如npm包、Docker镜像、Maven等。
搭配 GitHub Actions，你可以实现从代码构建、测试到自动部署的一体化持续交付（CD）流程。 在这门课程中，你将学习如何使用 Actions 构建、测试，并将可直接部署的构建产物发布到 GitHub Packages。

- **目标人群**：开发者、运维、全栈工程师、云工程师。
- **学习内容**：持续交付、如何保存和访问构建产物、包管理，以及如何将包发布到 GitHub Packages。
- **您将完成**：我们将构建一个小游戏 Docker 镜像。
- **先决条件**：建议你先完成以下课程：[Hello, GitHub Actions](https://github.com/github-china/hello-github-actions) 和 [Continuous Integration](https://github.com/skills/continuous-integration)。
- **课程时长**：不到 30 分钟。

在本课程中，你将：

1. 创建一个工作流（workflow）
2. 添加一个 Dockerfile 文件
3. 合并你的拉取请求（Pull Request）

### 如何开始本课程

<!-- For start course, run in JavaScript:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'publish-packages',
  owner: '@me',
  name: 'skills-publish-packages',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=github-china&template_name=publish-packages&owner=%40me&name=skills-publish-packages&description=My+clone+repository&visibility=public)

1. 右键点击上方 **Start course** 按钮，选择在新标签页中打开链接。
2. 在新页面中根据系统提示新建一个仓库。
   - 仓库名称、描述这些字段系统已经帮我们自动填充好了，您可以按需修改。
   - 建议选择公开仓库，因为私有仓库有[GitHub Actions 分钟数限制](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions)。
   - 最后点击 Create repository 按钮
3. 仓库创建完毕后，等待大约 20 秒（等待Action执行），然后刷新页面。注意是刷新您仓库的页面，不是本课程的页面。如果页面没有变化，请继续等待。然后按照 README 中的步骤一步步进行。

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/publish-packages) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
