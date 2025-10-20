# tar

tar (tape archive) - архиватор. Изначально создавался как инструмент для резервного копирования.  

Основные ключи:  
- `c` — создать архив
- `x` — извлечь файлы из архива
- `v` — подробный вывод
- `z, j, J` — тип сжатия gzip, bzip2, xz
- `f` — присвоить имя
- `t` — просмотр содержимого архива

## Создание архива

Важно! Опции всегда должны пыть переданы до названий файлов или путей!  
Давайте создадим архив.
```sh
# архива нет, только файл
root@633916c9fb8a:/archive_test# ls
file.txt

# создаем архив
root@633916c9fb8a:/archive_test# tar -czvf archive.tar.gz ./file.txt
./
./file.txt
tar: .: file changed as we read it

# теперь есть архив и файл
root@633916c9fb8a:/archive_test# ls
archive.tar.gz  file.txt
```
* `tar` - вызов утилиты
* `с` - создать архив
* `z` - указан тип сжатия gzip
* `v` - выводить подробную информацию о процессе
* `f` - указать ия архива archive.tar.gz
* `./file.txt` - поместить в текущей директории

Для создания архивая не в текущей папке а в любой другой:
```sh
# проверяем список файлов 
root@633916c9fb8a:/archive_test# ls
file.txt

# создаем тестовую папку
root@633916c9fb8a:/archive_test# mkdir archive_test

# создаем архив
root@633916c9fb8a:/archive_test# tar -czvf ./archive_test/arc.tar.gz file.txt 
file.txt

# проверяем наличие архива
root@633916c9fb8a:/archive_test# ls archive_test/
arc.tar.gz
```

* `tar -czvf` - вызов утилиты с ключами
* * `./archive_test/arc.tar.gz` - куда сохраняем архив с его именем
* * `file.txt` - что архивируем, можно также указать путь