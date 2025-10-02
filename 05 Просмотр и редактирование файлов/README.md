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
# Перенаправление вывода: `>` и `>>`
Например, мы можем вывод любой команды записать или дописать в файл. Давайте содержимое директории сохраним в файл:  
```bash
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # проверим содержимое директории
test_file.txt  text.txt

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls > content.txt # передадим результат вывода в новый файл

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls # видим, что новый файл появился в директории
content.txt  test_file.txt  text.txt

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat content.txt # и он содержит список файлов директории
content.txt
test_file.txt
text.txt
```
Теперь мы допишем в наш созданный файл вывод команды:  
```bash
$ ls d:/git >> content.txt # через >> дописываем вывод содержимого из другой директории

user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat content.txt # смотрим на результат 
content.txt 
test_file.txt 
text.txt
Bash/ # отсюда начинаются новые строки, которые мы дописали
DBT/
Docker/
GIT/
Python/
SQL/
```