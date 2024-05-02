### Проектная работа 6 (SkillFactory)

В проекте переконфигурирован _**ansible.cfg**_
```
[defaults]
inventory = /home/ansible/project_6/hosts
roles_path = /home/ansible/project_6/roles
sudo_user = ansible
```
**roles** и **hosts** находятся в папке проекта.

Заданы адреса управляемых хостов и переменные **_hosts_**
```commandline
# хосты, на которые ставится докер
[app]
192.168.0.4
192.168.0.26

# на localhost крутится база данных
[database]
localhost postgres_data_dir=/opt/database postgres_version=15

[web]
localhost
```
Playbook `install_docker.yaml` устанавливает на управляемый хост
Docker в зависимости от операционной системы хоста (Ubuntu or CentOS)

Playbook `install_postgres.yaml` устанавливает на управляемый хост
(localhost в нашем случае) Postgres. Версия и директория для хранения
данных задаются переменными в `hosts`

