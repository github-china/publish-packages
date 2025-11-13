<!--
  <<< Author notes: Step 4 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 4: 拉取你的镜像

工作流正在后台构建并推送你的 Docker 镜像到 GitHub Container Registry（GHCR）。这个过程可能需要几分钟，请稍等片刻🍿，等构建完成后再继续。

:cook: **在等待构建完成的同时，我们先准备好本地环境。**

要在本地运行 Docker 镜像，我们需要先安装 Docker 环境。为了方便使用并确保跨平台兼容性（Windows、macOS 和 Linux），我们选择安装带有图像界面的 Docker Desktop。

请注意：**Docker Engine** 是运行容器的基础组件，而 **[Docker Desktop](https://www.docker.com/blog/how-to-check-docker-version/)** 则是一个集成了 Docker Engine、图形界面（GUI）和虚拟机（VM）的**一体化安装包**，对初学者更友好。

### 准备工作

1. Windows 用户请查看 [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/#install-docker-desktop-on-windows) 安装说明。
   * 如果你使用的是 macOS 或 Linux，请通过页面左侧的导航菜单找到对应系统的安装说明。

2. 安装完毕后，启动 Docker Desktop，并[简单熟悉一下界面](https://docs.docker.com/desktop/use-desktop/)。

3. 打开终端命令行，准备运行 `docker` 命令。

:inbox_tray: **接下来，我们需要登录 Docker，以便拉取私有镜像。**

由于 GitHub Packages（GHCR）中的镜像是私有的（除非你主动设为公开），你需要通过身份验证才能拉取。为此，请先创建一个 **Personal Access Token**，并确保包含以下权限：

- `repo`（全部勾选）
- `write:packages`
- `read:packages`

![screenshot personal access token creation page with boxes for repo (all), write:packages, and read:packages checked](https://user-images.githubusercontent.com/3250463/219254714-82bb1da5-33b1-491b-97c0-b25f51494f6a.png)

### 登录 GHCR

1. 打开命令行。
2. 运行以下命令登录 GitHub Container Registry：

   ```bash
   docker login ghcr.io -u YOUR_GITHUB_USERNAME
   ```

3. 将 `YOUR_GITHUB_USERNAME` 替换为你的实际 GitHub 用户名。
4. 当系统提示输入密码时，**粘贴你刚刚创建的 Personal Access Token**（不是你的 GitHub 密码！）。
5. 按 **Enter**。

如果一切顺利 :crossed_fingers:，你应该会在终端看到：

```
Login Succeeded
```

### :keyboard: 实操环节：拉取你的镜像

1. 获取镜像的 `pull` 命令：
   - 🔥 **提示**：你可以这样找到它：进入你仓库的 **Code** 标签页，在仓库描述下方的导航栏中，点击 **Packages** 链接。 
        ![GitHub Packages 页面上的 pull 命令截图](https://user-images.githubusercontent.com/3250463/219254981-9ff949fa-4d01-46e3-9e3d-b8ce3710c2a9.png)
   - 或者，直接访问以下链接（记得替换 `YOURNAME` 和 `REPONAME`）：
     ```
     https://github.com/users/YOURNAME/packages?repo_name=REPONAME
     ```
     然后点击你的包名称。

2. 将 `YOURNAME` 替换为你的 GitHub 用户名。
3. 将 `TAG` 替换为实际的镜像标签。

3. 最终命令看起来会像这样：

   ```bash
   docker pull ghcr.io/YOURNAME/publish-packages/game:sha-abc123
   ```

4. 将命令粘贴到终端并按 **Enter** 执行。
5. 如果成功，你会看到类似以下的输出：

   ```
   Status: Downloaded newer image for ghcr.io/YOURNAME/publish-packages/game:sha-abc123
   ```

   ![成功拉取 Docker 镜像的终端输出截图](https://user-images.githubusercontent.com/3250463/219255178-3c943a6f-6c15-4f59-9002-228249b1c469.png)

> 💡 **注意**：这一步无法由系统自动验证，请确认你已成功拉取镜像后，继续进入下一步。
