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

# Определение типпа файла `file`
Команда явно определит тип файла вне зависимости от его расширения.
```sh
# здесь все понятно, это pdf
user@WIN-CVKT899RCS2 MINGW64 /d
$ file learn/big_file.pdf
learn/big_file.pdf: PDF document, version 1.3, 1 page(s)

# а что в этом странном файле?
user@WIN-CVKT899RCS2 MINGW64 /d
$ file learn/photo.exe # выглядит как подвох
learn/photo.exe: ASCII text
# всего лишь текстовый файл
```