# wget

Wget — консольная программа для получения данных из сети, работающая без графического интерфейса. Позволяет напрямую из терминала загружать контент с веб-ресурсов.

Ключевые возможности:  
- Загрузка одиночных файлов по URL-адресам

- Автоматическое возобновление при обрыве соединения

- Рекурсивное скачивание целых веб-сайтов со всеми связанными ресурсами

- Ограничение скорости для предотвращения перегрузки канала

- Работа в фоновом режиме без вмешательства пользователя

**Базовый синтаксис и параметры**
```sh
# Стандартная загрузка
wget https://example.com/document.pdf

# Продолжение прерванной загрузки
wget -c https://example.com/large_file.iso

# Рекурсивное скачивание сайта
wget -r --level=2 https://example-site.com
```

## Практические сценарии использования

### Загрузка с переименованием

```sh
wget -O dataset.csv "https://api.example.com/data/export?format=csv"
```

### Ограничение скорости загрузки

```sh
wget --limit-rate=1M https://mirror.example.com/ubuntu-22.04.iso
```

### Скачивание в фоновом режиме

```sh
wget -b -q https://example.com/large-video.mp4
```

## Примеры установки ПО

### Загрузка пакетов для последующей установки:

```sh
# Получение пакета Zoom
wget https://zoom.us/client/latest/zoom_amd64.deb

# Скачивание архива VLC
wget https://get.videolan.org/vlc/3.0.18/vlc-3.0.18.tar.xz

# Загрузка браузера Chrome
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

### Установка загруженных .deb пакетов:

```sh
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt install -f  # Установка зависимостей
```