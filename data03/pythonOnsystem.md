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
~~~
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8 5
$ sudo update-alternatives --list python
/usr/bin/python2.7
/usr/bin/python3.5
/usr/bin/python3.6
/usr/bin/python3.7
/usr/bin/python3.8
~~~
