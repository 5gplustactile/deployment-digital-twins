
DEMO NWDAF AND 5GC
-------------------

Open5GS
--------
--------

| Internal Endpoint | Ports|
|----------|----------|
| open5gs-amf-ngap.auto-open5gs.svc.cluster.local | 38412/SCTP |
| open5gs-amf-sbi.auto-open5gs.svc.cluster.local | 7777/TCP |
| open5gs-upf-gtpu.auto-open5gs.svc.cluster.local | 2152/UDP |
| open5gs-upf-pfcp.auto-open5gs.svc.cluster.local| 8805/UDP |


Prometheus
----------
----------

| Internal Endpoint | Ports|
|----------|----------|
| prometheus.prometheus-system.svc.cluster.local | 9090/TCP |

```
# to access to prometheus external endpoint, use the jump host and foxiproxy using this ssh config (you must be connected through the ITuser VPN):
Host tactile5g-telefonica
  HostName 10.11.29.8
  ProxyJump pen-socks
  User labuser
  DynamicForward 8080
```

| External Endpoint | Ports|
|----------|----------|
| http://10.11.29.104:9090 | 9090/TCP |


Events-svc
----------
----------

| Internal Endpoint | Ports|
|----------|----------|
| events-svc.events-svc.svc.cluster.local | 80/TCP |
| mongo.events-svc.svc.cluster.local | 27017/TCP |
| mongo-express.events-svc.svc.cluster.local | 8082/TCP |

NWDAF
-----
-----

| Internal Endpoint | Ports|
|----------|----------|
| nwdaf-nginx.nwdaf-netapi.svc.cluster.local | 80/TCP |

Airflow
-------
-------

```
# to access to airflow external endpoint, use the jump host and foxiproxy using this ssh config (you must be connected through the ITuser VPN):
Host tactile5g-telefonica
  HostName 10.11.29.8
  ProxyJump pen-socks
  User labuser
  DynamicForward 8080
```

| External Endpoint | Ports|
|----------|----------|
| http://10.11.29.105:8080 | 8080/TCP |


Skooner
-------
-------

```
# to access to skooner external endpoint, use the jump host and foxiproxy using this ssh config (you must be connected through the ITuser VPN):
Host tactile5g-telefonica
  HostName 10.11.29.8
  ProxyJump pen-socks
  User labuser
  DynamicForward 8080
```


| External Endpoint | Ports|
|----------|----------|
| http://10.11.29.103:4654/ | 4654/TCP |


ArgoCD
-------
-------

```
# to access to argocd, use the jump host and foxiproxy using this ssh config (you must be connected through the ITuser VPN):
Host tactile5g-telefonica
  HostName 10.11.29.8
  ProxyJump pen-socks
  User labuser
  DynamicForward 8080

- https://internal-argocd-https-1137655741.eu-west-3.elb.amazonaws.com

```
