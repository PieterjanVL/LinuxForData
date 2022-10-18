info: naar een package zoeken: apt search php

## Eerste deel:

1. installatie: sudo apt install apache2 libapache2-mod-php php php-mysql
2. debian niet nodig start enable automatisch gdn!, redhad wel
3. controleren apache draaien: systemctl status apache2
4. Surf naar http://localhost/ we zien dat apache aan het draaien is
5. osboxes@osboxes:~$ cd /var/www/ => de standaard html locatie van apache
6. osboxes@osboxes:/var/www/html$ sudo nano info.php
7. in de info.php schrijven <?php phpinfo(); ?> control x opslaan
8. surfen naar http://localhost/info.php => debuggen php, in terminal php info.php
9. installeren: sudo apt -y install mariadb-server
10. status  systemctl mariadb
11. verwijderen testdb: sudo mysql_secure_installation
12. yes, yes, no, yes, yes
13. inloggen db mariadb: sudo mysql, eruit control d
14. MariaDB [(none)]>  none is de huidige db
15. Opvragen alle datatbanken: MariaDB [(none)]> show databases;
16. Veranderen naar db mysql, MariaDB [(none)]> show databases;
17. MariaDB [mysql]> select user, host, password from user; opvragen gebruikers
18. osboxes@osboxes:/var/www/html$ sudo mysql mysql, direct inloggen op de db mysql
19. toevoegen eerste script
20. uitvoeren osboxes@osboxes:~$ sudo mysql < init-db.sql 
21. testen of db bestaat osboxes@osboxes:~$ sudo mysql www_db
22. MariaDB [www_db]> show tables;
23. MariaDB [www_db]> select * from todo_list;
24. inloggen met user www_user wachtwoord hogen2022 op db www_db: osboxes@osboxes:~$ mysql -uwww_user -phogent2022 www_db
25. osboxes@osboxes:~$ mysql -uwww_user -phogent2022 www_db << _EOF_ om queuries uit te voeren
26. osboxes@osboxes:~$ mysql -uwww_user -phogent2022 www_db << _EOF_
> select * from todo_list;
<br>> _EOF_

27. hetzelfde als hierboven maar op een andere manier: osboxes@osboxes:~$ mysql -uwww_user -phogent2022 www_db <<< "select * from todo_list;"
28. osboxes@osboxes:/var/www/html$ sudo nano todo.php, script 2, vergeet ww niet te veranderen!
29. testen: osboxes@osboxes:/var/www/html$ php todo.php
30. surf naar: http://localhost/todo.php
31. osboxes@osboxes:/var/www/html$ , zitten volgende mappen in: <br>index.html,  info.php,  todo.php
32. website buiten vm tonen, settings > network > advanced > port forwarding 
33. invullen: Web, TCP, 127.0.0.1, 8080, 10.0.2.15, 80
34. Nu op het fysiek systeem surfen naar: 127.0.0.1:8080
35. osboxes@osboxes:/var/www/html$ sudo ss -tlnp