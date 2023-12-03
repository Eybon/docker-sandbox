# docker-sandbox
Projet sandbox pour tests sur des images dockers


## 1️⃣ Image `basic-http-hello-world`

Une simple image docker qui renvoit une réponse `http` lors d'un appel sur le port `8080`.

L'image est dispo sur plusieurs plateformes :
- `linux/amd64` --> pour utilisation wsl2 par exemple
- `linux/arm/v7` --> pour utilisation sur une raspberry par exemple

**Commande docker** :
```shell
# Build des images docker en local
docker build --platform linux/amd64 --tag=basic-http-hello-world:amd64 basic-http-hello-world
docker build --platform linux/arm/v7 --tag=basic-http-hello-world:armv7 basic-http-hello-world


# Run image local
docker run -p 8080:8080 -d basic-http-hello-world:amd64

# Run image github
docker run -p 8080:8080 -d ghcr.io/eybon/basic-http-hello-world:amd64

# Use
curl localhost:8080
curl -I localhost:8080
```
