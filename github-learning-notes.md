# GitHub 学习记录

这份文档整理了本次从零开始学习 Git 和 GitHub 的过程，方便之后复习。

## 1. Git 和 GitHub 的关系

Git 是本地版本管理工具，用来记录文件每一次变化。

GitHub 是放在网上的代码仓库，可以保存、查看和分享 Git 项目。

简单理解：

- Commit：在本地保存一次版本
- Push：把本地版本上传到 GitHub
- Pull：从 GitHub 拉取最新版本到本地

## 2. 初始化本地 Git 项目

在项目目录里执行初始化后，这个文件夹就会变成 Git 项目。

本次项目目录是：

```text
/Users/mark/Documents/ChatGPT/mark_git
```

初始化后会出现一个隐藏目录：

```text
.git
```

它保存 Git 的版本记录和仓库信息。

## 3. README.md 的作用

`README.md` 是项目说明书。

GitHub 仓库首页会默认展示它的内容。

通常可以写：

- 项目是做什么的
- 怎么安装和运行
- 文件目录说明
- 使用注意事项

## 4. .gitignore 的作用

`.gitignore` 用来告诉 Git：哪些文件不要提交到仓库。

常见不提交的内容：

- 系统文件，例如 `.DS_Store`
- 临时文件，例如 `tmp/`
- 依赖目录，例如 `node_modules/`
- 本地配置，例如 `.env`

本次新增了 `.gitignore`，并提交到了 GitHub。

## 5. 提交和推送

一次完整上传通常分三步：

```bash
git add 文件名
git commit -m "提交说明"
git push
```

含义：

- `git add`：选择要提交的文件
- `git commit`：在本地保存一次版本
- `git push`：上传到 GitHub

在 VS Code 里也可以完成同样操作：

1. 打开 Source Control
2. 输入提交说明
3. 点击 Commit
4. 点击 Sync Changes 或 Push

## 6. main 分支

`main` 通常是主分支。

一般用来保存稳定版本。

本次项目最开始在 `main` 上创建了：

- `README.md`
- `.gitignore`
- 测试文件

## 7. feature_1 分支

新功能或测试内容可以放到新分支里。

本次创建了：

```text
feature_1
```

刚创建分支时，它会复制 `main` 当时的全部内容。

之后两个分支会分开变化：

- `feature_1` 上的修改不会自动影响 `main`
- `main` 后续新增内容也不会自动同步到 `feature_1`

## 8. 在分支上新增文件

本次在 `feature_1` 上新增了：

```text
test_feature_1
```

内容包括：

```text
feature_1 test file
新分支测试文件
```

之后提交并推送到了 GitHub 的 `feature_1` 分支。

## 9. 查看 main 和 feature_1 的区别

GitHub 可以直接对比分支。

对比链接格式：

```text
https://github.com/用户名/仓库名/compare/main...feature_1
```

本项目的对比链接是：

```text
https://github.com/13603601431mayc-cell/mark_git/compare/main...feature_1
```

页面里：

- 绿色内容表示新增
- 红色内容表示删除
- `base: main` 表示目标分支
- `compare: feature_1` 表示拿来比较的分支

## 10. 合并分支

确认 `feature_1` 内容没问题后，可以合并到 `main`。

本次已经把 `feature_1` 合并到了 `main`，并推送到了 GitHub。

合并后，`main` 也拥有了：

- `test_feature_1`
- `test/test_text` 里的“鸭梨”

## 11. GitHub 页面常用入口

GitHub 仓库里常用的页面：

- Code：查看文件
- Commits：查看提交记录
- Branches：查看分支
- Pull requests：对比分支、合并代码
- Issues：记录问题和待办
- Actions：自动化任务
- Settings：仓库设置

## 12. 常用命令速查

查看当前状态：

```bash
git status
```

查看当前分支：

```bash
git branch --show-current
```

新建并切换分支：

```bash
git switch -c 分支名
```

切换到已有分支：

```bash
git switch 分支名
```

提交文件：

```bash
git add 文件名
git commit -m "提交说明"
```

推送到 GitHub：

```bash
git push
```

合并分支：

```bash
git switch main
git merge 分支名
git push
```

## 13. 本次学习结论

本次已经完成：

- 初始化 Git 项目
- 推送到 GitHub
- 新增 `.gitignore`
- 创建 `feature_1` 分支
- 在分支上新增和修改文件
- 对比 `main` 和 `feature_1`
- 把 `feature_1` 合并回 `main`
- 将合并结果推送到 GitHub

后续继续练习时，推荐流程是：

```text
新建分支 -> 修改文件 -> 提交 -> 推送 -> 对比 -> 合并回 main
```
