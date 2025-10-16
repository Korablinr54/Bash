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
