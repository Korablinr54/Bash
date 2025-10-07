# Команда find
Синтаксис `find <directory> <options> <action>`:   
- `<directory>` (Директория): Исходная точка для поиска. Задаёт, в каком месте файловой системы начинать сканирование.  
- `<options>` (Параметры): Критерии отбора, которым должны удовлетворять искомые файлы и каталоги (например, по имени, размеру или правам доступа).    
- `<action>` (Действие): Операция, производимая с каждым найденным объектом. 

Популярные ключи:  
| Ключ | Что делает | Пример использования |
|------|------------|-----------------------|
| `-name` | Поиск по имени | `find . -name "*.txt"` |
| `-type` | Поиск по типу (f-файл, d-папка) | `find /var -type d` |
| `-size` | Поиск по размеру | `find . -size +10M` |
| `-mtime` | Поиск по дате изменения (в днях) | `find /home -mtime -7` |
| `-user` | Поиск по владельцу | `find /tmp -user john` |
| `-exec` | Выполнить команду для найденного | `find . -name "*.log" -exec rm {} \;` |

# Примеры

## Поиск по имени
```sh
# найдем все записи с подстрокой some в имени
user@WIN-CVKT899RCS2 MINGW64 /d
$ find d:/ -name some_*

d:/learn/some_file # результаты с подстройок some
d:/learn/some_folder
```

<br>

Найдем отдельно файлы и отдельно директории:
```bash
$ find d:/ -name some_* -type f # для поиска файлов

d:/learn/some_file # наш файл

user@WIN-CVKT899RCS2 MINGW64 /d
$ find d:/ -name some_* -type d # для поиска директорий
d:/learn/some_folder
```

## Поиск по размеру

Варианты:  
- +100M - больше 100 МБ  
- -100M - меньше 100 МБ  
- 100M - ровно 100 МБ  

Найдем наш файл, указав, что ищем именно файл размером менее 1 МБ.
```sh
$ find d:/ -name some_* -type f -size -1M
d:/learn/some_file
```

## Поиск пустых файлов и папок

Поиск пустых файлов:
```sh
$ find d:/ -name some_* -type f -empty
d:/learn/some_file
```

Поиск пустых файлов:
```sh
$ find d:/ -name some_* -type d -empty
d:/learn/some_folder
```

# Поиск файлов, доступных для чтения
```sh
$ find d:/learn/ -readable
d:/learn/
d:/learn/some_file
d:/learn/some_folder

# поиск файлов, доступных для чтения в директории
$ find d:/learn/ -readable -type f
d:/learn/some_file

# поиск папок, доступных для чтения 
user@WIN-CVKT899RCS2 MINGW64 /d
$ find d:/learn/ -readable -type d
d:/learn/
d:/learn/some_folder
```