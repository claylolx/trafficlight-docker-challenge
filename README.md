# Proyecto Traffic Light + Proxy inverso + Balanceador de carga 🚦

Este proyecto simula un sistema de tráfico utilizando Docker Compose, compuesto por:
- Tres microservicios de colores (Red, Yellow, Green).
- Un proxy inverso Nginx para enrutar las aplicaciones por diferentes puertos.
- Un balanceador de carga que distribuye las peticiones entre los microservicios.

---

## Requisitos

- Docker
- Docker Compose (incluido en Docker Desktop)

---

## Cómo ejecutar el proyecto

### 1. Proxy Inverso

1. Abre la terminal y navega a la carpeta del proxy inverso:

```bash
cd proxy-inverso
```

2. Levanta los contenedores:

```bash
docker-compose up -d
```

3. Accede a las aplicaciones desde el navegador:

```
http://localhost:3000    # App Red
http://localhost:4000    # App Amarillo
http://localhost:5000    # App Verde
```

4. Para parar los contenedores:

```bash
docker-compose down
```

---

### 2. Balanceador de carga

1. Abre la terminal y navega a la carpeta del balanceador:

```bash
cd balanceador-de-carga
```

2. Levanta los contenedores:

```bash
docker-compose up -d
```

3. Accede a la aplicación desde el navegador:

```
http://localhost
```

4. Para parar los contenedores:

```bash
docker-compose down
```

---

## Notas finales

- No es necesario instalar nada manualmente.
- Docker Compose se encarga de construir todas las imágenes automáticamente desde los Dockerfile.
- Todas las aplicaciones están contenidas en contenedores y se comunican mediante una red interna de Docker.
- Si deseas limpiar completamente los recursos después de probar, puedes usar:

```bash
docker-compose down --rmi all
```

Esto eliminará también las imágenes locales construidas.

---
