# Práctica 6: Servidor web Nginx con Docker

Servidor web Nginx corriendo de forma local con Docker Compose. La página que se muestra está en la carpeta `src` y se monta dentro del contenedor usando un volumen.

## Estructura del proyecto

```
practica6-nginx-docker/
├── src/
│   └── index.html
├── docker-compose.yml
└── README.md
```

## Requisitos

- Docker Desktop instalado y en ejecución

## Cómo ejecutarlo

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/Arisleidy-03/practica6-nginx-docker.git
   cd practica6-nginx-docker
   ```

2. Levantar el contenedor:

   ```bash
   docker compose up -d
   ```

3. Abrir en el navegador:

   ```
   http://localhost:8080
   ```

4. Para detener el contenedor:

   ```bash
   docker compose down
   ```

## Configuración

En el archivo `docker-compose.yml` se usa la imagen oficial de Nginx. El puerto 80 del contenedor se mapea al puerto 8080 de la PC, y la carpeta `src` se monta en `/usr/share/nginx/html`, que es donde Nginx busca los archivos que va a mostrar. Así, cualquier cambio en `index.html` se ve con solo recargar la página.

## Autora

Arisleidy Melo - 2025-1044
