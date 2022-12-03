## step-1

### Задача
 - [x] Докеризировать приложение
 - [ ] Описать логику сервиса
 - [ ] Описать сущность **Order**
 - [ ] Создать логику запроса сущности **Order**

### Выполнено
Приложение доступно в контейнере. Dockerfile в папке docker:
```bash
$tree docker/
docker/
└── Dockerfile

0 directories, 1 file
```

Пример команды запуска:
```bash
$docker run -d --name pfb -p 8080:8080 daskain/proxy-for-backend:0.1.0
6c279d18d191281ed38f03256b4645bfce4c47227026cc619ae62ebd6d8aed9a
$docker ps -a
CONTAINER ID   IMAGE                             COMMAND               CREATED          STATUS          PORTS                    NAMES
6c279d18d191   daskain/proxy-for-backend:0.1.0   "java -jar pfb.jar"   27 seconds ago   Up 26 seconds   0.0.0.0:8080->8080/tcp   pfb
```

В текущей сборке доступен actuator