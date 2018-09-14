---
title: "우분투(Ubuntu)에서 파이썬(python) pip 설치 불가"
comments: true
categories:
  - Ubuntu
tags:
  - ubuntu
  - python
---

## Ubuntu에서 python pip 설치 방법

지금까지 우분투에서 파이썬의 pip 패키지를 설치하려면 다음과 같이 입력하면 되었다.

```
sudo apt-get install python3-pip
```

하지만 이번에는 pip 패키지를 설치하려니 다음과 같은 에러가 발생!! :anger:  

```
E: Unable to locate package python-pip
```

구글에서 검색해 보니 우분투 12.04 또는 그 이상의 버전에서는 다음과 같이 실행해야 pip을 설치할 수 있다고 함!

```
sudo apt-get install python3-setuptools
sudo easy_install3 pip
```

```
jun@Jun-Laptop:~$ sudo apt-get install python3-setuptools
[sudo] password for jun:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following package was automatically installed and is no longer required:
  libfreetype6
Use 'sudo apt autoremove' to remove it.
Suggested packages:
  python-setuptools-doc
The following NEW packages will be installed:
  python3-setuptools
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 88.0 kB of archives.
After this operation, 439 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu xenial/main amd64 python3-setuptools all 20.7.0-1 [88.0 kB]
Fetched 88.0 kB in 1s (59.9 kB/s)
Selecting previously unselected package python3-setuptools.
(Reading database ... 25568 files and directories currently installed.)
Preparing to unpack .../python3-setuptools_20.7.0-1_all.deb ...
Unpacking python3-setuptools (20.7.0-1) ...
Setting up python3-setuptools (20.7.0-1) ...

jun@Jun-Laptop:~$ sudo easy_install3 pip
Searching for pip
Reading https://pypi.python.org/simple/pip/
Best match: pip 18.0
Downloading https://files.pythonhosted.org/packages/69/81/52b68d0a4de760a2f1979b0931ba7889202f302072cc7a0d614211bc7579/pip-18.0.tar.gz#sha256=a0e11645ee37c90b40c46d607070c4fd583e2cd46231b1c06e389c5e814eed76
Processing pip-18.0.tar.gz
Writing /tmp/easy_install-dkzdqshg/pip-18.0/setup.cfg
Running pip-18.0/setup.py -q bdist_egg --dist-dir /tmp/easy_install-dkzdqshg/pip-18.0/egg-dist-tmp-z3m20w_f
/usr/lib/python3.5/distutils/dist.py:261: UserWarning: Unknown distribution option: 'python_requires'
creating /usr/local/lib/python3.5/dist-packages/pip-18.0-py3.5.egg
Extracting pip-18.0-py3.5.egg to /usr/local/lib/python3.5/dist-packages
Adding pip 18.0 to easy-install.pth file
Installing pip3 script to /usr/local/bin
Installing pip script to /usr/local/bin
Installing pip3.5 script to /usr/local/bin

Installed /usr/local/lib/python3.5/dist-packages/pip-18.0-py3.5.egg
Processing dependencies for pip
Finished processing dependencies for pip

jun@Jun-Laptop:~$ pip --version
pip 18.0 from /usr/local/lib/python3.5/dist-packages/pip-18.0-py3.5.egg/pip (python 3.5)
```
스무스하게 해결됨! :two_hearts:
