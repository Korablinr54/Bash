# Просмотр файла: `cat`
Команда хорошо подходит для знакомтсва с содержимым файла:
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # проверям содержимое папки
text.txt

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat text.txt # смотрим на содержимое файла
Привет! Я изучаю bash. # вывод
```
Помимо просмотра, команда `cat` может создавать файлы:
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat > test_file.txt # создаем новый файл указав его имя
'Привет! Что ты изучаешь?' # вводим в него текст и завершаем Ctrl + d
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # смотрим на список файлов и видим новый файл, который создали
test_file.txt  text.txt

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat test_file.txt # открываем файл и видим наш текст
Привет! Что ты изучаешь?
```
А еще `cat` может дописать один файл в другой, или добавить строку, переданную команде:  
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat > test_file.txt
Привет! Что ты изучаешь?

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat text.txt >> test_file.txt 

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat >> test_file.txt 
Что у вас здесь происходит?

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat test_file.txt 
Привет! Что ты изучаешь?
Привет! Я изучаю bash.
Что у вас здесь происходит?
```