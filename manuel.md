# Commandes

## Mac os

复制文件地址 : [OPTION] + [⌘ Command] + C

自由截图 : [⇧ Shift] + [⌘ Command] + 4 （点击截图可复制）

TextEdit 进入纯文本编辑模式 : [⇧ Shift]  + [⌘ Command] + T

光标选择文本 : 单击想选中文本的起始位置，按[⇧ Shift]不动，单击想选中的结束位置

### Terminal

textutil -convert txt [file/name]





## GCP

gsutil cp -r [local/file/path] [remote/file/path]

Local to Dataproc : `gs://lranalytics-frds-endpoint-select-vm/660531/LIUXIN/`

Dataproc to Jupyter: `gs://lranalytics-eu-660531-aqim-coderepo/660531/LIUXIN/`

`-m`: en parallèle, plus rapide

`-r`: répertoire



## Python

显示所有列

pd.set_option('display.max_columns', None)

显示所有行

pd.set_option('display.max_rows', None)

不截断每列的内容

pd.set_option('display.max_colwidth', None)



## Markdown

换行：在行尾加两个空格



## Git

### 初始化

`git init `

`git add . `

`git commit -m "初始化提交：添加所有文件"`

`git remote add origin https://github.com/Liuxin-ylx/Internship_2025_DSFR_Dataquality.git `

`git branch -M main`

`git push -u origin main`

### 更新代码

1. 确保在 main 分支：  `git checkout main`

2. 从 main 创建一个新分支保存第二个版本：

   `git checkout -b v2`

​	`git add .`

​	`git commit -m "第二个版本"`

​	`git push origin v2`

​	输用户名和密码的时候，密码输入创建的personal token

3. 合并main和branch

   1. 强制push覆盖远程：`git push origin main --force`

   2. 先pull，再rebase：

      `git pull origin main --rebase`
      `git push origin main`

      > 如果遇到冲突，查看冲突的文件：`git status`
      >
      > 手动编辑文件，把冲突部分整理好，只保留需要的最终版本：
      >
      > <<<<<< HEAD
      >
      > #来自远程 GitHub 的版本
      >
      > =======
      >
      > #你本地的版本
      >
      > 6c68a19 (初始化提交：添加所有文件)
      >
      > 修改完冲突的所有文件之后：`git add .`， 再继续rebase