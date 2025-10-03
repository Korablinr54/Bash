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
# Объединение файлов
`cat` позволяет нам также объединять файлы:  
```bash
# Просматриваем файлы в текущей директории
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls
content.txt  test_file.txt  text.txt

# ОБЪЕДИНЕНИЕ ФАЙЛОВ: создаем merged.txt, содержащий содержимое ДВУХ файлов
# ПОРЯДОК ФАЙЛОВ ВАЖЕН: сначала content.txt, потом test_file.txt
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat content.txt test_file.txt > merged.txt

# Проверяем - появился новый файл merged.txt
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ ls
content.txt  merged.txt  test_file.txt  text.txt

# Смотрим содержимое объединенного файла
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat merged.txt 
content.txt          # ← из content.txt
test_file.txt        # ↓
text.txt             # ↓
Bash/                # ↓
DBT/                 # ↓  
Docker/              # ↓
GIT/                 # ↓
Memories/            # ↓
py_data/             # ↓
Python/              # ↓
SQL/                 # ↓
Привет! Что ты изучаешь?           # ← из test_file.txt
Привет! Я изучаю bash.Что у вас здесь происходит?  # ↓
```
Аналогично мы можем дописать один файл в другой:  
```bash
# ДОБАВЛЯЕМ содержимое файла text.txt в КОНЕЦ merged.txt
# Используется оператор >> (добавление), а не > (перезапись)
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat text.txt >> merged.txt

# Просматриваем обновленное содержимое merged.txt
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ cat merged.txt 
content.txt                          # ← из content.txt
test_file.txt                        # ↓
text.txt                             # ↓
Bash/                                # ↓
DBT/                                 # ↓  
Docker/                              # ↓
GIT/                                 # ↓
Memories/                            # ↓
py_data/                             # ↓
Python/                              # ↓
SQL/                                 # ↓
Привет! Что ты изучаешь?             # ← из test_file.txt
Привет! Я изучаю bash.Что у вас здесь происходит?  # ↓
Привет! Я изучаю bash.               # ← ДОБАВЛЕНО из text.txt (последняя строка)
```
# Постраничный просмотр: `less`
```bash
# Открываем файл для просмотра в less
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ less merged.txt
```
`Основные клавиши навигации в less:`  

**Перемещение по файлу**:  
- Пробел или Page Down - следующая страница  
- b или Page Up - предыдущая страница  
- ↓ или Enter - следующая строка  
- ↑ - предыдущая строка   

**Быстрая навигация:**  
- g - перейти в начало файла  
- G - перейти в конец файла  
- 50g - перейти к строке 50  
- /привет - поиск слова "привет" (вперед)  
- ?привет - поиск слова "привет" (назад)  
- n - следующий результат поиска  
- N - предыдущий результат поиска  

```bash
# Открываем большой файл
user@WIN-CVKT899RCS2 MINGW64 /d/learning
$ less large_file.txt

# Внутри less:
- Нажимаем **/error** чтобы найти все ошибки
- Нажимаем **n** чтобы перейти к следующему совпадению
- Нажимаем **G** чтобы перейти в конец файла
- Нажимаем **g** чтобы вернуться в начало
- Нажимаем **q** чтобы выйти
```