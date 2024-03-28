~~~
$ sudo update-alternatives --config python
[sudo] password for b3nn9:
대체 항목 python에 대해 (/usr/bin/python 제공) 3개 선택이 있습니다.

  선택       경로              우선순 상태
------------------------------------------------------------
* 0            /usr/bin/python3.6   3         자동 모드
  1            /usr/bin/python2.7   1         수동 모드
  2            /usr/bin/python3.5   2         수동 모드
  3            /usr/bin/python3.6   3         수동 모드

Press <enter> to keep the current choice[*], or type selection number: 
$
~~~
~~~
$ sudo update-alternatives --install /usr/bin/python python /usr/local/bin/python3.7 4
update-alternatives: using /usr/local/bin/python3.7 to provide /usr/bin/python (python) in auto mode
$ sudo update-alternatives --install /usr/bin/python python /usr/local/bin/python3.9 5
update-alternatives: using /usr/local/bin/python3.9 to provide /usr/bin/python (python) in auto mode
$ python -V
Python 3.9.1
~~~
~~~
$ update-alternatives --list python
/usr/bin/python2.7
/usr/bin/python3.5
/usr/bin/python3.6
/usr/local/bin/python3.7
/usr/local/bin/python3.9
$ update-alternatives --config python
대체 항목 python에 대해 (/usr/bin/python 제공) 5개 선택이 있습니다.

  선택       경로                    우선순 상태
------------------------------------------------------------
* 0            /usr/local/bin/python3.9   5         자동 모드
  1            /usr/bin/python2.7         1         수동 모드
  2            /usr/bin/python3.5         2         수동 모드
  3            /usr/bin/python3.6         3         수동 모드
  4            /usr/local/bin/python3.7   4         수동 모드
  5            /usr/local/bin/python3.9   5         수동 모드

Press <enter> to keep the current choice[*], or type selection number:
$
~~~
