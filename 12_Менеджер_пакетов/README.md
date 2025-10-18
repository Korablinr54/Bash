# Менеджер пакетов apt

## Установка программ `apt install`

Для установки пакета программ используется приложение `apt`:
```sh
root@69b01309ee03:/# apt install terminator
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
...
Progress: [ 82%] [#######################################################......................]
...
done.
```

### Проблема с установкой
При установке пакета может возникнуть ошибка. Ошибка `E: Unable to locate package terminator` означает, что пакетный менеджер APT не может найти пакет terminator в доступных репозиториях. Причин может быть несколько, мы попробуем обновить менеджер пакетов, в нашем случае это поможет.  

### Обновление списка доступных пакетов `apt update`

`apt update` (Обновление списка пакетов)
- **Что делает?** Эта команда обращается к репозиториям (специальным серверам, откуда качаются программы) и запрашивает свежий список доступных пакетов и их версий. Она не устанавливает никакие обновления.

- **Как работает?** Она обновляет локальную базу данных на вашем компьютере, сверяя ее с данными на серверах. После выполнения вы увидите список репозиториев, с которых были получены данные.

- **Зачем это нужно?** Система должна знать, какие вообще существуют новые версии программ. Без этой команды apt просто не будет в курсе, что вышло обновление для, скажем, Firefox или ядра системы.

- **Когда выполнять?** Перед каждым apt upgrade. Это хорошая практика.

```sh
root@69b01309ee03:/# apt update
Get:1 http://archive.ubuntu.com/ubuntu noble InRelease [256 kB]
...
Get:18 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Packages [33.9 kB]
Fetched 34.0 MB in 4s (7974 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
2 packages can be upgraded. Run 'apt list --upgradable' to see them.
```

### Обновление всех установленных пакетов `apt upgrade`

`apt upgrade` (Установка обновлений)
- **Что делает?** Эта команда скачивает и устанавливает все доступные обновления для уже установленных в системе пакетов. Она использует актуальный список пакетов, который был получен с помощью apt update.

- **Как работает?** Она сравнивает версии установленных пакетов с теми, что есть в обновленном списке, и предлагает обновить их до новых версий.

- **Важный нюанс**: Эта команда НЕ удаляет старые пакеты и НЕ устанавливает новые пакеты, если они требуются для обновления (если только они не конфликтуют с существующими). Это "безопасное" обновление.  

**Правильная последовательность действий**  

Всегда выполняйте эти команды по порядку:
```sh
sudo apt update
sudo apt upgrade
```

## Удаление `apt remove`

Таким же обрпазом удалим то, что установили. `apt remove название пакета`.
```sh
root@69b01309ee03:/# apt remove terminato
Removing terminator (2.1.3-1) 
...
```

## Поиск информации о пакете `apt search`

```sh
root@69b01309ee03:/# apt search bash
```

## Справка по пакету `apt help`

Просмотр справки по пакету можно вызвать таким образом:
```sh
root@69b01309ee03:/# apt help bash
apt 2.8.3 (amd64)
Usage: apt [options] command

apt is a commandline package manager and provides commands for
searching and managing as well as querying information about packages.
It provides the same functionality as the specialized APT tools,
like apt-get and apt-cache, but enables options more suitable for
interactive use by default.

Most used commands:
  list - list packages based on package names
  search - search in package descriptions
  show - show package details
  install - install packages
  reinstall - reinstall packages
  remove - remove packages
  autoremove - automatically remove all unused packages
  update - update list of available packages
  upgrade - upgrade the system by installing/upgrading packages
  full-upgrade - upgrade the system by removing/installing/upgrading packages
  edit-sources - edit the source information file
  satisfy - satisfy dependency strings

See apt(8) for more information about the available commands.
Configuration options and syntax is detailed in apt.conf(5).
Information about how to configure sources can be found in sources.list(5).
Package and version choices can be expressed via apt_preferences(5).
Security details are available in apt-secure(8).
                                        This APT has Super Cow Powers.
```

