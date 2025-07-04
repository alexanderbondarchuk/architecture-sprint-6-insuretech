# Заметки по практической работе

## Предусловия. Установлены инструменты

1. Minikube
2. Kubectl
3. Python
4. Pip
5. Locust. Чтобы его установить, потребуется pip.

## Порядок действий

1. Запустил миникуб
  
   ```bash
   minikube start
   ```

2. Запустил сервис метрик

   ```bash
   minikube addons enable metrics-server
   ```

3. Применил конфигурацию деплоймента

   ```bash
   kubectl apply -f deployment.yaml
   ```

4. Применил конфигурацию автоскейлера

    ```bash
    kubectl apply -f hpa.yaml
    ```

5. Применил конфигурацию сервиса

   ```bash
   kubectl apply -f service.yaml
   ```

6. Запустил дашборд кубернетеса

   ```bash
   minikube dashboard
   ```

7. Получил адрес для обращения к сервису 

   ```bash
   minikube service scaletestapp-service --url
   ```

8. Запустил Locust, вставил адрес из предыдущего пункта в соответствующее поле, настроил профиль нагрузки: цель в 10000 пользователей с шагом прироста 25

    ```bash
    locust
    ```
