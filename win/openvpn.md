### 갑자기 OpenVPN 접속이 안되는
- 로그를 봅니다: %UserProfile%\OpenVPN\log
~~~
2024-01-13 12:45:21 WARNING: Compression for receiving enabled. Compression has been used in the past to break encryption. Sent packets are not compressed unless "allow-compression yes" is also set.
2024-01-13 12:45:21 DEPRECATED OPTION: --cipher set to 'AES-256-CBC' but missing in --data-ciphers (AES-256-GCM:AES-128-GCM). Future OpenVPN version will ignore --cipher for cipher negotiations. Add 'AES-256-CBC' to --data-ciphers or change --cipher 'AES-256-CBC' to --data-ciphers-fallback 'AES-256-CBC' to silence this warning.
2024-01-13 12:45:21 OpenVPN 2.5.4 Windows-MSVC [SSL (OpenSSL)] [LZO] [LZ4] [PKCS11] [AEAD] built on Oct 20 2021
2024-01-13 12:45:21 Windows version 10.0 (Windows 10 or greater) 64bit
2024-01-13 12:45:21 library versions: OpenSSL 1.1.1l  24 Aug 2021, LZO 2.10
2024-01-13 12:45:21 MANAGEMENT: Socket bind failed on local address [AF_INET]127.0.0.1:25341
2024-01-13 12:45:21 Exiting due to fatal error
~~~
- 파워쉘 열고 설정을 변경합니다
~~~
(base) PS C:\Windows\system32> netsh int ipv4 set dynamic tcp start=51001 num=5000
확인됨

(base) PS C:\Windows\system32> reg add HKLM\SYSTEM\CurrentControlSet\Services\hns\State /v EnableExcludedPortRange /d 0 /f
작업을 완료했습니다.
(base) PS C:\Windows\system32> netsh int ipv4 show excludedportrange protocol=tcp

프로토콜 tcp 포트 제외 범위

시작 포트    끝 포트
----------    --------
     20238       20337
     20338       20437
     25239       25338
     25339       25438
     39091       39091
     39721       39721
     47166       47265
     47678       47777
     50000       50059     *
     50195       50294

* - 관리 포트 제외입니다.
~~~
