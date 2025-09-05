# UPD transfer over ssh

https://www.disk91.com/2020/technology/systems/transfer-udp-over-ssh/

on laptop :

ssh -L 1234:localhost:1234 srlab

on srlab :
socat tcp4-listen:1234,reuseaddr,fork UDP:10.42.0.10:2527

on laptop :
socat -T15 udp4-recvfrom:2527,reuseaddr,fork tcp:localhost:1234