[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-f059dc9a6f8d3a56e377f745f24479a46679e63a5d9fe6f495e02850cd0d8118.svg)](https://classroom.github.com/online_ide?assignment_repo_id=6382484&assignment_repo_type=AssignmentRepo)
# 3-simplelayout-package

## 简介

- 本次作业将大家完成的数据生成器进行打包，可供 pip 进行安装，发布到 [PyPI](https://pypi.org/)。同时使用 Sphinx 构建文档，发布到 [Read the Docs](https://readthedocs.org/)。


>**Sphinx** is a powerful documentation generator that has many great features for writing technical documentation including:
>- Generate web pages, printable PDFs, documents for e-readers (ePub), and more all from the same sources
>- You can use reStructuredText or Markdown to write documentation
>- An extensive system of cross-referencing code and documentation
>- Syntax highlighted code samples
>- A vibrant ecosystem of first and third-party extensions

- Python 生态的文档大都以 Sphinx 进行发布，例如 [Python 自身的官方文档](https://docs.python.org/3/)、[Pytorch 文档](https://pytorch.org/docs/stable/index.html) 等等。

- [Read the Docs](https://readthedocs.org/) 是一个可以自动化托管 Sphinx 文档的网站。

- Read the Docs 有上手教程，[参考](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html)。

## 要求

- 将个人完成的 `2-simplelayout-generator` 项目中的 `simplelayout` 目录复制到本次作业的 `src` 目录下。
- 编写 `setup.py`
  - 参考[官方文档](https://docs.python.org/3/distributing/index.html#reading-the-python-packaging-user-guide)，与 [Packaging and distributing projects](https://packaging.python.org/guides/distributing-packages-using-setuptools/)，正确配置 `setuptools.setup()`，确保能被 `pip` 正确安装，要求
    - package 名称设置为 `simplelayout-github账号名`
    - 正确包含 `src/simplelayout` 这个 package
    - `install_requires` 包含 `simplelayout` 的相关依赖
    - 正确配置 `entry_points`，使命令 `simplelayout` 对应 `simplelayout/__main__.py` 中的 `main()` 函数
- 参考 [文档](https://packaging.python.org/guides/distributing-packages-using-setuptools/#packaging-your-project)，正确打包
- 参考 [文档](https://packaging.python.org/guides/distributing-packages-using-setuptools/#id77)，正确上传到 PyPI
- 根据[参考教程](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html)，创建 `docs` 目录，并创建 `Sphinx` 项目。
  - 在执行 `sphinx-quickstart` 时输入相关信息
  - Sphinx 默认使用 rst 格式（[reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) ）编写文档，可进行配置使用 [Markdown](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html#using-markdown-with-sphinx) 进行文档编写。
  - 选做：[参考](https://www.sphinx-doc.org/en/master/usage/extensions/napoleon.html) 配置 autodoc、napoleon 插件，自动生成 simplelayout 中的 docstring API。
  - 在本地生成正确的 Sphinx 文档
- 注册 [Read the Docs](https://readthedocs.org/)，将个人仓库中的文档正确托管
- 将个人项目 PyPI 仓库的链接、read the docs 链接以评论的方式发在 `Feedback` 上

## 注意

本次作业的在线测试分为以下部分：
1. 测试能否正确执行
  ```
  pip install .
  ```
  分值：1 分
1. 测试能否正确执行
  ```
  pip install .
  simplelayout -h
  ```
  分值：1 分

以上测试通过后，会在 `Feedback` 中打印相关信息（包括 PyPI 链接，生成图片），但不会对 `PyPI`、`Read the Docs` 自动测试