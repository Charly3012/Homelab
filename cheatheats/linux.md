# 🐧 Guía de Supervivencia: La Terminal Linux

Esta es tu referencia rápida para moverte por el servidor sin miedo. Recuerda: en Linux, **las mayúsculas y minúsculas importan** (no es lo mismo `Documentos` que `documentos`).

---

## 📂 1. Navegación (¿Dónde estoy?)

| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `pwd` | "Print Working Directory". Te dice la ruta de la carpeta donde estás. | `pwd` |
| `ls` | "List". Muestra los archivos y carpetas que hay aquí. | `ls` |
| `ls -la` | Muestra TODO (archivos ocultos y permisos detallados). | `ls -la` |
| `cd <nombre>` | "Change Directory". Entra a una carpeta. | `cd Containers` |
| `cd ..` | Sube un nivel (te saca de la carpeta actual a la anterior). | `cd ..` |
| `clear` | Limpia la pantalla para que no sea un caos de texto. | `clear` |

---

## 📄 2. Gestión de Archivos y Carpetas

| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `mkdir <nombre>` | Crea una carpeta nueva. | `mkdir mi-proyecto` |
| `touch <nombre>` | Crea un archivo vacío (ideal para archivos .yml o .txt). | `touch nota.txt` |
| `cp <orig> <dest>` | Copia un archivo. | `cp index.html index_bak.html` |
| `mv <orig> <dest>` | Mueve o **renombra** un archivo. | `mv viejo.txt nuevo.txt` |
| `rm <archivo>` | Borra un archivo (**¡No hay papelera, es definitivo!**). | `rm basura.txt` |
| `rm -rf <carpeta>` | Borra una carpeta y todo lo que tenga dentro. | `rm -rf vieja-config` |



---

## 🛠️ 3. Ver y Editar 

| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `cat <archivo>` | Escupe el contenido del archivo en la pantalla. | `cat .env` |
| `nano <archivo>` | Abre el editor de texto para modificar el archivo. | `nano docker-compose.yml` |

> **💡 Tips de Nano:**
> * Para **Guardar**: Presiona `Ctrl + O` y luego `Enter`.
> * Para **Salir**: Presiona `Ctrl + X`.

---

## 🔑 4. Superpoderes y Redes

| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `sudo <comando>` | Ejecuta algo como Administrador (pide contraseña). | `sudo apt update` |
| `ip a` | Te muestra tu dirección IP (la dirección de tu "edificio"). | `ip a` |
| `sudo chown -R 1000:1000 .` | **¡El Sana-Sana!** Arregla permisos de carpetas para Docker. | `sudo chown -R 1000:1000 .` |

---

## ⌨️ Atajos de Teclado (Para ir rápido)

* **TAB (Tabulador):** Escribe las primeras letras de una carpeta y presiona TAB. Linux completará el nombre por ti. **¡Úsalo siempre para evitar errores de dedo!**
* **Flechas Arriba/Abajo:** Navega por los comandos que ya escribiste antes.
* **Ctrl + C:** Detiene cualquier proceso que se haya quedado trabado o corriendo.
* **Ctrl + L:** Atajo rápido para limpiar la pantalla.
* **Click derecho (en terminal):** En la mayoría de las terminales, el click derecho sirve para **pegar** el texto que traigas del portapapeles.

---