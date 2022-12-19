Install postgresql 14 for 1C server
=========

postgresql14-role

Ansible role для установки postgresql 14 c патчем от 1С.
Состоит из следующих групп tasks:
- Установка locales RU - install_locale_ru.yml.
- Установка дополнительных объектов - install_other_pack.yml.
- Установка postgresql 14 с патчем от 1С - install_postgresql.yml.

Включить/отключить нужный блок можно раскоментировав/закоментировав его в tasks/main.yml

Перед запуском роли необходимо скачать в папку files/distr установочные пакеты postgresql14 с патчем от 1С.

Requirements
------------

- Разработана с помощью ansible 2.13.3
- Работоспособность протестирована на Ubuntu 20.04 и Ubuntu 22.04.

Role Variables
--------------

folder_distr: расположение папки для копирования устновочных пакетов
path_distr: для удобства полный путь
psql_password: password
psql_ver: устанавливаемая версия postgresql (в данном случае14.5-3.1C
psql_packages: список пакетов для установки
other_packages: список дополнительных пакетов для установки
  
Example Playbook
----------------
```
- name: Install postgresql 14 for server 1C
  hosts: your_servers
  roles:
    - postgresql14-role
```
  
License
-------

MIT

Author Information
------------------

Сердюков Роман
reserdukov@gmail.com