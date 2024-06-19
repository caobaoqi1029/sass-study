# 一、Hello Django

- https://www.djangoproject.com/start/overview/

Django 是一个针对完美主义者的 Web 框架，使得构建更好的 Web 应用程序更加容易、更快捷、代码更少。 是一个高级的 Python 网络框架，鼓励快速开发和清晰、实用的设计。由经验丰富的开发人员开发，它可以减轻许多 Web 开发的麻烦，因此您可以专注于编写应用程序，而不需要重新发明轮子。

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191516708.png)

------

- Django 旨在帮助开发人员尽快将应用程序从概念到完成。
- Django 包含数十个附加功能，您可以使用它来处理常见的 Web 开发任务。Django 负责用户身份验证、内容管理、站点地图、RSS 提要和更多任务——开箱即用。
- Django 非常重视安全性，并帮助开发人员避免许多常见的安全错误，例如 SQL 注入、跨站点脚本、跨站点请求伪造和点击劫持。其用户身份验证系统提供了一种管理用户帐户和密码的安全方式。
- 地球上一些最繁忙的站点使用 Django 快速灵活扩展的能力来满足最繁重的流量需求。
- 公司、组织和政府已经使用 Django 来构建各种各样的东西——从内容管理系统到社交网络再到科学计算平台。

# 二、Python venv

虚拟环境 venv是（主要的特性）：

- 用来包含支持一个项目（库或应用程序）所需的特定 Python 解释器、软件库和二进制文件。 它们在默认情况下与其他虚拟环境中的软件以及操作系统中安装的 Python 解释器和库保持隔离。
- 包含在一个目录中，根据惯例被命名为项目目录下的`venv` 或 `.venv`，或是有许多虚拟环境的容器目录下，如 `~/.virtualenvs`。
- 不可签入 Git 等源代码控制系统。
- 被视为是可丢弃性的 —— 应当能够简单地删除并从头开始重建。 你不应在虚拟环境中放置任何项目代码。
- 不被视为是可移动或可复制的 —— 你只能在目标位置重建相同的环境。

## 2.1 venv

> https://docs.python.org/zh-cn/3/library/venv.html#

