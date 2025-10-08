# Команда grep

**grep** - это мощная утилита для поиска текста в файлах и потоках данных.

Синтаксис:  
```sh
grep [опции] "шаблон" [файлы]
```

## Поиск в файлах
```sh

# поиск в одном файле
user@WIN-CVKT899RCS2 MINGW64 /d
$ grep 'Ты' d:/learn/poem.txt
Ты и Вы

# поиск в нескольких файлах
user@WIN-CVKT899RCS2 MINGW64 /d
$ grep 'Ты' d:/learn/poem.txt d:/learn/some_file
d:/learn/poem.txt:Ты и Вы

# поиск в директории `-r`
user@WIN-CVKT899RCS2 MINGW64 /d
$ grep 'Ты' -r d:/learn
d:/learn/poem.txt:Ты и Вы

# игнорирование регистра `-i`
user@WIN-CVKT899RCS2 MINGW64 /d
$ grep 'Ты' -ri d:/learn
d:/learn/poem.txt:Ты и Вы
d:/learn/poem.txt:Пустое вы сердечным ты
d:/learn/poem.txt:И все счастливые мечты

# указание номера строки `-n`
user@WIN-CVKT899RCS2 MINGW64 /d
$ grep 'Ты' -ri -n d:/learn
d:/learn/poem.txt:1:Ты и Вы
d:/learn/poem.txt:2:Пустое вы сердечным ты
d:/learn/poem.txt:4:И все счастливые мечты
```