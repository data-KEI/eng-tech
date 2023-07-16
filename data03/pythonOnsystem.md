### 시스템에서 주 파이썬 버전 선택
~~~
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
update-alternatives: using /usr/bin/python2.7 to provide /usr/bin/python (python) in auto mode
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.5 2
update-alternatives: using /usr/bin/python3.5 to provide /usr/bin/python (python) in auto mode
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 3
update-alternatives: using /usr/bin/python3.6 to provide /usr/bin/python (python) in auto mode
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.7 4
update-alternatives: using /usr/bin/python3.7 to provide /usr/bin/python (python) in auto mode
$ sudo update-alternatives --list python
/usr/bin/python2.7
/usr/bin/python3.5
/usr/bin/python3.6
/usr/bin/python3.7
$ sudo update-alternatives --config python
There are 4 choices for the alternative python (providing /usr/bin/python).

  Selection    Path                Priority   Status
------------------------------------------------------------
* 0            /usr/bin/python3.7   4         auto mode
  1            /usr/bin/python2.7   1         manual mode
  2            /usr/bin/python3.5   2         manual mode
  3            /usr/bin/python3.6   3         manual mode
  4            /usr/bin/python3.7   4         manual mode

Press <enter> to keep the current choice[*], or type selection number: 3
update-alternatives: using /usr/bin/python3.6 to provide /usr/bin/python (python) in manual mode
~~~
### 파이썬 3.8 설치 on Ubuntu 18.04.3 LTS
~~~
$ cat /etc/os-release
NAME="Ubuntu"
VERSION="18.04.3 LTS (Bionic Beaver)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 18.04.3 LTS"
VERSION_ID="18.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=bionic
UBUNTU_CODENAME=bionic
$ sudo apt install python3.8 -y
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 5
$ sudo update-alternatives --list python
/usr/bin/python2.7
/usr/bin/python3.5
/usr/bin/python3.6
/usr/bin/python3.7
/usr/bin/python3.8
~~~
### 파이썬 3.9 코드컴파일 설치 on Ubuntu 18.04.3 LTS
~~~
$ sudo apt install build-essential zlib1g-dev \
libncurses5-dev libgdbm-dev libnss3-dev \
libssl-dev libreadline-dev libffi-dev curl software-properties-common
$ wget https://www.python.org/ftp/python/3.9.0/Python-3.9.0.tar.xz
$ tar -xf Python-3.9.0.tar.xz
$ cd Python-3.9.0/
$ sudo make altinstall
$ sudo update-alternatives --install /usr/bin/python python /usr/local/bin/python3.9 6
$ sudo update-alternatives --list python
/usr/bin/python2.7
/usr/bin/python3.5
/usr/bin/python3.6
/usr/bin/python3.7
/usr/bin/python3.8
/usr/local/bin/python3.9
~~~
