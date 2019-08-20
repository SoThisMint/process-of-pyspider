64位win10系统
Python3.7
用pip命令安装pyspider，命令pip install pyspider进行安装，但是重点来了：报错！！！错误大概如下：

“Command "python setup.py egg_info" failed with error code 10”...
Your are using pip version 10.0.1, however version 18.0 is available...
所以接下来升级pip版本，执行命令 python -m pip install --upgrade pip

PS D:\python\demo> pip install pyspider
Collecting pip
  Downloading https://files.pythonhosted.org/packages/5f/25/e52d3f31441505a5f3af41213346e5b6c221c9e086a166f3703d2ddaf940/pip-18.0-py2.py3-none-any.whl (1.3MB)
    100% |████████████████████████████████| 1.3MB 45kB/s
Installing collected packages: pip
  Found existing installation: pip 10.0.1
    Uninstalling pip-10.0.1:
      Successfully uninstalled pip-10.0.1
Successfully installed pip-18.0
提示成功后再次执行pip install pyspider进行安装，但是又双叒叕报错！！！错误不提示pip版本问题了：

Command "python setup.py egg_info" failed with error code 10 in C:\Users\xxx\AppData\Local\Temp\pip-install-tc5uvu7l\pycurl\
经过网上大拿的经验需要安装wheel，执行命令pip3 install wheel安装，提示Successfully installed wheel-0.31.1代表安装成功，然后访问https://www.lfd.uci.edu/~gohlke/pythonlibs/下载相关安装文件，具体如下：

PycURL, a interface to the libcurl library.
    pycurl‑7.43.1‑cp27‑cp27m‑win32.whl
    pycurl‑7.43.1‑cp27‑cp27m‑win_amd64.whl
    pycurl‑7.43.1‑cp34‑cp34m‑win32.whl
    pycurl‑7.43.1‑cp34‑cp34m‑win_amd64.whl
    pycurl‑7.43.1‑cp35‑cp35m‑win32.whl
    pycurl‑7.43.1‑cp35‑cp35m‑win_amd64.whl
    pycurl‑7.43.1‑cp36‑cp36m‑win32.whl
    pycurl‑7.43.1‑cp36‑cp36m‑win_amd64.whl
    pycurl‑7.43.1‑cp37‑cp37m‑win32.whl
    pycurl‑7.43.1‑cp37‑cp37m‑win_amd64.whl
具体下载版本根据你使用的环境来定，比如我的是python3.7，然后python是32位版本，则需要选择pycurl‑7.43.1‑cp37‑cp37m‑win32.whl进行下载，注意：32或64位版本不是电脑的版本，是安装python的版本！！！

下载后进行安装，命令 pip3 install D:\python\demo\pycurl-7.43.1-cp37-cp37m-win_amd64.whl执行，如果报错：

pycurl-7.43.1-cp37-cp37m-win_amd64.whl is not a supported wheel on this platform.
代表你安装的版本不对，就是上面所述的那个，我电脑是64位的，python是32位的，所以报错，然后下载pycurl‑7.43.1‑cp37‑cp37m‑win32.whl后再执行命令pip3 install D:\python\demo\pycurl-7.43.1-cp37-cp37m-win32.whl安装即可，提示Successfully installed pycurl-7.43.1及安装成功！

费了很大事，最后再安装pyspider就OK了，执行命令pip3 install pyspider提示

Successfully installed Flask-1.0.2 Flask-Login-0.4.1 Jinja2-2.10 MarkupSafe-1.0 PyYAML-3.13 Werkzeug-0.14.1 click-6.7 cssselect-1.0.3 defusedxml-0.5.0 itsdangerous-0.24 jsmin-2.2.2 lxml-4.2.5 pyquery-1.4.0 pyspider-0.3.10 tblib-1.3.2 tornado-4.5.3 u-msgpack-python-2.5.0 wsgidav-2.4.1
大功告成！！！
