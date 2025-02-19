1. Créer un volume:
```bash
docker volume create site-web
```

2. Créer un container:
```bash
echo "<h1>Bonjour depuis un volume Docker !</h1>" > index.html
```

3. Lancer un conteneur en partageant ce fichier :
```bash
docker run -d -p 8080:80 -v $(pwd)/index.html:/usr/share/nginx/html/index.html nginx
```
4. Ouvrir dans le navigateur :
Ouvrir http://localhost:8080

Tu devrais voir le message "Bonjour depuis un volume Docker !"
