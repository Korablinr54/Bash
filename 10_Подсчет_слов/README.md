# Команда wc
Используется для подсета слов и неплохо работает вместе с `find` и `grep`.

Основные опции wc:  
- `-m` — общее количество символов (включая пробелы);  
- `-w` — количество слов в файле;  
- `-l` — количество строк в файле;  
- `-L` — величина самой длинной строки;  
- `-c` — размер файла в байтах.  

## Примеры

### Общее количество символов `-m`
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ wc -m poem.txt
221 poem.txt
```

### Общее количество слов `-w`
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ wc -w poem.txt
39 poem.txt
```

### Общее количество строк `-l`
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ wc -l poem.txt
9 poem.txt
```

### Самая длинная строка `-L`
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ wc -L poem.txt
28 poem.txt
```

### Размер файла в битах `-c`
```sh
user@WIN-CVKT899RCS2 MINGW64 /d/learn
$ wc -c poem.txt
385 poem.txt
```