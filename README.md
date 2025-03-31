# IFMO_DistributedComputing_for_DevOps
Создал простой плейбук, который установит на целевую машину с ОС Ubuntu Docker, а также запустит в нём Wordpress с MariaDB.
Для запуска требуется подключиться из под пользователя с root правами, который может запускать sudo команды без запроса пароля.
На целевой машине требуется установить ansible крайней версии:
```
sudo apt update -y
sudo apt install -y software-properties-common
sudo add-apt-repository -y --update ppa:ansible/ansible
sudo apt install -y ansible
```
Команда для запуска плейбука:
```
ansible-playbook -i inventory.ini playbook.yaml
```
В inventory.ini нужно перечислить целевые хосты.
