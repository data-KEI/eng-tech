### 오류
- SSH 접속이 안됨: 서버키가 변경되어 "C:\Users\[계정명]\.ssh\known_hosts"에서 [서버주소] 검색해서 키를 삭제(해당 라인 전체)하고 저장하면 됨
~~~
C:\Users\KEI>ssh [ID]@[서버주소] -p 764
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ECDSA key sent by the remote host is
SHA256:DnHMpMVFn5EHB32SoQTajIrw2I0YGT4r93XqsI1QeNM.
Please contact your system administrator.
Add correct host key in C:\\Users\\KEI/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in C:\\Users\\KEI/.ssh/known_hosts:27
ECDSA host key for [192.168.1.107]:764 has changed and you have requested strict checking.
Host key verification failed.
~~~
