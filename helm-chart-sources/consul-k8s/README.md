consul-k8s集群部署
### 部署前需要确认，相关pvc配置


## pvc pv 创建规律是
- 一般请下是3个
> {{ .Values.volumeMountsName }}-{{ .Values.ServiceName }}-[0-2]

```yaml
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-0
  labels:
    app: crld-oa-uat-consul-consul-server-0
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-0
    server: 10.201.199.14
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-1
  labels:
    app: crld-oa-uat-consul-consul-server-1
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-1
    server: 10.201.199.14
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-2
  labels:
    app: crld-oa-uat-consul-consul-server-2
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-2
    server: 10.201.199.14
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-0
  labels:
    app: crld-oa-uat-consul-consul-server-0
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-0
    server: 10.201.199.14
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-1
  labels:
    app: crld-oa-uat-consul-consul-server-1
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-1
    server: 10.201.199.14
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: crld-oa-uat-consul-consul-server-2
  labels:
    app: crld-oa-uat-consul-consul-server-2
spec:
  capacity:
    storage: 10Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  nfs:
    path: /hrzd_rqpt_prod2/crld-oa-uat-consul-consul-server-2
    server: 10.201.199.14
[root@crc-dev_k8s_master-1 consul]# cat pvc-crld-oa-uat-consul.yaml
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: crld-oa-uat-consul-consul-server-0
  namespace: crld-oa-uat
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Gi
  volumeMode: Filesystem
  volumeName: crld-oa-uat-consul-consul-server-0
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: crld-oa-uat-consul-consul-server-1
  namespace: crld-oa-uat
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Gi
  volumeMode: Filesystem
  volumeName: crld-oa-uat-consul-consul-server-1
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: crld-oa-uat-consul-consul-server-2
  namespace: crld-oa-uat
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Gi
  volumeMode: Filesystem
  volumeName: crld-oa-uat-consul-consul-server-2
```