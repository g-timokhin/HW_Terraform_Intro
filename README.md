# Чек-лист готовности к домашнему заданию

1) Установить Terraform

![image](https://github.com/user-attachments/assets/dd055a87-39cd-454f-92bf-83aeba905a77)

2) Склонировать репозиторий

![image](https://github.com/user-attachments/assets/fd726f87-8fd6-49b9-9138-bc175011335c)

3) Проверить наличие докера

![image](https://github.com/user-attachments/assets/4d6ef65d-85b9-4bfa-8bf2-04c91449946a)

# Задание 1

1) Установка зависимостей

![image](https://github.com/user-attachments/assets/5fa605b2-a747-455d-b6a2-7af3e9a5761f)

2) Согласно .gitignore, секретную информацию допустимо хранить в файле personal.auto.tfvars

3) Выполнение кода:

![image](https://github.com/user-attachments/assets/facd5e53-3b2e-4634-a8b0-f351ddba1201)

![image](https://github.com/user-attachments/assets/183ca229-4cb8-4eeb-80a6-de8a5399b55d)

Секретное содержимое ресурса random_password

"result": "XNTduCIucyc525yW"

4) Валидация разархивированного кода

![image](https://github.com/user-attachments/assets/015edc9c-735a-47c8-b862-23b3b1422cd2)

В коде допущены четыре ошибки:
* Для ресурса docker_image не указано имя
* Имя для ресурса docker_container выбрано некорректно -- оно не должно начинаться с цифры
* В аргументе name ресурса docker_container указано неверное имя для обращения к ресурсу random_password -- random_string_FAKE вместо random_string
* В аргументе name для ресурса docker_container неверно указано наименование параметра -- resulT вместо result


5) Ошибки исправлены, валидация проходит успешно

![image](https://github.com/user-attachments/assets/ec51785c-1517-47a9-b20d-e8df2ff91df7)


![image](https://github.com/user-attachments/assets/7b93c32c-c237-4e6f-8046-b4ad44994cfc)

Выполнение кода проходит успешно

![image](https://github.com/user-attachments/assets/ae999ceb-5ea1-4ebb-9b41-887e9b1fab1e)

Вывод команды docker ps

![image](https://github.com/user-attachments/assets/3ac9330d-2d46-430d-8da3-92ec39edd83f)

6) Использование флага -auto-approve позволяет пропускать этап подтверждения выполнения команды terraform apply вручную (посредством ввода пользователем "yes"), данная опция может быть полезной при интеграции Terraform в пайплайны CI/CD или при автоматическом развертывании инфраструктуры с помощью скриптов, однако ее применение сопряжено с риском пропуска пользователем значимых изменений в HCL-коде, которые могут повлечь за собой масштабные инфраструктурные сбои и потерю ценных данных

Имя контейнера успешно изменено

![image](https://github.com/user-attachments/assets/f0e7ed7a-9f03-4437-9190-20847a44c692)

7) Уничтожение созданных ресурсов

![image](https://github.com/user-attachments/assets/3bd35fa7-5f24-4e97-b0b4-8b41c35f0d98)

Содержимое файла terrafotm.tfstate

![image](https://github.com/user-attachments/assets/83118b9c-48ed-434f-86de-f67654c628d3)

8) Докер-образ не был удален, потому что для ресурса docker_image указано "keep_locally = true"

В документации про этот аргумент написано: keep_locally (Boolean) If true, then the Docker image won't be deleted on destroy operation. If this is false, it will delete the image from the docker local storage on destroy operation.


















