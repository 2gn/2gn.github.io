#linux

意外と使うが取り上げられにくいコマンドを紹介します。随時更新
## ss -tuln

使ってるポートの一覧が見れる

例:

```
$ ss -tuln
Netid  State   Recv-Q   Send-Q                             Local Address:Port                      Peer Address:Port                  Process
udp    UNCONN  0        0                                        0.0.0.0:5353                           0.0.0.0:*
udp    UNCONN  0        0                                        0.0.0.0:39395                          0.0.0.0:*
udp    UNCONN  0        0                                        0.0.0.0:53                             0.0.0.0:*
udp    UNCONN  0        0                                        0.0.0.0:41641                          0.0.0.0:*
udp    UNCONN  0        0                                        0.0.0.0:53082                          0.0.0.0:*
udp    UNCONN  0        0                                        0.0.0.0:21027                          0.0.0.0:*
udp    UNCONN  0        0                                           [::]:5353                              [::]:*
udp    UNCONN  0        0                                              *:22000                                *:*
udp    UNCONN  0        0                                              *:47401                                *:*
udp    UNCONN  0        0                                              *:39281                                *:*
udp    UNCONN  0        0                                           [::]:53                                [::]:*
udp    UNCONN  0        0                                           [::]:49207                             [::]:*
udp    UNCONN  0        0          [fe80::a47e:9570:5a5f:bd4f]%wlp0s20f3:546                               [::]:*
udp    UNCONN  0        0                                           [::]:41641                             [::]:*
udp    UNCONN  0        0                                              *:1716                                 *:*
udp    UNCONN  0        0                                           [::]:52854                             [::]:*
udp    UNCONN  0        0                                           [::]:21027                             [::]:*
tcp    LISTEN  0        10                                     127.0.0.1:37593                          0.0.0.0:*
tcp    LISTEN  0        4096                              100.110.194.55:45051                          0.0.0.0:*
tcp    LISTEN  0        4096                                   127.0.0.1:4369                           0.0.0.0:*
tcp    LISTEN  0        32                                       0.0.0.0:53                             0.0.0.0:*
tcp    LISTEN  0        128                                    127.0.0.1:5984                           0.0.0.0:*
tcp    LISTEN  0        128                                    127.0.0.1:631                            0.0.0.0:*
tcp    LISTEN  0        4096                                   127.0.0.1:8384                           0.0.0.0:*
tcp    LISTEN  0        10                                     127.0.0.1:34673                          0.0.0.0:*
tcp    LISTEN  0        4096                                   127.0.0.1:2019                           0.0.0.0:*
tcp    LISTEN  0        128                                    127.0.0.1:36821                          0.0.0.0:*
tcp    LISTEN  0        1024                                   127.0.0.1:4000                           0.0.0.0:*
tcp    LISTEN  0        50                                             *:33755                                *:*
tcp    LISTEN  0        4096                                       [::1]:4369                              [::]:*
tcp    LISTEN  0        32                                          [::]:53                                [::]:*
tcp    LISTEN  0        50                                             *:1716                                 *:*
tcp    LISTEN  0        4096                 [fd7a:115c:a1e0::ea01:c237]:41958                             [::]:*
tcp    LISTEN  0        128                                        [::1]:631                               [::]:*
tcp    LISTEN  0        4096                                           *:22000                                *:*
tcp    LISTEN  0        4096                                           *:8080                                 *:*

```


