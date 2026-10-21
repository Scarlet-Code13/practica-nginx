# Servidor Web Nginx con Docker Compose

## Descripción

Esta práctica consiste en crear y ejecutar un servidor web Nginx de forma local utilizando Docker Compose. La página web muestra un mensaje de bienvenida y se sirve desde un contenedor Docker.

## Objetivos

- Crear una página web sencilla utilizando HTML.
- Configurar un servidor web Nginx con Docker Compose.
- Compartir el directorio de la página web con el contenedor mediante un volumen.
- Ejecutar y comprobar el funcionamiento del servidor.
- Subir el proyecto a un repositorio público de GitHub.

## Estructura del proyecto

```text
practica-nginx/
├── src/
│   └── index.html
├── docker-compose.yml
└── README.md
```

## Tecnologías utilizadas

- HTML
- Nginx
- Docker
- Docker Compose
- Git y GitHub

## Configuración de Docker Compose

El archivo `docker-compose.yml` utiliza la imagen `nginx:alpine` para ejecutar el servidor web.

El volumen está configurado de la siguiente manera:

```yaml
volumes:
  - ./src:/usr/share/nginx/html:ro
```

Esta configuración permite que Nginx sirva los archivos ubicados en el directorio `src` de la computadora. El parámetro `:ro` indica que el volumen se monta en modo de solo lectura.

El puerto 8080 de la computadora está conectado al puerto 80 del contenedor.

## Cómo ejecutar el proyecto

1. Abrir una terminal en el directorio del proyecto.
2. Ejecutar el siguiente comando para iniciar el contenedor:

   ```bash
   docker compose up -d
   ```

3. Verificar el estado del contenedor:

   ```bash
   docker compose ps
   ```

4. Abrir el navegador y acceder a:

   http://localhost:8080

## Resultado

Al acceder a la dirección local, se muestra el siguiente mensaje:

**Hola mundo**

Mi servidor Nginx funciona con Docker Compose.

## Detener el servidor

Para detener y eliminar el contenedor creado por Docker Compose, ejecutar:

```bash
docker compose down
```

## Repositorio

[practica-nginx en GitHub](https://github.com/Scarlet-Code13/practica-nginx)

## Conclusión

Con esta práctica se logró crear y ejecutar un servidor web Nginx mediante Docker Compose, utilizando un volumen para servir una página HTML local y publicando los archivos del proyecto en un repositorio público de GitHub.
