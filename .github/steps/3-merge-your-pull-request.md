<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 3: 合并你的更改

_现在，让我们正式发布吧! :heart:_

你已经完成了所有准备工作，现在可以将 `cd` 分支中的更改合并到 `main` 分支了。一旦合并，GitHub Actions 会自动触发工作流，构建并把 Docker 镜像发布到 GitHub Packages。

### :keyboard: 实操环节: 合并你的更改

1. 将 `cd` 分支的更改合并到 `main` 分支：
    - 如果你在第 1 步中已经创建了拉取请求（PR），只需打开该 PR，点击 **Merge pull request**（合并拉取请求）按钮即可。
    - 如果尚未创建 PR，现在可以按第 1 步中的说明新建一个：进入 **Pull Requests** 标签页，点击 **New pull request**，设置 `base: main`、`compare: cd`，然后创建并合并它。
2. （可选）合并完成后，你可以删除 `cd` 分支以保持仓库整洁。
3. 等待约 20 秒，然后刷新本页面。[GitHub Actions](https://docs.github.com/en/actions) 会自动检测到 `main` 分支的更新，并进入下一步。