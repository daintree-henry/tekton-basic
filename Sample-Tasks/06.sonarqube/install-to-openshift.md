## Install sonarqube to OpenShift

```shell
git clone https://github.com/daintree/helm-chart-sonarqube.git

cd helm-chart-sonarqube/charts/sonarqube
helm dependency update

oc new-project sonarqube

helm upgrade --install -f values.yaml -n sonarqube sonarqube ./

oc expose service/sonarqube-sonarqube --hostname=sonarqube.apps.cicd.kolonocp4.com
oc get all,pvc,route

```

##### 설치 후 프로젝트 및 토큰 생성