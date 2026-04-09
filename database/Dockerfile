FROM postgres:17.2-alpine

# -e permet d'éviter de mettre en dur ici 

ENV POSTGRES_DB=db \
   POSTGRES_USER=usr \
   POSTGRES_PASSWORD=pwd

# dans mon docker je dois créer ce fichier --> /docker-entrypoint-initdb.d
# Il faut trouver la commande dans dockerfile qui lui dit d'aller chercher dans ce fichier pour exécuter mes deux fichiers sql

COPY create-schema.sql /docker-entrypoint-initdb.d/01-create-schema.sql
COPY insert-data.sql /docker-entrypoint-initdb.d/02-insert-data.sql
