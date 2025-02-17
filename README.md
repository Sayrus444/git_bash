# Работа с bash
Знаком с базовыми командами bash. В процессе работы через командную строку были созданы, перемещены и удалены файлы и каталоги. Также была выполнена работа по редактированию содержимого файлов, поиску необходимой информации внутри них и выводу данных на экран. Помимо этого, были осуществлены действия по проверке сетевых настроек и взаимодействию с сетью с помощью специализированных команд.

[Базовые команды в Bash (задание №1)](https://github.com/Sayrus444/git_bash/blob/main/bash1.txt)

[Базовые команды в Bash (задание №2)](https://github.com/Sayrus444/git_bash/blob/main/bash2.txt)


## Задание №1

```bash

# 1) Определить имя папки, в которой вы находитесь
pwd

# 2) Создать внутри этой папки каталог с именем test1
mkdir test1

# 3) Перейти в папку test1
сd test1

# 4) Создать файл 1,2 и 3 внутри каталога test1
touch file1.txt 
touch file2.txt 
touch file3.txt

# 5) Проверить содержимое каталога test1
ls

# 6) Перейти в домашнюю директорию
cd ..

# 7) Создать папку test2 внутри домашней директории
mkdir test2

# 8) Удалить папку test2
rm -r test2

# 9) Удалить файл 2 из папки test1
cd test1
rm file2.txt

# 10) Создать папку в домашней директории test3 и добавить в нее два файла
cd ..
mkdir test3
cd test3
touch file1.txt
touch file2.txt

# 11) Удалить папку test3
cd ..
rm -r test3

# 12) Создать папку test4 в домашней директории
mkdir test4

# 13) Переместить файлы 1 и 3 из папки test1 в папку test4
mv test1/file1.txt test1/file3.txt test4/


# 14) Добавить в файл 1 три строки со словами line
cd test4
echo "line" >> file1.txt
echo "line" >> file1.txt
echo "line" >> file1.txt


# 15) Посмотреть содержимое файла 1
cat file1.txt


# 16) Добавьте в файл 3 три строки со словами line
echo "line" >> file3.txt
echo "line" >> file3.txt
echo "line" >> file3.txt


# 17) Просмотрите содержимое двух файлов (1 и 3) сразу
cat file1.txt file3.txt


# 20) Используя один из редакторов замените все строки в файле 1
echo no line > file1.txt
echo no line >> file1.txt
echo no line >> file1.txt
```





## Задание №2

```bash

# 1) Создать папку test 3
mkdir test3

# 2) Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4
cd test3
touch file4.txt
echo "row1" >> file4.txt (4 раза)
echo "row2" >> file4.txt (4 раза)
echo "row3" >> file4.txt (4 раза)
echo "row4" >> file4.txt (4 раза)
cp file4.txt file5.txt
cp file4.txt file6.txt

# 3) Найдите строку row2 в файле 5
grep "row2" file5.txt

# 4) Найдите строку row в папке test3
cd ..
grep -r "row" test3

# 5) Посчитайте сколько строк с содержимым row в файле 6
cd test3
grep -c "row" file6.txt

# 6) Найдите файл 5 внутри папки test3
cd ..
find test3 -name "file5.txt"

# 7) Используя команду find, удалите файл 5
find test3 -name "file5.txt" -exec rm {} \;

# 8) Используя команду echo, добавьте слово test в файл 4 (без сохранения содержимого)
cd test3
echo test > file4.txt

# 9) Замените слово test в файле 4 на fail
sed -i 's/test/fail/g' file4.txt

# 10)Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
echo test >> file4.txt

# 11) Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
ps / ps aux / top

# 12) Убейте процесс 666 в консоли (можно не убивать, а просто написать команду)
kill 666

# 13) Узнайте доступность ресурса rusau.net, используя ping
ping rusau.net

# 14) Отправьте 5 пакетов на сайт rusau.net
ping -n 5 rusau.net (ping -c 5 rusau.net не сработал, требуется права администратора)

# 15) Используя GET и команду curl, получите информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/
echo "Available pets:"
curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=available" -H "accept: application/json"

echo "Pending pets:"
curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=pending" -H "accept: application/json"

echo "Sold pets:"
curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=sold" -H "accept: application/json"

echo " pets:"
curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=" -H "accept: application/json"

# 16) Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
curl -X 'POST' \
  'https://petstore.swagger.io/v2/user' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 44,
  "username": "Test",
  "firstName": "Test",
  "lastName": "Tester",
  "email": "test@mail.ru",
  "password": "123456",
  "phone": "+79999999999",
  "userStatus": 1
}'

```
