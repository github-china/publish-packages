<!--
  <<< Author notes: Step 5 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 5: 运行你的镜像

_干得漂亮，你已经成功拉取了自己的 Docker 镜像啦! :relaxed:_

接下来，我们来运行它看看效果。

### :keyboard: 实操环节：运行你的镜像

1. 先查看一下你本地的镜像信息，输入命令：

   ```bash
   docker image ls
   ```

   ![Docker image ls 命令输出示例，展示了镜像列表、REPOSITORY、TAG 和 docker URL](https://i.imgur.com/UAwRXiq.png)<!-- This screenshot should be changed. -->
2. 使用以下命令，从你的镜像启动一个容器：

   ```bash
   docker run -dp 8080:80 --rm <YOUR_IMAGE_NAME:TAG>
   ```
3. 将命令中的 `YOUR_IMAGE_NAME` 替换为你实际的镜像名称（`REPOSITORY` 那列）。
4. 将 `TAG` 替换为对应的镜像标签（`TAG` 列中的值）。
5. 按下 **Enter** 键执行命令。
6. 如果一切正常，你会在终端中看到一串哈希值输出。
7. （可选）打开浏览器访问 [localhost:8080](http://localhost:8080)，就能看到你刚刚创建的页面啦。
8. *这一环节系统无法自动验证，请直接继续下一步。*