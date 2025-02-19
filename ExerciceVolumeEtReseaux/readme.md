# Etape 1: Créer un réseau pour l'application

```bash
docker network create blog-network
```

# Etape 2: Créer un volume pour la base de données

```bash
docker volume create blog-db
```

# Etape 3: Lancer MySQL avec le volume et le réseau
```bash
docker run -d --name db --network=blog-network -v blog-db:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=wordpress mysql:8
```

# Etape 4: Lancer WordPress avec le réseau et le volume
```bash
docker run -d --name wordpress --network=blog-network -p 8080:80 -e WORDPRESS_DB_HOST=db -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=root wordpress
```

# Etape 5: Ouvrir votre navigateur et accéder à http://localhost:8080