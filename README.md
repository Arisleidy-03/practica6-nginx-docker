# Práctica 6: Servidor web Nginx con Docker Compose

En esta práctica se levanta un servidor web Nginx de forma local usando Docker Compose. La página web se encuentra en la carpeta `src` y se conecta al contenedor mediante un volumen, de modo que Nginx la sirve directamente desde la PC.

## Objetivo

Crear y ejecutar un contenedor de Nginx con Docker Compose que muestre una página `index.html` con el mensaje "Hola Mundo".

## Tecnologías utilizadas

| Herramienta | Uso |
|---|---|
| Docker Desktop | Ejecutar los contenedores |
| Docker Compose | Definir y levantar el servicio |
| Nginx | Servidor web |
| HTML y CSS | Página de inicio |
| Git y GitHub | Control de versiones |

## Estructura del proyecto

```
practica6-nginx-docker/
├── src/
│   └── index.html        # Página que muestra Nginx
├── docker-compose.yml    # Configuración del servicio
└── README.md
```

## Desarrollo de la práctica

### 1. Directorio `src` con el archivo `index.html`

Se creó la carpeta `src` y dentro el archivo `index.html`, que muestra el mensaje "Hola Mundo".

### 2. Archivo `docker-compose.yml`

```yaml
services:
  web:
    image: nginx:latest
    container_name: nginx-practica6
    ports:
      - "8080:80"
    volumes:
      - ./src:/usr/share/nginx/html
    restart: unless-stopped
```

- `image`: usa la imagen oficial de Nginx.
- `ports`: conecta el puerto 8080 de la PC con el puerto 80 del contenedor.
- `volumes`: monta la carpeta `src` en `/usr/share/nginx/html`, que es la carpeta donde Nginx busca los archivos que va a mostrar.
- `restart`: reinicia el contenedor automáticamente si se detiene por un error.

### 3. Ejecución del contenedor

```bash
docker compose up -d
```

Para comprobar que el contenedor está corriendo:

```bash
docker ps
```

Luego se abre en el navegador la dirección:

```
http://localhost:8080
```

### 4. Repositorio en GitHub

El proyecto se subió a este repositorio público para su entrega.

## Cómo ejecutarlo

1. Tener Docker Desktop instalado y abierto.
2. Clonar el repositorio:

   ```bash
   git clone https://github.com/Arisleidy-03/practica6-nginx-docker.git
   cd practica6-nginx-docker
   ```

3. Levantar el contenedor:

   ```bash
   docker compose up -d
   ```

4. Abrir `http://localhost:8080` en el navegador.

## Comandos útiles

| Comando | Descripción |
|---|---|
| `docker compose up -d` | Levanta el contenedor en segundo plano |
| `docker ps` | Muestra los contenedores en ejecución |
| `docker compose logs` | Muestra los registros de Nginx |
| `docker compose down` | Detiene y elimina el contenedor |

## Autora

Arisleidy Melo - 2025-1044
