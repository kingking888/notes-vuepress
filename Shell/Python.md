# Python


[[toc]]




## Flag

> 由于`Python`是动态编译的语言，和`C`/`C++`、`Java`或者`Kotlin`等静态语言不同，它是在运行时一句一句代码地边编译边执行的，
> 而`Java`是提前将高级语言编译成了`JVM`字节码，运行时直接通过JVM和机器打交道，所以进行密集计算时运行速度远高于动态编译语言。
> 但是根据`二八定律`（帕累托法则），有`80%`的计算资源只被`20%`的程序所使用，因此在大部分情况下，
> 原生的`CPython`解释器已经足够满足日常编程，加上很多科学计算库底层都是`C`/`C++`写的，一般不会用`Python`做密集计算。


> 当你从官网下载并安装好`Python`后，就自带了一个`CPython`解释器，是使用最广的`Python`解释器，
> 我们在终端使用`python xxx.py`命令就是调用的`CPython`解释器。

> `PyPy`使用了`JIT`（即时编译）技术，混合了动态编译和静态编译的特性，仍然是一句一句编译源代码，
> 但是会将翻译过的代码缓存起来以降低性能损耗。相对于静态编译代码，即时编译的代码可以处理延迟绑定并增强安全性。

+ [https://github.com/python](https://github.com/python)
    + [https://www.python.org](https://www.python.org)
    + [https://docs.python.org/zh-cn](https://docs.python.org/zh-cn)
    + [https://www.python.org/ftp/python](https://www.python.org/ftp/python)
    + [http://npm.taobao.org/mirrors/python](http://npm.taobao.org/mirrors/python)

* [GO-Node-Python的简单性能比较](https://www.izhongxia.com/posts/64310.html)
* [内置异常和函数](https://lichangke.github.io/category/#python)
* [Python语言小册](https://python.fasionchan.com/zh_CN/latest/index.html)
* 最良心的 Python 教程 [https://github.com/TwoWater/Python](https://github.com/TwoWater/Python)
* [https://github.com/xxg1413/python](https://github.com/xxg1413/python)
* [https://github.com/yidao620c/python3-cookbook](https://github.com/yidao620c/python3-cookbook)
* [https://github.com/eastlakeside/interpy-zh](https://github.com/eastlakeside/interpy-zh)
* [https://github.com/cloga/scipy-lecture-notes_cn](https://github.com/cloga/scipy-lecture-notes_cn)
* [https://www.junmajinlong.com/python/index](https://www.junmajinlong.com/python/index)
* [https://zmister.com](https://zmister.com)
* [python3基础教程](https://morvanzhou.github.io/tutorials/python-basic/basic)
* Python中的设计模式和习惯用法的集合 [https://github.com/faif/python-patterns](https://github.com/faif/python-patterns)
* Python中文网 [https://www.cnpython.com](https://www.cnpython.com)


+ [https://github.com/vinta/awesome-python](https://github.com/vinta/awesome-python)
+ [python3 中执行系统命令](https://www.jianshu.com/p/a19de14c4b57)
+ [Python图像处理库—-Pillow](https://www.lizenghai.com/archives/17611.html)
+ [https://github.com/aio-libs](https://github.com/aio-libs)
+ [Python Selenium教程 - 猿人学Python](https://www.yuanrenxue.com/python-selenium)

- [https://github.com/Arronlong/py_scripts](https://github.com/Arronlong/py_scripts)



## 第三方库

+ [https://github.com/jobbole/awesome-python-cn](https://github.com/jobbole/awesome-python-cn)

- [https://github.com/topics/python](https://github.com/topics/python)
    - [https://github.com/ipython](https://github.com/ipython)
    - 用Python实现的所有算法 [https://github.com/TheAlgorithms/Python](https://github.com/TheAlgorithms/Python)
    - 纠正以前的控制台命令中的错误 [https://github.com/nvbn/thefuck](https://github.com/nvbn/thefuck)
    - 命令行HTTP客户端 [https://github.com/jakubroztocil/httpie](https://github.com/jakubroztocil/httpie)
- [https://github.com/topics/expect](https://github.com/topics/expect)
    - [https://www.nist.gov/services-resources/software/expect](https://www.nist.gov/services-resources/software/expect)
    - [https://github.com/clarkwang/sexpect](https://github.com/clarkwang/sexpect)
    - 自动化交互式 [https://github.com/pexpect/pexpect](https://github.com/pexpect/pexpect)
    - [https://github.com/pytest-dev/pytest](https://github.com/pytest-dev/pytest)
    - [https://github.com/jacebrowning/pytest-expecter](https://github.com/jacebrowning/pytest-expecter)
- [https://github.com/topics/ops](https://github.com/topics/ops)
- [https://github.com/topics/automation](https://github.com/topics/automation)
- [https://github.com/pyecharts/pyecharts](https://github.com/pyecharts/pyecharts)



## 安装新版

> 全部操作都在`root`用户下执行

### 安装编译相关工具

```bash
yum -y groupinstall "Development tools"
yum -y install zlib-devel bzip2-devel openssl-devel \
ncurses-devel sqlite-devel readline-devel tk-devel \
gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel
```

### 下载安装包解压

* 到官网复制最新版下载地址 https://www.python.org/downloads/release

```bash
wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tar.xz
# 解压
tar -xvJf Python-3.7.3.tar.xz
# 切换到解压目录
cd Python-3.7.3
```

### 编译安装

```bash
# 创建编译安装目录，并配置指定安装路径
mkdir /usr/local/python3 && ./configure --prefix=/usr/local/python3
# 编译安装并把安装日志保存下来
make && make install > install.log
```

### 创建软连接

```bash
ln -s /usr/local/python3/bin/python3 /bin/python3
ln -s /usr/local/python3/bin/pip3 /bin/pip3
```

### 验证是否成功

```bash
python3 -V && pip3 -V
```

### 安装后yum不能正常使用

- 把 `#!/usr/bin/python` 修改为 `#!/usr/bin/python2`
 
```bash
vi /usr/bin/yum 
```

- 把 `#!/usr/bin/python` 修改为 `#!/usr/bin/python2`

```bash
vi /usr/libexec/urlgrabber-ext-down 
```


## pip

* [Python包管理工作流](https://frostming.com/2018/09-14/python-packaging-flow)


### 镜像源

* [https://pypi.python.org](https://pypi.python.org)
* [https://pypi.org](https://pypi.org)


- 阿里云 [https://mirrors.aliyun.com/pypi/simple](https://mirrors.aliyun.com/pypi/simple)
- 中国科技大学 [https://pypi.mirrors.ustc.edu.cn/simple](https://pypi.mirrors.ustc.edu.cn/simple)
- 清华大学 [https://pypi.tuna.tsinghua.edu.cn/simple](https://pypi.tuna.tsinghua.edu.cn/simple)

* 豆瓣(douban) [http://pypi.douban.com/simple](http://pypi.douban.com/simple)
* 中国科学技术大学 [http://pypi.mirrors.ustc.edu.cn/simple](http://pypi.mirrors.ustc.edu.cn/simple)
* 华中理工大学 [http://pypi.hustunique.com](http://pypi.hustunique.com)
* 山东理工大学 [http://pypi.sdutlinux.org](http://pypi.sdutlinux.org)
* 上海交通大学 [https://mirrors.sjtug.sjtu.edu.cn/pypi](https://mirrors.sjtug.sjtu.edu.cn/pypi)


- 安装单个库

```batch
# 使用pip参数`-i 网址`，如果不是`https`协议网址需要加--trusted-host参数
pip install -i http://pypi.douban.com/simple --trusted-host pypi.douban.com requests
```

- 使用命令全局配置

```bash
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

- 编辑文件全局配置

```bash
# Linux环境
vi ~/.pip/pip.conf 
# windows环境
%APPDATA%\Romaing\pip\pip.ini

# 添加或者修改
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host=mirrors.aliyun.com
```



### 生成依赖管理文件

```bash
pip freeze > requirements.txt
```


### 根据管理文件安装依赖

```bash
pip install -r requirements.txt
pip install --requirement requirements.txt
```



### 更新

**更新pip**

```bash
python -m pip install --upgrade pip setuptools
```

- 解决pip安装模块提示已经安装更高版本问题

```bash
pip3 install --ignore-installed 模块名
```

**查看可更新的库**

```bash
pip list -o
pip list --outdated
# format有两个选项：columns(有表头), freeze(无表头), json
pip list --outdated --format=columns
```

**更新单个库**

```bash
pip install --upgrade 要升级的包名
```

**批量更新库**

* [使用pip升级所有包](https://www.codenong.com/2720014)

```bash
pip freeze --local | grep -v '^-e' | cut -d = -f 1  | xargs -n1 pip install -U

pip list -o --format=freeze | cut -d = -f 1  | xargs -n1 pip install -U
```

```bash
# 安装 pip-review
pip install pip-review
# 查看可更新的包
pip-review
# 自动更新所有包
pip-review --auto
# 更新包，提供操作可选项：[Y]es, [N]o, [A]ll, [Q]uit
pip-review --local --interactive
```

```python
from subprocess import call
from pip._internal.utils.misc import get_installed_distributions

packages = [dist.project_name for dist in get_installed_distributions()]
call("pip install --upgrade" + ' '.join(packages), shell=True)
```

```python
import pkg_resources
from subprocess import call

packages = [dist.project_name for dist in pkg_resources.working_set]
call("pip install --upgrade" + ' '.join(packages), shell=True)
```


### 卸载库

```bash
pip uninstall 要卸载的包名
```


