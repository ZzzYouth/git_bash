# 📌 Работа с git и bash

Иногда нам нужно работать с удаленными серверами, которые не имеют графического интерфейса. В этом случае хорошо иметь возможность использовать команды bash. Они позволяют нам выполнять обычные действия, такие как создание, редактирование, удаление файлов и папок через CLI.

Я с радостью поделюсь некоторыми командами bash, которые я использовал для выполнения задач во время обучения по программе «Обеспечение качества».

## Ссылки на файлы

- [Задача 1](https://github.com/ZzzYouth/git_bash/blob/main/bash1.txt.txt)

- [Задача 2](https://github.com/ZzzYouth/git_bash/blob/main/bash2.txt.txt)

## Задача 1

##### Работа с файлами и каталогами
```bash
~                                                                              # Открыть домашнюю директорию через терминал 
pwd                                                                            # Определить имя папки, в которой вы находитесь
mkdir test1                                                                    # Создать внутри этой папки каталог с именем test1
cd test1                                                                       # Перейти в папку test1
touch file1.txt file2.txt file3.txt                                            # Создать файл 1,2 и 3 внутри каталога test1
ls                                                                             # Проверить содержимое каталога test1 
cd                                                                             # Перейти в домашнюю директорию
mkdir test2                                                                    # Создать папку test2 внутри домашней директории
rmdir test2                                                                    # Удалить папку test2
rm ~/test1/file2.txt                                                           # Удалить файл 2 из папки test1
cd && mkdir test3 && cd test3 && touch test1.txt test2.txt                     # Создать папку в домашней директории test3 и добавить в нее два файла 
cd && rm -r ~/test3                                                            # Удалить папку test3
mkdir test4                                                                    # Создать папку test4 в домашней директории
~/test1/file1.txt ~/test1/file3.txt ~/test4/                                   # Переместить файлы 1 и 3 из папки test1 в папку test4
echo -e "line 1\nline 2\nline 3" >> ~/test4/file1.txt                          # Добавить в файл 1 три строки со словами line  
cat ~/test4/file1.txt                                                          # Посмотреть содержимое файла 1
echo -e "line 1\nline 2\nline 3" >> ~/test4/file3.txt                          # Добавьте в файл 3 три строки со словами line
echo -e "новая строка 1\nновая строка 2\nновая строка 3" > ~/test4/file1.txt   # Используя один из редакторов замените все строки в файле 1

```
## Задача 2
##### Редактирование файлов, проверка и завершение процессов, пингование веб-сайтов
```bash
cd ~                                                                     # Зайти в домашнюю директорию через терминал 
mkdir test3                                                              # Создать папку test3

    cd test3                                                             # Добавить в папку test3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4
    touch file4.txt file5.txt file6.txt
    echo -e "row1\nrow2\nrow3\nrow4" > ~/test3/file4.txt
    echo -e "row1\nrow2\nrow3\nrow4" > ~/test3/file5.txt
    echo -e "row1\nrow2\nrow3\nrow4" > ~/test3/file6.txt  
grep "row2" ~/test3/file5.txt                                             # Найдите строку row2 в файле 5                               
grep "row" ~/test3/file5.txt                                              # Найдите строку row в папке test3
grep -c "row" ~/test3/file6.txt                                           # Посчитайте сколько строк с содержимым row в файле 6
find ~/test3 -name "file5.txt"                                            # Найдите файл 5 внутри папки test3
find ~/test3 -name "file5.txt" -exec rm {} \;                             # Используя команду find, удалите файл 5
echo "test" >> ~/test3/file4.txt                                          # Используя команду echo, добавьте слово test в файл 4
sed -i 's/test/fail/g' ~/test3/file4.txt                                  # Замените слово test в файле 4 на fail
$ echo "test" >> ~/test3/file4.txt                                        # Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
ps aux                                                                    # Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
kill 666                                                                                              # Убейте процесс 666 в консоли (можно не убивать, а просто написать команду)
ping rusau.net                                                                                        # Узнайте доступность ресурса rusau.net, используя ping
ping -n 5 rusau.net                                                                                   # Отправьте 5 пакетов на сайт rusau.ne
                                      
           # Используя GET и команду curl, получите информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/

             curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=available" -H "accept: application/json"

                     # Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/

curl -X POST "https://petstore.swagger.io/v2/user" \
> -H "Content-Type: application/json" \
> -d '{
>   "id": 0,
>   "username": "newuser",
>   "firstName": "John",
>   "lastName": "Doe",
>   "email": "john.doe@example.com",
>   "password": "password123",
>   "phone": "1234567890",
>   "userStatus": 1
> }'
hone": "1234567890",\x0a"userStatus": 1\x0a}';9001acf2-e978-48af-b72d-9664a0b3f2d9{"code":200,"type":"unknown","message":"9223372036854775807"}
```
