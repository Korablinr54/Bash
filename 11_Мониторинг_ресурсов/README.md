# Размер файла или каталога `du`
Команда используется для оценки размера каталога или отдельного файла.
Основные ключи:  
- `-h` показывает размер в удобных единицах  
- `-a` отдельное отражения размера каждого файла в директории.  
```sh
# сам по себе вызов du не очень информативен
# для директории
user@WIN-CVKT899RCS2 MINGW64 /d
$ du learn/
0       learn/some_folder
7508    learn/

# для файла
user@WIN-CVKT899RCS2 MINGW64 /d
$ du learn/'big file.pdf'
7504    learn/big file.pdf
```

Запустим с упомянутыми ключами:
```sh
# совем другое дело
user@WIN-CVKT899RCS2 MINGW64 /d
$ du learn/ -ah
7.4M    learn/big file.pdf
1.0K    learn/numbers.txt
1.0K    learn/poem.txt
1.0K    learn/some_file
0       learn/some_folder
1.0K    learn/sort_file.txt
7.4M    learn/ # общий размер папки

# а можно через | pipe, например добавить сортировку
user@WIN-CVKT899RCS2 MINGW64 /d
$ du learn/ -ah | sort -r
7.4M    learn/big file.pdf
7.4M    learn/
1.0K    learn/sort_file.txt
1.0K    learn/some_file
1.0K    learn/poem.txt
1.0K    learn/numbers.txt
0       learn/some_folder
```

# Анализ места на диске `df`
Для анализа доступного пространства на диске необходимо использовать `df -hT`. `-h` отобразит данные в удобном формате а `-T` сообщит информацию о файловой системе.  
```sh
user@WIN-CVKT899RCS2 MINGW64 /d
$ df -hT
Filesystem           Type  Size  Used Avail Use% Mounted on
D:/Program Files/Git ntfs  269G  185G   85G  69% /
C:                   ntfs  198G  103G   96G  52% /c
E:                   ntfs   10G  8.4G  1.7G  84% /e
```