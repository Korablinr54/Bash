# Команда sort

В случае, если сортировка по-умолчанию нас почему-то не устраивает мы можем это исправить используяю команду `sort`.

Основные ключи:  
- `-n`: сортирует численно.  
- `-r`: обратный порядок сортировки.  
- `-u`: удаляет дублирующиеся строки.  

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