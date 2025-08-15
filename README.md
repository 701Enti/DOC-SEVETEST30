# 本地离线访问文档 - 如何在本地/无网络情况下浏览文档

## 方法 1 - 使用 SEVETEST30 仓库

- **前提**: 在之前已经 clone/下载了 SEVETEST30 仓库,并且确定它是最新的
- **浏览文档**:
  - 进入该仓库文件夹目录,打开根目录中的 index.html 文件
  - 这将在浏览器显示文档,这无需网络连接

## 方法 2 - 使用本仓库

- **前提**: 在之前已经 clone/下载了文档仓库,并且确定它是最新的
- **浏览文档**:
  - 进入该仓库文件夹目录,打开./doxygen/html/index.html 文件
  - 这将在浏览器显示文档,这无需网络连接

# 云端部署相关

## 如何在指定域名下上线新分支的文档(利用 GitHub Pages,公共仓库免费托管)

- **例如需上线 SEVETEST30 仓库的关键分支 K 分支对应文档**:
  (需要 SEVETEST30 团队通过 pull&request 才可完成部署)

  - 1.进入 SEVETEST30 本地仓库目录，并确保处于个人分支最新版本
  - 2.进入./docs/official/repo_doc
  - 3.在此目录下,安装文档仓库的 K 分支作为个人分支的子模块
    `git submodule add -b K https://github.com/701Enti/DOC-SEVETEST30.git`
    如果报错"Invalid branch name":
    这可能是因为文档仓库未建立需要的文档分支,一般只有关键分支如 master 会被考虑自动文档支持
    当然,如果您希望自己的分支像关键分支一样可云端部署文档,您可以在本地运行 Doxygen 生成文档
    并推送到 SEVETEST30 文档仓库与个人分支同名的分支,之后可联系 SEVETEST30 团队协商,他们管理文档的云端部署
    详情请见 SEVETEST30 仓库 README-文档相关,如果确实是关键分支,可以更改工作流配置并触发文档同步,之后再次执行
  - 4.同步子模块代码
    `git submodule update --init --recursive`
  - 5.推送更改到个人分支,并发起个人分支到 master 分支的 pull&request
  - 6.需要 SEVETEST30 团队通过 pull&request 才可完成部署

- **例如需上线 SEVETEST30 仓库的个人分支 A 对应文档**:
  (需要 SEVETEST30 团队通过 pull&request 才可完成部署)
  - 1.进入 SEVETEST30 本地仓库目录，并确保处于个人分支最新版本
  - 2.进入./docs/personal/repo_doc
  - 3.在此目录下,安装文档仓库的 A 分支作为个人分支的子模块
    `git submodule add -b A https://github.com/701Enti/DOC-SEVETEST30.git`
    如果报错"Invalid branch name":
    这可能是因为文档仓库未建立需要的文档分支,联系申请者在本地运行 Doxygen 生成文档
    并推送到 SEVETEST30 文档仓库与个人分支 A 同名的分支,之后可联系 SEVETEST30 团队协商,他们管理文档的云端部署
    详情请见 SEVETEST30 仓库 README-文档相关
  - 4.同步子模块代码
    `git submodule update --init --recursive`
  - 5.推送更改到个人分支,并发起个人分支到 master 分支的 pull&request
  - 6.需要 SEVETEST30 团队通过 pull&request 才可完成部署
