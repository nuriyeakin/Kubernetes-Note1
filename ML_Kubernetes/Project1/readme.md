
### 1. 

``` 
apiVersion: hangi api versionuyla tanımlanacak.
kind:       hangi tür obje oluşturulacak
metadata:   unig bilgileri tanımlarız.İsim gibi
spec:       objenin özelliklerini belirleme
``` 

mlops_ingress_4/ml-prediction-deployment.yaml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ml-prediction-deployment
  labels:
    app: ml-prediction
spec:
  replicas: 3
  selector:
    matchLabels:
      app: ml-prediction
  template:
    metadata:
      labels:
        app: ml-prediction
    spec:
      containers:
      - name: ml-prediction
        image: ml_kubectl_ingress
        imagePullPolicy: Never
        ports:
        - containerPort: 8000
```