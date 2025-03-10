# Домашнее задание к занятию «Kubernetes. Часть 1»

### Задание 1
Выполните действия:

Запустите Kubernetes локально, используя k3s или minikube на свой выбор.
Добейтесь стабильной работы всех системных контейнеров.

![Снимок экрана (551)](https://github.com/user-attachments/assets/8731f146-90e0-463e-957a-57a7429e708c)


### Задание 2
Есть файл с деплоем:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: redis
spec:
  selector:
    matchLabels:
      app: redis
  replicas: 1
  template:
    metadata:
      labels:
        app: redis
    spec:
      containers:
      - name: master
        image: bitnami/redis
        env:
         - name: REDIS_PASSWORD
           value: password123
        ports:
        - containerPort: 6379








```


Выполните действия:

Измените файл с учётом условий:
redis должен запускаться без пароля;
создайте Service, который будет направлять трафик на этот Deployment;
версия образа redis должна быть зафиксирована на 6.0.13.
Запустите Deployment в своём кластере и добейтесь его стабильной работы.
















