# IFMO_DistributedComputing_for_DevOps
Лабораторная работа 1.
Создал плейбук, который установит на целевую машину с ОС Ubuntu Docker, а также запустит в нём Wordpress с MariaDB.
Для запуска требуется подключиться из под пользователя с root правами, который может запускать sudo команды без запроса пароля.
На хосте с которого будет происходить управление требуется установить ansible крайней версии:
```
sudo apt update -y
sudo apt install -y software-properties-common
sudo add-apt-repository -y --update ppa:ansible/ansible
sudo apt install -y ansible
```
Команда для запуска плейбука:
```
ansible-playbook -i inventory/production/hosts site.yaml --ask-vault-pass
```
В inventory/production/hosts нужно перечислить целевые хосты.
При запросе ввести пароль password (используется в демонстративных целях).
Без шифровки пример файла с переменными в group_vars/all_example.yaml
