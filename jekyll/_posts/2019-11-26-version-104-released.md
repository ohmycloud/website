---
title: "1.0.4 版本现已发布！"
author: Nim 开发团队
excerpt: "Nim 团队很高兴为大家带来 1.0.4 版本发布的消息！这是我们在 Nim 1.0.0 之后发布的第二个补丁版本。"
---
> 以下由中文社区翻译，能力有限，如有翻译错误，欢迎加入 QQ 群指正！

Nim 团队很高兴为大家带来 1.0.4 版本发布的消息，
这是我们在 Nim 1.0.0 之后发布的第二个补丁版本。

想要了解更多关于 1.0.0 版本的细节，可以查看我们两个月前
[版本发布说明](/blog/2019/09/23/version-100-released.html)。

距离前一个版本的发布尽管只是过去了一个月的时间，
但这次的版本已经包含了超过 [70 次新的提交](https://github.com/nim-lang/Nim/compare/v1.0.2...v1.0.4),
新修复了 20 个问题，
让我们的 1.0 版本变成了更好的样子。


## 安装 1.0.4

如果你已经用 ``choosenim`` 安装了之前版本的 Nim ，
升级到 Nim 的 1.0.4 版本会非常简单:

```bash
$ choosenim update stable
```

如果你还没有安装 ``choosenim`` ，
你可以通过
[这些说明](https://github.com/dom96/choosenim) 来下载和安装 ``choosenim``，
当然你也可以按照我们的
[安装](/install.html) 页面直接安装。


## 更新日志

你可以
[在我们的 GitHub 仓库中](https://github.com/nim-lang/Nim/blob/version-1-0/changelogs/changelog_1_0_4.md)
查阅此版本的变更日志以及 Nim 的其余源码。

---
附《更新日志》
## 语言层面的变更

* 模仿早期版本的 Nim ，在运行时取消了对无符号整数转换的检查。
文档中已针对这一改进做出了说明。查看 [https://github.com/nim-lang/RFCs/issues/175]() 了解更多细节 (#12688)
* 添加了 `or detectOs(Manjaro)`，这样当检测到系统为 Manjaro 时，调用原生的包管理器会使用 `pacman` 进行包管理 ([#12587](https://github.com/nim-lang/Nim/pull/12587))
* `--os:ios` 编译指令现在也代表了 macosx ([#12585](https://github.com/nim-lang/Nim/pull/12585))
* 导出了 nim.cfg 解析器，现在其他工具也可以调用 `readConfigFile` 了 ([#12602](https://github.com/nim-lang/Nim/pull/12602
))

## BUG 修复

* 修复了“在 OSX 上多次调用后，`gorgeEx()` 失败”的问题 ([#12337](https://github.com/nim-lang/Nim/issues/12337))
* 优化和加强了 posix 模块 （[#10723](https://github.com/nim-lang/Nim/issues/10723)）
* 修复了 “Nim 的语法检查 允许使用 `gorgeEx()`，但不允许 `writeFile()`”的问题，现在这两个都被提示 *don't run staticExec for 'nim suggest* 了 ([#12491](https://github.com/nim-lang/Nim/issues/12491))
