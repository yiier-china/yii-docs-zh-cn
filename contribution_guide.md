# 贡献手册 Contrubition Guide



## 目录 Table Of Content

* [git 操作流程](#git-workflow)

- [贡献流程](#workflow)

- [注意事项](precaution)



## Git 操作流程 <a name="git-workflow">

**准备工作**

1. fork项目

2. 把fork后的项目(也就是你自己github名下的仓库)`clone`到本地

3. 在命令行运行 `git branch editing`来创建一个新分支，分支名是`editing`，你也可以用其它任何自己命名的名字

4. 运行 `git checkout editing` 来切换到新分支

5. 添加本项目的远端库，命名为`upstream`（也可以是其他名字），用来获取更新。

   * 在文档库的目录内，运行`git remote add upstream https://github.com/yiier-china/yii-docs-zh-cn.git` 把本项目文档库添加为远端库

     

以上步骤是一个初始化流程，只需要做一遍就行，之后请一直在`temp`（或其他名字）分支进行修改。



**每次翻译或校对前**

6. 在本地目录内，运行`git remote update`更新两库 
7. 在本地目录内，运行`git fetch upstream master`拉取两库的更新到本地 
8. 在本地目录内，使用`git checkout editing`切换回你的日常分支后，运行 `git rebase upstream/master`将两库的更新合并到你的分支



> 如果修改过程中我们的仓库有了更新，在对应的库目录下重复6、7、8步即可。 也可以简写为`git pull --rebase upstream master` 一条命令。或者你用SourceTree等GUI的话，在`push`面板下勾选用变基替代合并。也可以起到相同的作用，巧用变基，可以避免不必要的合并。



9. 修改之后，首先 Push 到你的库，然后登录 GitHub，在你的库的首页可以看到一个 pull request 按钮，点击它，填写一些说明信息，然后提交即可。

> 如果没有直接修改权限，你需要创建 Pull Request 简称 PR。最好可以把相关PR都挂在同一个 issue 之下，便于交流。 如果你翻译地较多，在群里吱一声，就可以提升为写权限，这样就可以直接 push 了，即使是有权限也建议使用 PR 处理 大规模多次零散的翻译提交，这样管理和沟通都会方便。对 open 的 PR 所在的 branch（分支）进行多次提及。




参与项目的流程如下

**翻译流程**：认领 → 翻译 → 建Pull Request（简称PR） / 直接提交 → 等待官方合并或其他评论

**校对流程**：看文档 → 发现不顺不对等的地方 → 点击Edit修改 → PR提交 





## 注意事项<a name="precaution">



* 除非紧贴标点符号，否则`英文单词/数字`与`中文`之间应加一个空格。如：`我们说 Yii 3.0 而非Yii3.

* 可以翻译且易于理解的术语，尽量用翻译后的形式，除非无法翻译或英文已经约定俗成，如：`Cookie/Session`。前人已经翻译的术语，请参见[术语表（Glossary）](glossary.md)。如果表中没有请添加您自己的翻译。如果对已有的术语翻译存在质疑，可以创建issue，或者在 QQ 群里沟通。总之，尽量避免“同词不同译”的发生。

* 若原文中包含`*斜体*`，一律改为`**粗体**`：原因是中文是方块字，汉字本就没有倾斜风格，而雅黑等主流中文字体的倾斜效果都处理得不好，会影响阅读体验。

* 如果是原文中的URL是维基百科或 PHP 手册，且提供了相应的中文翻译，我们最好把 URL 改为中文版本页面的 URL。

  如果没有，则最好注明**英文**字样。

  比如：

  [Composer 文档（英文）](https://getcomposer.org/doc/04-schema.md#autoload)（[中文汉化版本](https://github.com/5-say/composer-doc-cn/blob/master/cn-introduction/04-schema.md#autoload)）

* 注意保留 Markdown 语法及官方 apidoc 扩展所需特殊符号。
