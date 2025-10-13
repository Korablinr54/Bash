# Команда sort

В случае, если сортировка по-умолчанию нас почему-то не устраивает мы можем это исправить используяю команду `sort`.

Основные ключи:  
- `-n`: числовая сортировка.  
- `-r`: обратный порядок.  
- `-u`: без дубликатов.  

Посмотрим на практике:
```sh
# отправляемся в директорию
user@WIN-CVKT899RCS2 MINGW64 ~
$ cd d:/leanr

# возвращаем список файлов
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ ls
poem.txt  some_file  some_folder/

# создаем новый файл в редакторе nano
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ nano sort_file.txt

# ага, файл появился
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ ls
poem.txt  some_file  some_folder/  sort_file.txt # вот

# читаем файл
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ cat sort_file.txt
banana
apple
orange
pineaple
tomato
potato
pepper
linux_1
linux
linux_test
1
2
3
4
5

```

## Примеры 
### Обычная сортировка
Обычная сортировка:
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ sort sort_file.txt
1 # по возрастанию
2
3
4
5
apple # а дальше в лексикографическом порядке 
banana
linux
linux_1
linux_test
orange
pepper
pineaple
potato
tomato
```

### -r (в обратном порядке)
Обратная сортировка:
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ sort sort_file.txt -r
tomato
potato
pineaple
pepper
orange
linux_test
linux_1
linux
banana
apple
5
4
3
2
1
```

### -u (без дубликатов)
Сортировка с удалением дубликатов:
```sh
# добавим дубликатов
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ nano sort_file.txt

# посмотрим на файл
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ cat sort_file.txt
banana
apple # 
apple # дубль
apple # дубль
orange
pineaple
tomato
potato
pepper
linux_1
linux
linux_test
1
2
3
4
5

# а теперь отсортируем файл с ключом -u
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ sort -u sort_file.txt
1
2
3
4
5
apple # дубликатов нет
banana
linux
linux_1
linux_test
orange
pepper
pineaple
potato
tomato
```

### -n (числовая сортировка)
```sh
# создадим новый файл
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ nano numbers.txt

# взглянем на него
# обычная сортировка бесполезна
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ sort numbers.txt
1
10
2
22
3
apple

# используем ключ -n и -r для обратной сортировки
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ sort -nr numbers.txt
22
10
3
2
1
apple
```