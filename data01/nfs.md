~~~
$ sudo exportfs -a
exportfs: /etc/exports [1]: Neither 'subtree_check' or 'no_subtree_check' specified for export "192.168.1.101/255.255.255.0:/media".
  Assuming default behaviour ('no_subtree_check').
  NOTE: this default has changed since nfs-utils version 1.0.x

$ sudo systemctl status nfs-kernel-server.service
● nfs-server.service - NFS server and services
   Loaded: loaded (/lib/systemd/system/nfs-server.service; enabled; vendor preset: enabled)
   Active: active (exited) since 목 2024-05-16 16:34:48 KST; 7s ago
  Process: 5885 ExecStopPost=/usr/sbin/exportfs -f (code=exited, status=0/SUCCESS)
  Process: 5881 ExecStopPost=/usr/sbin/exportfs -au (code=exited, status=0/SUCCESS)
  Process: 5877 ExecStop=/usr/sbin/rpc.nfsd 0 (code=exited, status=0/SUCCESS)
  Process: 5965 ExecStart=/usr/sbin/rpc.nfsd $RPCNFSDARGS (code=exited, status=0/SUCCESS)
  Process: 5961 ExecStartPre=/usr/sbin/exportfs -r (code=exited, status=0/SUCCESS)
 Main PID: 5965 (code=exited, status=0/SUCCESS)

 5월 16 16:34:48 DataLX01 systemd[1]: Starting NFS server and services...
 5월 16 16:34:48 DataLX01 exportfs[5961]: exportfs: /etc/exports [1]: Neither 'subtree_check' or 'no_subtree_check' spec
 5월 16 16:34:48 DataLX01 exportfs[5961]:   Assuming default behaviour ('no_subtree_check').
 5월 16 16:34:48 DataLX01 exportfs[5961]:   NOTE: this default has changed since nfs-utils version 1.0.x
 5월 16 16:34:48 DataLX01 rpc.nfsd[5965]: rpc.nfsd: unable to bind inet TCP socket: errno 98 (Address already in use)
 5월 16 16:34:48 DataLX01 systemd[1]: Started NFS server and services.
~~~
~~~
$ sudo apt update
기존:1 http://mirror.kakao.com/ubuntu xenial InRelease
기존:2 http://mirror.kakao.com/ubuntu xenial-updates InRelease
기존:3 http://mirror.kakao.com/ubuntu xenial-backports InRelease
기존:4 http://mirror.kakao.com/ubuntu xenial-security InRelease
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다
상태 정보를 읽는 중입니다... 완료
260 packages can be upgraded. Run 'apt list --upgradable' to see them.
$ sudo apt install nfs-kernel-server
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다
상태 정보를 읽는 중입니다... 완료
The following additional packages will be installed:
  keyutils libnfsidmap2 nfs-common
제안하는 패키지:
  open-iscsi watchdog
다음 새 패키지를 설치할 것입니다:
  keyutils libnfsidmap2 nfs-common nfs-kernel-server
0개 업그레이드, 4개 새로 설치, 0개 제거 및 260개 업그레이드 안 함.
352 k바이트 아카이브를 받아야 합니다.
이 작업 후 1,486 k바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
......
(데이터베이스 읽는중 ...현재 407737개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../libnfsidmap2_0.25-5_amd64.deb ...
Unpacking libnfsidmap2:amd64 (0.25-5) ...
Selecting previously unselected package keyutils.
Preparing to unpack .../keyutils_1.5.9-8ubuntu1_amd64.deb ...
Unpacking keyutils (1.5.9-8ubuntu1) ...
Selecting previously unselected package nfs-common.
Preparing to unpack .../nfs-common_1%3a1.2.8-9ubuntu12.3_amd64.deb ...
Unpacking nfs-common (1:1.2.8-9ubuntu12.3) ...
Selecting previously unselected package nfs-kernel-server.
Preparing to unpack .../nfs-kernel-server_1%3a1.2.8-9ubuntu12.3_amd64.deb ...
Unpacking nfs-kernel-server (1:1.2.8-9ubuntu12.3) ...
Processing triggers for man-db (2.7.5-1) ...
Processing triggers for ureadahead (0.100.0-19.1) ...
ureadahead will be reprofiled on next reboot
Processing triggers for systemd (229-4ubuntu21.31) ...
libnfsidmap2:amd64 (0.25-5) 설정하는 중입니다 ...
keyutils (1.5.9-8ubuntu1) 설정하는 중입니다 ...
nfs-common (1:1.2.8-9ubuntu12.3) 설정하는 중입니다 ...

Creating config file /etc/idmapd.conf with new version

Creating config file /etc/default/nfs-common with new version
시스템 사용자 `statd' (129) 추가 ...
새로운 사용자 `statd' (129) 을(를) 그룹 `nogroup'(으)로 추가 ...
홈 디렉토리 '/var/lib/nfs' 을(를) 만들지 않습니다.
nfs-utils.service is a disabled or a static unit, not starting it.
nfs-kernel-server (1:1.2.8-9ubuntu12.3) 설정하는 중입니다 ...
Replacing config file /etc/exports with new version
Replacing config file /etc/exports with new version

Creating config file /etc/default/nfs-kernel-server with new version
Processing triggers for libc-bin (2.23-0ubuntu11.3) ...
/sbin/ldconfig.real: /usr/local/cuda-10.0/targets/x86_64-linux/lib/libcudnn.so.7 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-10.1/targets/x86_64-linux/lib/libcudnn.so.7 is not a symbolic link

Processing triggers for ureadahead (0.100.0-19.1) ...
Processing triggers for systemd (229-4ubuntu21.31) ...
~~~
