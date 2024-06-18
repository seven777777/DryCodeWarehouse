# 业务代码干货宝典

该书旨在协助记忆日常业务开发过程中一些常用的方法代码，方便在实际开发时遇到能够快速的找到并使用。

### Tip

node 版本：10
npm 版本：6

#### 技术栈

本书开发技术栈：GitBook + Typora + Git

> -   Typora 下载地址：https://typora.io/
> -   Git 下载地址：https://git-scm.com/downloads

#### 项目相关语法

-   `npm install -g gitbook-cli` 安装 gitbook

-   `gitbook init` 初始化
    初始化后会生成两个文件 ——README.md  和  SUMMARY.md

    在 SUMMARY.md 中修改文件目录后，重新执行`gitbook init`，会根据 SUMMARY.md 文件中描述的目录和文件,创建相应的文件夹

    ```
    // SUMMARY.md 示例
    * [前言](README.md)
    * [第一章](Chapter1/README.md)
    	* [第1节：test](Chapter1/test.md)
    ```

-   `gitbook serve` 预览书籍

    默认端口是：4000

    可以指定端口 `gitbook serve --port xxxx `

    默认会输出到`/_book`文件夹下，可指定输出文件夹 `gitbook serve [书籍路径] [输出路径]`

-   `gitbook build` 创建书籍

    默认会输出到`/_book`文件夹下，可指定输出文件夹 `gitbook build [书籍路径] [输出路径]`

    因为我希望能够在 github 上生成预览页面，因此，根据 github page 的设定，此处使用`gitbook build ./ ./docs` 设置输出文件夹名为`docs`

    #### 其他

    1. 生成  PDF 格式的电子书

        ```
        gitbook pdf ./ ./mybook.pdf
        ```

    2. 生成 epub 格式的电子书

        ```
        gitbook epub ./ ./mybook.epub
        ```

    3. 生成 mobi 格式的电子书

        ```
        gitbook mobi ./ ./mybook.mobi
        ```
