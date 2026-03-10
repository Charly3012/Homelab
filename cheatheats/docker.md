# 🐳 Guía de Docker y Docker Compose

Docker es el motor que corre las aplicaciones, y Docker Compose es el manual de instrucciones para lanzarlas de forma organizada.

---

## 📝 1. El Archivo: `compose.yaml`

Históricamente se usaba `docker-compose.yml`, pero el estándar moderno y recomendado es simplemente **`compose.yaml`**. 



### 💡 Reglas de Oro de YAML (El formato):
* **Identación con Espacios:** YAML no entiende de pestañas. Nunca uses la tecla **TAB**, usa siempre **2 espacios** para cada nivel.
* **Espacios Obligatorios:** Siempre debe haber un espacio después de los dos puntos (`clave: valor`) y después de los guiones (`- valor`).
* **Listas:** Se indican con un guion `-`. Se usan para puertos, volúmenes y redes.
* **Comentarios:** Usa `#` para escribir notas que el sistema ignorará.

---

## 🚀 2. Comandos de Docker Compose

> **Importante:** Estos comandos deben ejecutarse **dentro de la carpeta** donde está tu archivo `compose.yaml`.

| Comando | Acción |
| :--- | :--- |
| `docker compose up -d` | **Encender:** Lee el archivo, descarga imágenes y levanta todo en segundo plano (`-d`). |
| `docker compose down` | **Apagar:** Detiene y elimina los contenedores (pero no tus datos). |
| `docker compose ps` | **Estado:** Muestra qué servicios están corriendo y cuáles fallaron. |
| `docker compose logs -f` | **Caja Negra:** Muestra los logs (mensajes de error/estado) en tiempo real. |
| `docker compose restart` | **Reiniciar:** Útil para aplicar cambios rápidos sin apagar todo. |
| `docker compose pull` | **Actualizar:** Baja la versión más reciente de las imágenes. |

---

## 📦 3. Gestión de Docker (Comandos Core)

A veces necesitas controlar contenedores individuales o limpiar el sistema:

| Comando | Acción |
| :--- | :--- |
| `docker ps` | Lista todos los contenedores activos en el servidor. |
| `docker images` | Muestra todas las imágenes descargadas que ocupan espacio. |
| `docker exec -it <nombre> bash` | **Entrar:** Abre una terminal dentro del contenedor (modo hacker). |
| `docker system prune -f` | **Limpieza:** Borra contenedores parados e imágenes huérfanas. |
| `docker stop <nombre>` | Detiene un contenedor específico sin borrarlo. |



---

## 🏗️ 4. Anatomía de un `compose.yaml`

Copia este ejemplo como plantilla base para tus servicios:

```yaml
services:              # 1. El inicio de todo
  mi-web:              # 2. Nombre del servicio (el que quieras)
    image: nginx:latest # 3. La app que bajaremos de Docker Hub
    container_name: web-servidor
    ports:
      - "8080:80"      # 4. "Puerto_Laptop:Puerto_Contenedor"
    volumes:
      - ./sitio:/usr/share/nginx/html # 5. Carpeta compartida (Persistencia)
    restart: unless-stopped           # 6. Se levanta solo si la VM se reinicia