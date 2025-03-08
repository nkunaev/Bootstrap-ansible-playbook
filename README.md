# bootstrap-ansible-playbook
This ansible playbook developed to speedup boostraping own machine

![Ansible](https://img.shields.io/badge/ansible-role-blue.svg)
![Molecule](https://img.shields.io/badge/molecule-testing-green.svg)

## Описание
Этот репозиторий содержит Ansible-роль для преднастройки виртуальной машины.Конфигурация проверяется с помощью тестирования на основе [Molecule](https://molecule.readthedocs.io/).

# Платформы
- Deb-based

## Возможности
- Настройка окружения на виртуальной машине
- Возможность кастомизации через переменные Ansible
- Автоматическое тестирование роли через Molecule
- Управление устанавливаемыми пакетами
- Установка и кастромизация параметров NTP сервера
- Управление репозиториями (app, deb) и их gpg-подписями
- Изменение параметров sysctl
- Создание пользователя и пароля к нему через prompt
- Установка дополнительных корневых сертификатов

## Требования
Перед началом работы убедитесь, что у вас установлены следующие зависимости:
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Molecule](https://molecule.readthedocs.io/en/latest/installation.html)
- [Podman](https://podman.io/docs/installation)

## Установка
Клонируйте репозиторий и перейдите в его директорию:  
```sh
git clone https://github.com/nkunaev/bootstrap-ansible-playbook.git && cd bootstrap-ansible-playbook
```  

## Использование

Запустите плейбук Ansible:
```sh
ansible-playbook -i inventory bootstrap.yaml
```
## Тестирование
Для запуска тестов воспользуйтесь командой:
```sh
molecule test
```
Для пошагового запуска:
```sh
molecule converge
molecule verify
```
## Переменные
Вы можете переопределить переменные по умолчанию в используя *extra_vars*:  
```yaml
ansible-playbook -i inventory bootstrap.yaml -e @path/to/vars.yaml
```

## Лицензия
Этот проект распространяется под лицензией MIT.
## Автор
- nkunaev - [GitHub](https://github.com/nkunaev)
