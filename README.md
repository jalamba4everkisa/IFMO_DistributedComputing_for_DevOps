# IFMO_DistributedComputing_for_DevOps
Distributed Computing course for DevOps 2025

## Используемый стек

- Ubuntu 24.04
- Установленный Ansible 2.18.4
- Доступ по SSH к удалённому хосту
- Wordpress 6.7
- MariaDB 11.7

---

## Структура проекта

├── .env                  # Переменные окружения для WordPress и MariaDB
├── .gitignore            # Исключения для Git (например, inventory.ini)
├── docker-compose.yml    # Описание Docker-сервисов
├── LICENSE               # Файл с данными по лизении
├── playbook.yml          # Ansible playbook для установки и запуска
└──  README.md             # Файл с описанием проекат

---

## Возможности

- Развёртывание WordPress и MariaDB по одной команде
- Переменные вынесены в `.env` для удобства конфигурации
- Очищаются старые контейнеры перед запуском
- Повторяемый и удобный для CI/CD подход

---

## Установка

1. Клонируйте репозиторий:

```bash
git clone https://github.com/praeitor/IFMO_DistributedComputing_for_DevOps.git
cd IFMO_DistributedComputing_for_DevOps.git
```

2. Создайте `inventory.ini` и укажите IP и SSH-параметры:

```bash
touch inventory.ini
```

```ini
[wordpress]
<IP-адрес вашего сервера> ansible_user=your_user ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3.12
```

3. Отредактируйте `.env` (указанные логин и пароли предоставлены в качестве примера):

```env
MYSQL_DATABASE=wpdb
MYSQL_USER=wpuser
MYSQL_PASSWORD=change_me_ple4se
MYSQL_ROOT_PASSWORD=rootP4ssw0rd!

WORDPRESS_DB_NAME=wpdb
WORDPRESS_DB_USER=wpuser
WORDPRESS_DB_PASSWORD=change_me_ple4se
WORDPRESS_DB_HOST=db:3306
```

4. Запустите Ansible:

```bash
ansible-playbook -i inventory.ini playbook.yml
```

---

## Доступ

После выполнения playbook установщик WordPress будет доступен по адресу:

```
http://<IP-адрес вашего сервера>
```

---

## Автор

Проект подготовлен в рамках курса **"Распределённые вычисления в DevOps"**
**Денис Булгаков**
Апрель 2025

---