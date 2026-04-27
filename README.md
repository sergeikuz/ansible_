# Ansible Learning Project

Проект для изучения Ansible — автоматизация настройки серверов и развёртывания.

## Структура

```
ansible/
├── ansible.cfg              # Конфигурация Ansible
├── inventory.ini            # Инвентарь серверов
├── requirements.yml         # Зависимости (роли из Ansible Galaxy)
├── playbooks/               # Плейбуки
├── foo_role/                # Учебная роль
├── foo_second_role/         # Вторая учебная роль
└── roles/
    └── user_setup/          # Роль настройки пользователя-разработчика
```

## Роли

### `foo_role` / `foo_second_role`
Учебные роли для ознакомления со структурой ролей Ansible.

### `user_setup`
Настройка окружения для удалённого разработчика:
- Создание пользователя
- Настройка `.gitconfig` (шаблон `gitconfig.j2`)
- Установка необходимых пакетов

## Использование

1. Установите зависимости:
   ```bash
   ansible-galaxy install -r ansible/requirements.yml
   ```

2. Запустите плейбук:
   ```bash
   ansible-playbook -i ansible/inventory.ini ansible/roles/setup_dev_env.yml
   ```

## Инвентарь

| Группа       | Сервер                              |
|-------------|-------------------------------------|
| webservers  | server1 (193.32.216.239)            |
|             | server2 (111.88.152.169)            |
| appservers  | 111.88.152.169                      |
