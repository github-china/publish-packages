<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 2: 添加 Dockerfile

_你已经成功创建了用于发布的 workflow! :tada:_

接下来，我们将在 `cd` 分支下添加 `Dockerfile` 文件，用于构建最终的 Docker 镜像。如果你第一次接触 Dockerfile 可以[深入了解 Dockerfile 的语法和用法](https://docs.docker.com/engine/reference/builder/)。

### :keyboard: 实操环节：添加 Dockerfile

1. 在 `cd` 分支的根目录下创建名为 `Dockerfile` 的文件，并写入以下内容：

   ```dockerfile
   FROM nginx:1.24-alpine
   COPY . /usr/share/nginx/html
   ```

   我来解释下：
   - 使用 `nginx:1.24-alpine` 作为基础镜像。
   - 将当前项目目录下的所有文件复制到 Nginx 的默认网页目录中。

2. 提交你的更改。
3. 等待约 20 秒，然后刷新本页面。[GitHub Actions](https://docs.github.com/en/actions) 会自动检测到新文件，并推进到下一步。