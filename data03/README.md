### 주피터 허브 재기동
~~~
$ sudo service jupyterhub restart
~~~
### 주피터 관리자 설정
~~~
$ vi /etc/jupyter/jupyterhub_config.py
c.JupyterHub.admin_access = True
c.JupyterHub.admin_users = {'b3nn9','dyjin','noconda'}
$ sudo service jupyterhub restart
~~~
