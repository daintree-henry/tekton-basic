### Kubernetes

### OpenShift
```shell
#overlay 파일시스템을 이용하기 위해 pipeline SA에 privileged 권한이 필요
oc adm policy add-scc-to-user privileged -z pipeline

#docker hub에 Push하기 위한 레지스트리 정보를 pipeline SA에 할당
oc create secret docker-registry dockertoken --docker-username=dainforest --docker-password=$DOCKERHUBTOKEN
oc secrets link pipeline dockertoken -n cicd
```