## Популярные команды

| Команда | Назначение | Практическое применение | Пример использования |
|---------|------------|-------------------------|----------------------|
| **`apt update`** | Синхронизирует локальную базу данных пакетов с удаленными репозиториями | Подготовка системы к обновлению, получение актуальной информации о доступных версиях | `sudo apt update` - проверяет наличие новых версий пакетов |
| **`apt upgrade`** | Безопасное обновление установленного ПО до новых версий без изменения структуры зависимостей | Регулярное обслуживание системы, установка исправлений безопасности | `sudo apt upgrade` - обновляет все установленные пакеты |
| **`apt install`** | Добавление нового программного обеспечения в систему | Установка приложений, утилит или системных компонентов | `sudo apt install nginx` - устанавливает веб-сервер nginx |
| **`apt remove`** | Деинсталляция пакета с сохранением пользовательских настроек | Временное удаление программы с возможностью восстановления конфигурации | `sudo apt remove apache2` - удаляет Apache, оставляя файлы настроек |
| **`apt purge`** | Полное удаление пакета со всеми сопутствующими файлами | Окончательная очистка системы от нежелательного ПО | `sudo apt purge mysql-server` - полностью стирает MySQL с настройками |
| **`apt autoremove`** | Очистка от orphaned-пакетов (неиспользуемых зависимостей) | Освобождение дискового пространства после удаления программ | `sudo apt autoremove` - убирает ненужные библиотеки |
| **`apt search`** | Поиск программного обеспечения в репозиториях | Нахождение нужных утилит или приложений по ключевым словам | `apt search text-editor` - ищет текстовые редакторы |
| **`apt show`** | Детальная диагностика информации о конкретном пакете | Изучение характеристик пакета перед установкой | `apt show python3` - показывает данные о Python 3 |
| **`apt clean`** | Глубокая очистка кеша загруженных DEB-файлов | Радикальное освобождение места в системном разделе | `sudo apt clean` - удаляет все загруженные пакеты |
| **`apt list`** | Инвентаризация установленных или доступных пакетов | Аудит системы, проверка установленного ПО | `apt list --installed` - перечисляет все установленные пакеты |
| **`apt full-upgrade`** | Комплексное обновление системы с разрешением сложных зависимостей | Переход между major-версиями дистрибутивов, критичные обновления | `sudo apt full-upgrade` - выполняет полное обновление системы |

# Менеджер dpkg 

Основное отличие:  
- **DPKG** — низкоуровневая система управления пакетами (работает с отдельными `*.deb` файлами)  
- **APT** — высокоуровневая система управления пакетами (работает с репозиториями и зависимостями)  
  
## Установка пакета `-i`

Например, мы хотим установить some_app приложение. Для этого выполним:
```sh
dpkg -i some_app.deb
```

## Удаление пакета `-r`
Для удаления установленного пакета достаточно воспользоваться:
```sh
# Сначала проверяем, что пакет установлен
dpkg -l | grep some_app

# Затем удаляем
dpkg -r some_app

# Проверяем, что пакет удален
dpkg -l | grep some_app
```

## Решение проблем с зависимостями `-f`

При установке пакета может возникнуть ситуация отсуствия необходимых библиотек, в этом случае нам поможет `-f`
```sh
# Пытаемся установить пакет с зависимостями
dpkg -i some_app.deb

# Если возникает ошибка зависимостей:
# "dpkg: dependency problems prevent configuration..."
apt install -f
```

## Информаиця о пакете `-l`

```sh
# Поиск по точному имени
dpkg -l some_app

# Поиск по шаблону (очень полезно!)
dpkg -l "*some_app*"
dpkg -l "*chrome*"
dpkg -l "*python*"

# или вернуть список всех пакетов
dpkg -l
```

# Менеджер snap