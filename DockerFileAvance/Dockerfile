# Utilisation de l'image officielle de Nginx
FROM nginx:latest
FROM mysql:8-alpine
# Définition d'une varaible d'environnement
ENV APP_NAME="Mon premier serveur Web Docker"

# Créer un dossier et copier les fichiers HTML dedans
RUN mkdir -p /usr/share/nginx/html
COPY index.html /usr/share/nginx/html

# Exposer le port 80
EXPOSE 80

# Commande à exécuter au démarrage du conteneur
CMD ["nginx", "-g", "daemon off;"]

# docker build -t nginx-html .

# docker run -d -p 8080:80 nginx-html
