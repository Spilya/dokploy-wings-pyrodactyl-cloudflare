Если использовать проксирование в cloudflare то не будет работать sftp, ну точнее будет только по прямому IP.
То есть спрятать айпишник sftp через cloudflare не выйдет!

1. Устанавливаем Pyrodactyl из темплейтов dokploy;
2. Открываем домен на 80 порт, запись проксируется;
3. Создаём композ, из файла wings-docker-compose.yml;
4. Заменить Host(`node2.yiffiy.pet`) на адрес ноды;
4. Заменить XXXXXX на что то случайное;
5. Настраиваем ноду из панели Pyrodactyl:
- Communicate Over SSL - Use SSL Connection;
- Behind Proxy - Behind Proxy;
- Daemon Port = 443.
6. На моменте когда копируем конфиг поправляем remote: 'http://pyro.yiffiy.pet' на https;

Таким образом мы прячем IP ноды за cloudflare и дружим её с dokploy.