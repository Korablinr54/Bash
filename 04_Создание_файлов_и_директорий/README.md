# Создание файлов и директорий

## Создать директорию: `mkdir`
Создать директорию можно командой `mkdir`. Для создания иерархий директорий используем флаг `-п`:  
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls -l # проверяем текущую директорию и убеждаемся, что она пуста
total 0

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ mkdir test_folder # создаем папку

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls -l # снова проверяем и видим нашу новую папку
total 0
drwxr-xr-x 1 user 197121 0 Oct  1 15:49 test_folder/

# или создать иерархию папок 
# флаг -p позволяет создавать иерархии папок

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ mkdir -p level_1/level_2/level_3 # создаем иерархию с флагом -р

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ mkdir -p level_1/level_2/level_3/hierarchy_test_file # добавим туда файл

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls level_1/level_2/level_3 # убедимсмя, что иерархия создана и в ней лежит файл
hierarchy_test_file/
```

## Создание пустого файла: `touch`
С помощью команды `touch` мы можем создать пустой файл как в текущей директории так и в какой-либо структуре:  
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # смотрим на содержимое директории  
level_1/  test_folder/

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ touch current_dir_file # создаем пустой файл в текущей директории

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ touch level_1/level_2/hierarchy_test_file # создаем файл в иерархии

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # убеждаемся, что файл есть в текущей директории
current_dir_file  level_1/  test_folder/

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls level_1/level_2/ # убеждаемся, что файл есть в иерархии
hierarchy_test_file  level_3/
```

## Удаление пустой папки: `rmdir`
Команда `rmdir` используется для удаления пустой директории. Это удобно, т.к. можно быть увереным в том, что случайно не удалишь нужные файлы при удалении ненужных пустых папок:
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # смотрим на содержимое папки
current_dir_file  level_1/  test_folder/

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ rmdir level_1/ # пытаемся удалить иерархию папок и поулчаем ошибку
rmdir: failed to remove 'level_1/': Directory not empty

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ rmdir test_folder/ # удаляем пустую папку - успешно

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # пустая папка удалена, папка с вложениями осталась
current_dir_file  level_1/
```

## Рекурсивное удаление с содержимым: `rm -r`
Если мы уверены, что необходимо удалить всю иерархию со всем ее содержимым или просто удалить конкретный файлы, то мы используем `rm`:  
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # смотрим на содержимое
current_dir_file  level_1/

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ rm current_dir_file # удаляем файл

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # файл был успешно удален
level_1/

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ rm -r level_1/ # удаляем структуру папок

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # проверяем содержимое

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ # и файл и структура папок с файлами внутри были удалены
```

