# 在MAC环境中安装LLaMA Factory

[TOC]

LLaMA Factory是一款对大模型进行微调的开源框架。

本文简单介绍如何在Mac操作系统中安装 LLaMA Factory。

## 1、项目下载


官方项目地址: 

> https://github.com/hiyouga/LLaMA-Factory



使用git下载代码:

```sh
mkdir -p ~/GITHUB_ALL

cd ~/GITHUB_ALL

# 只下载1个深度
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git

```


## 2、配置Python环境

首先通过conda创建一个Python环境。

```sh
# 创建一个名为 llama310 的环境
conda create -y -n llama310 python=3.10

# 激活环境
conda activate llama310

# 测试
python --version
# Python 3.10.18

```

如果没有 conda, 可以参考前面的文章:


> [适合新手的Python与神经网络学习日记](https://blog.csdn.net/renfufei/article/details/150343467)



## 3、安装依赖



```sh

cd LLaMA-Factory

# 激活环境
conda activate llama310

# 在当前目录下以开发模式安装项目, 
# 并安装 setup.py 中定义的依赖组 [torch,metrics]
pip install -e ".[torch,metrics]" --no-build-isolation

```

## 4、验证安装



需要先激活之前安装 LLaMA-Factory 的Python环境。


```sh

# 进入工作目录
# cd LLaMA-Factory

# 激活环境
conda activate llama310

# 查看版本号
llamafactory-cli version

```


需要等一会儿, 会展示类似下面这样的信息:


```yml
# 显示的消息
----------------------------------------------------------
| Welcome to LLaMA Factory, version 0.9.4.dev0           |
|                                                        |
| Project page: https://github.com/hiyouga/LLaMA-Factory |
----------------------------------------------------------

```

只要不报错, 就证明安装完成。

提示: 

> 如果有 shell 环境下的 prox-y 配置, 需要开个新shell环境，或者取消配置。
> 可参考: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/8026
> 或者: https://blog.halfcoffee.com/docs/ai/llamafactory


## 5、 查看帮助信息

```sh

# 进入工作目录
# cd LLaMA-Factory

# 查看帮助信息
llamafactory-cli

```

需要等一会儿, 会展示类似下面这样的信息:


```yml
----------------------------------------------------------------------
| Usage:                                                             |
|   llamafactory-cli api -h: launch an OpenAI-style API server       |
|   llamafactory-cli chat -h: launch a chat interface in CLI         |
|   llamafactory-cli eval -h: evaluate models                        |
|   llamafactory-cli export -h: merge LoRA adapters and export model |
|   llamafactory-cli train -h: train models                          |
|   llamafactory-cli webchat -h: launch a chat interface in Web UI   |
|   llamafactory-cli webui: launch LlamaBoard                        |
|   llamafactory-cli version: show version info                      |
----------------------------------------------------------------------
```

这里列出了常用的命令用法, 可以简单了解一下.



## 6、开启web管理界面


使用如下命令:

```sh

# 进入工作目录
# cd LLaMA-Factory

# 启动Web管理控制台
llamafactory-cli webui
```

启动完成之后, 会自动打开浏览器的标签页, 类似于这样的地址:

> http://localhost:7860/


在管理控制台界面中, 可以调整各种需要的配置, 以及执行各种操作。

比如最简单的, 调整界面语言(Language)为 中文(`zh`).


## 7、 小结




