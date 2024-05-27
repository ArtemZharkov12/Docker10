### 1. Tworzenie sieci mostkowej

```bash
docker network create --driver bridge lab10net 
```

### 2. Przygotowanie pliku HTML
Plik index.html został umieszczony w katalogu głównym i przygotowany do wyświetlenia informacji.

### 3. Konfiguracja katalogów dla logów
Utworzono katalogi web1, web2, web3 wewnątrz głównego katalogu logs dla logów nginx.

### 4. Uruchomienie kontenerów
Polecenia dla uruchomienia kontenerów:
```bash
docker run -d --name web1 --network lab10net -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/index.html:/usr/share/nginx/html/index.html:ro" -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/logs/web1:/var/log/nginx" -p 8081:80 nginx:latest
docker run -d --name web2 --network lab10net -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/index.html:/usr/share/nginx/html/index.html:ro" -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/logs/web2:/var/log/nginx" -p 8082:80 nginx:latest
docker run -d --name web3 --network lab10net -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/index.html:/usr/share/nginx/html/index.html:ro" -v "/c/Users/Artem Zharkov/Desktop/Docker/Docker10/logs/web3:/var/log/nginx" -p 8083:80 nginx:latest
```

### 5. Dostępność do stron HTML
Linki do stron każdego z serwerów :

http://localhost:8081

http://localhost:8082

http://localhost:8083