`venv` 模块支持创建轻量的“虚拟环境”，每个虚拟环境将拥有它们自己独立的安装在其 [`site`](https://docs.python.org/zh-cn/3/library/site.html#module-site) 目录中的 Python 软件包集合。 虚拟环境是在现有的 Python 安装版基础之上创建的，这被称为虚拟环境的“基础”Python，并且还可选择与基础环境中的软件包隔离开来，这样只有在虚拟环境中显式安装的软件包才是可用的。

**当在虚拟环境中使用时，常见安装工具如 \**[\*\*pip\*\*](https://pypi.org/project/pip/)\** 将把 Python 软件包安装到虚拟环境而无需显式地指明这一点。**

## 2.2 使用 pip 和 venv 在虚拟环境中安装软件包

> https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments

本指南讨论如何使用标准库的虚拟环境工具 venv 创建和激活虚拟环境，并安装软件包。本指南包括如何

- 创建并激活虚拟环境
- 使用 `pip` 命令将软件包安装到虚拟环境中
- 使用和创建 requirements.txt

前置要求：

- 本指南适用于受支持的 Python 版本，目前为 3.8 及更高版本
- 本指南的前提条件是，您使用的是从 < https://www.python.org/downloads/> 获取的官方 Python 版本。如果您使用操作系统的软件包管理器安装 Python，请确保已安装 Python 后再执行这些步骤

### 2.2.1 创建并激活虚拟环境

1. 创建新的虚拟环境

venv（适用于 Python 3）允许你管理不同项目的独立软件包安装。它可以创建一个 "虚拟 "隔离的 Python 安装。当您切换项目时，可以创建一个与其他虚拟环境隔离的新虚拟环境。虚拟环境让您受益匪浅，因为软件包可以放心地安装，不会干扰其他项目的环境。

**建议在使用第三方软件包时使用虚拟环境。**

要创建虚拟环境，请进入项目目录并运行以下命令。这将在名为 `.venv` 的本地文件夹中创建一个新的虚拟环境：

```Bash
py -m venv .venv
```

第二个参数是创建虚拟环境的位置。一般来说，只需在项目中创建并调用 `.venv` 即可。

`venv` will create a virtual Python installation in the `.venv` folder. `venv` 将在 `.venv` 文件夹中创建一个虚拟 Python 安装。

**您应该使用 \**\*\*`.gitignore`\*\**\* 或类似方法将虚拟环境目录从版本控制系统中排除。**

在开始安装或使用虚拟环境中的软件包之前，你需要 `activate` 它。激活虚拟环境将把特定于虚拟环境的 `python` 和 `pip` 可执行文件放入 shell 的 `PATH` .NET 中。

```Bash
.venv\Scripts\activate
```

要确认虚拟环境已激活，请检查 Python 解释器的位置：

```Bash
where python
```

当虚拟环境处于活动状态时，上述命令将输出包括 `.venv` 目录在内的文件路径，以下面的内容结尾：

```Bash
.venv\Scripts\python
```

当虚拟环境被激活时，pip 会将软件包安装到该特定环境中。这样，您就可以在 Python 应用程序中导入和使用软件包。

2. 停用虚拟环境

如果要切换项目或离开虚拟环境， `deactivate` 环境：

```Bash
deactivate
```

**关闭 shell 会停用虚拟环境。如果您打开一个新的 shell 窗口并想使用虚拟环境，请重新激活它。**

3. 重新激活虚拟环境

如果要重新激活现有虚拟环境，请遵循与激活虚拟环境相同的说明。无需创建新的虚拟环境。

### 2.2.2 pip

pip 是 Python 的参考软件包管理器。它用于在虚拟环境中安装和更新软件包。Windows 的 Python 安装程序包含 pip。运行以下命令可确保 pip 是最新的：

```Bash
py -m pip install --upgrade pip
py -m pip --version
```

之后，您就可以使用最新版本的 pip 了：

```Bash
pip 24.0 from C:\Users\2024c\AppData\Local\Programs\Python\Python312\Lib\site-packages\pip (python 3.12)
```

4. 使用 pip 安装软件包

激活虚拟环境后，就可以安装软件包了。使用 `pip install` 命令安装软件包。例如从 Python 软件包索引（PyPI）中安装 Requests 库：

```Bash
py -m pip install requests
```

pip 会下载 requests 及其所有依赖项并进行安装：

```Bash
Collecting requests
  Using cached requests-2.18.4-py2.py3-none-any.whl
Collecting chardet<3.1.0,>=3.0.2 (from requests)
  Using cached chardet-3.0.4-py2.py3-none-any.whl
Collecting urllib3<1.23,>=1.21.1 (from requests)
  Using cached urllib3-1.22-py2.py3-none-any.whl
Collecting certifi>=2017.4.17 (from requests)
  Using cached certifi-2017.7.27.1-py2.py3-none-any.whl
Collecting idna<2.7,>=2.5 (from requests)
  Using cached idna-2.6-py2.py3-none-any.whl
Installing collected packages: chardet, urllib3, certifi, idna, requests
Successfully installed certifi-2017.7.27.1 chardet-3.0.4 idna-2.6 requests-2.18.4 urllib3-1.22
```

5. 安装特定版本的软件包

pip 允许你使用版本说明符指定要安装的软件包版本。例如，要安装特定版本的 `requests`

```Bash
py -m pip install "requests==2.18.4"
```

安装最新 `2.x` 版本的 requests：

```Bash
py -m pip install "requests>=2.0.0,<3.0.0"
```

要安装预发布版本的软件包，请使用 `--pre` 标记：

```Bash
py -m pip install --pre requests
```

6. 安装额外功能

有些软件包有可选的附加功能。你可以在括号中指定附加功能，让 pip 安装这些附加功能：

```Bash
py -m pip install "requests[security]"
```

7. 从源代码安装软件包

pip 可以直接从源代码中安装软件包。例如，安装 `google-auth` 目录中的源代码：

```Bash
cd google-auth
py -m pip install .
```

此外，pip 可以在开发模式下从源代码安装软件包，这意味着源代码目录的更改会立即影响已安装的软件包，而无需重新安装：

```Bash
py -m pip install --editable .
```

8. 从版本控制系统安装

pip 可以直接从版本控制系统安装软件包。例如，你可以直接从 git 仓库安装：

```Bash
google-auth @ git+https://github.com/GoogleCloudPlatform/google-auth-library-python.git
```

9. 从本地安装

如果本地有分发包的存档副本（zip、wheel 或 tar 文件），可以直接用 pip 安装：

```Bash
py -m pip install --no-index --find-links=/local/dir/ requests
```

如果要在连接性有限的系统上安装软件包，或者要严格控制分发软件包的来源，这一点非常有用。

10. 升级软件包

pip 可以使用 `--upgrade` 标志就地升级软件包。例如，安装最新版本的 `requests` 及其所有依赖包：

```Bash
py -m pip install --upgrade requests
```

### 2.2.3 使用和创建 requirements.txt

pip 允许你在需求文件中声明所有依赖关系，而不是单独安装软件包。例如，您可以创建一个 `requirements.txt` 文件，其中包含

```Bash
requests==2.18.4
google-auth==1.1.0
```

然后使用 `-r` 标志告诉 pip 安装该文件中的所有软件包：

```Bash
py -m pip install -r requirements.txt
```

### 2.2.4 freezing dep

Pip 可以使用 `freeze` 命令导出所有已安装软件包及其版本的列表：

```Bash
py -m pip freeze
```

将输出软件包说明符列表，例如

```Bash
cachetools==2.0.1
certifi==2017.7.27.1
chardet==3.0.4
google-auth==1.1.1
idna==2.6
pyasn1==0.3.6
pyasn1-modules==0.1.4
requests==2.18.4
rsa==3.4.2
six==1.11.0
urllib3==1.22
```

`pip freeze > requirements.txt` 命令可用于创建 requirements 文件，该文件可重新创建环境中安装的所有软件包的准确版本。

# 三、项目搭建

本节的主要目的是通过 PyCharm 使用 venv 搭建一个 Django 初始化项目，便于后续开发

## 3.1创建项目

![202406191516251](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191516251.png)

------

**Python version 选项用于指定 venv 中 python 的基础版本，默认为当前 path 中的 version**

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517163.png)

默认创建好的项目应只包含一个 .venv 目录

> 使用 PyCharm 内终端会自动激活 venv 环境，具体表现为 命令前有一个`(.venv)`

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517377.png)

当前项目依赖仅包含 pip

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517862.png)

我们可以通过 `python.exe -m pip install --upgrade pip` 更新下 pip 版本

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517802.png)

## 3.2 通过 requirements 安装 django

```Bash
 pip freeze > requirements.txt
```

在生成的 `requirements.txt` 文件中添加

```Bash
Django>=5.0,<5.1
```

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517071.png)

```Bash
pip install -r requirements.txt 
```

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191517672.png)

## 3.3 初始化 Django 项目

```Bash
mkdir src
cd src
django-admin startproject home .
```

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191518132.png)

## 3.4 Django 启动

```Python
py manage.py runserver
```

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191518402.png)

![img](https://2024-cbq-1311841992.cos.ap-beijing.myqcloud.com/picgo/202406191518906.png)
