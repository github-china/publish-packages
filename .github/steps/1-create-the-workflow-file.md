<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## Step 1: 创建工作流文件（workflow）文件

_欢迎来到 "Publish packages" 课程! :wave:_

首先我们来看看下面这张图，它展示了 **持续集成**（CI）、**持续交付**（CD）和 **持续部署**（CD）三者之间的关系。

![](https://i.imgur.com/xZCkjmU.png)

**持续集成** (Continuous Integration, 简称CI) 是一种开发实践，要求开发者频繁地将代码变更合并到共享仓库中，每次更新时都会自动触发构建和测试，以确保合并代码更改的可靠性。
**持续交付** (Continuous Delivery, 简称CD) 是 CI 的下一步，不仅集成代码，还会将代码打包成可发布的版本，并存储到制品（artifact）仓库中。 
最后，**持续部署** (Continuous Deployment，同样缩写为 CD) 则更进一步，自动将这些发布版本部署到生产环境。

[**Docker**](https://www.docker.com/why-docker) 是一个容器运行引擎。  
**容器**是一种软件打包方式，能在不同环境中可靠运行。它包含了运行应用程序所需的一切内容，类似于虚拟机但更轻量。  
**Dockerfile** 是一个文本文件，其中包含构建 Docker 镜像所需的全部指令。  
**Docker 镜像** 是一个可执行的软件包，包含代码、依赖项、库、运行时、环境变量和配置文件。  
**Docker 容器** 则是 Docker 镜像在运行时的具体实例。

接下来，我们将创建一个 workflow 文件，用于将 Docker 镜像发布到 GitHub Packages。

### :keyboard: 实操环节：创建 workflow 文件

1. 打开一个新的浏览器标签页，方便一边阅读教程一边操作。
2. 进入代码仓库的 **Code**（代码）tab页。
3. 在 **main** 分支下拉菜单中，点击 **cd** 分支。
4. 进入 `.github/workflows/` 文件夹，点击 **Add file**（添加文件），然后选择 **Create new file**（创建新文件）。
5. 在 **Name your file...**（为文件命名）输入框中，输入 `publish.yml`。
6. 将以下内容粘贴到 `publish.yml` 文件中：
   ```yml
   name: Publish to Docker
   on:
     push:
       branches:
         - main
   permissions:
     packages: write
     contents: read
   jobs:
     publish:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v4
         # Add your test steps here if needed...
         - name: Docker meta
           id: meta
           uses: docker/metadata-action@v5
           with:
             images: ghcr.io/YOURNAME/publish-packages/game
             tags: type=sha
         - name: Login to GHCR
           uses: docker/login-action@v3
           with:
             registry: ghcr.io
             username: ${{ github.repository_owner }}
             password: ${{ secrets.GITHUB_TOKEN }}
         - name: Build container
           uses: docker/build-push-action@v5
           with:
             context: .
             push: true
             tags: ${{ steps.meta.outputs.tags }}
   ```
7. 将 `YOURNAME` 替换为你的 GitHub 用户名。
8. 确保镜像名称是唯一的（例如，使用你自己的用户名可避免冲突）。
9. 提交更改。
10. （可选）为便于跟踪课程中的所有修改，可以创建一个拉取请求（Pull Request）：
   - 点击 **Pull Requests** 标签页，
   - 点击 **New pull request**，
   - 设置 `base: main`，`compare: cd`。
11. 等待约 20 秒，然后刷新本页面。[GitHub Actions](https://docs.github.com/en/actions) 会自动检测到你的更改，并进入下一步。