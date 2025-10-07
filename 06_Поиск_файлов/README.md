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
find: ‘d:/$RECYCLE.BIN/S-1-5-18’: Permission denied
find: ‘d:/Config.Msi’: Permission denied
d:/learn/some_file # результаты с подстройок some
d:/learn/some_folder # 
d:/Program Files/Python/Lib/site-packages/scipy/io/matlab/tests/data/some_functions.mat
find: ‘d:/System Volume Information’: Permission denied
find: ‘d:/TEMP/msdtadmin’: Permission denied
```

<br>

Найдем отдельно файлы и отдельно директории:
```bash

```