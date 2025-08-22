¡Perfecto! A continuación, te presento una **plantilla lista para usar en Google Classroom**, diseñada especialmente para el **curso de Django con Python** que hemos desarrollado. Esta plantilla está organizada por **semanas o módulos**, incluye **títulos atractivos**, **descripciones claras**, **actividades**, **recursos**, **fechas sugeridas** y **formatos de entrega**, ideal para docentes que imparten clases a estudiantes de nivel **principiante** (preparatoria).

---

# 🎓 **Plantilla para Google Classroom: Curso de Django con Python**

> **Nombre del curso:** Desarrollo Web con Django y Python  
> **Nivel:** Principiante  
> **Duración:** 4 semanas (15 horas aproximadas)  
> **Plataforma:** Google Classroom  
> **Dirigido a:** Estudiantes de preparatoria  
> **Sistema operativo:** Windows

---

## 🖥️ **Cómo usar esta plantilla**

1. Crea un nuevo curso en [Google Classroom](https://classroom.google.com)
2. Copia cada sección como una **"Publicación"** (Anuncio, Trabajo o Pregunta)
3. Ajusta las fechas según tu calendario escolar
4. Sube los recursos (PDF, enlaces, videos, etc.)

---

### 📅 **Semana 1: Preparación del Entorno y Primeros Pasos con Django**

#### 📢 **Anuncio: Bienvenidos al curso de Django 🚀**
> ¡Hola! Bienvenidos a **Desarrollo Web con Django y Python**. En este curso aprenderás a crear aplicaciones web profesionales desde cero. No necesitas experiencia previa.  
>  
> 📅 Inicio: Lunes  
> 💻 Requisitos: Computadora con Windows, internet, Python y VS Code instalados.

---

#### 🧩 **Trabajo: Instalación y configuración del entorno**
- **Instrucciones:**
  1. Sigue el Módulo 1 del curso.
  2. Crea la carpeta `Curso_Django\practica_1`.
  3. Instala Python, VS Code y extensiones.
  4. Verifica `python --version` y `pip --version`.
- **Entrega:** Captura de pantalla de la terminal mostrando las versiones.
- **Formato:** Imagen (PNG o JPG)
- **Fecha de entrega:** Viernes

📎 **Recursos adjuntos:**
- [Guía de instalación de Python](https://www.python.org/downloads/)
- [Descargar VS Code](https://code.visualstudio.com/)

---

#### 🧪 **Actividad: Crear el entorno virtual y proyecto Django**
- **Instrucciones:**
  1. Crea el entorno virtual `.venv`.
  2. Actívalo y selecciona el intérprete en VS Code.
  3. Instala Django y crea el proyecto `backend_empleado`.
  4. Ejecuta el servidor y toma una captura de la página de bienvenida.
- **Entrega:** Captura de pantalla del navegador mostrando "The install worked successfully!".
- **Fecha de entrega:** Sábado

---

### 📅 **Semana 2: Modelos, Base de Datos y Panel de Administración**

#### 📢 **Anuncio: Aprendiendo a gestionar datos con Django 🗄️**
> Esta semana aprenderás a crear modelos, usar la base de datos SQLite y acceder al panel de administración. ¡Tendrás tu primer sistema de gestión listo!

---

#### 🧩 **Trabajo: Crear la app `app_empleado` y el modelo `Empleado`**
- **Instrucciones:**
  1. Crea la app `app_empleado`.
  2. Define el modelo con `nombre` y `edad`.
  3. Regístralo en el admin.
  4. Haz migraciones y aplica `migrate`.
- **Entrega:** Captura de pantalla del visor de SQLite mostrando la tabla `app_empleado_empleado`.
- **Fecha de entrega:** Miércoles

📎 **Recursos adjuntos:**
- PDF: Módulo 5 del curso
- Video: "Cómo usar SQLite Viewer en VS Code" (enlace a YouTube o grabación propia)

---

#### 🧪 **Actividad: Agregar empleados desde el panel de admin**
- **Instrucciones:**
  1. Crea un superusuario.
  2. Accede a `/admin` y agrega 3 empleados.
  3. Toma una captura del listado en el panel.
- **Entrega:** Imagen del panel de administración con los empleados.
- **Fecha de entrega:** Viernes

---

### 📅 **Semana 3: Vistas, URLs y CRUD sin Forms.py**

#### 📢 **Anuncio: ¡Manos a la obra con el CRUD! ✏️**
> Esta semana construiremos todas las operaciones: Crear, Leer, Actualizar y Eliminar. Todo sin usar `forms.py` ni `base.html`, ideal para principiantes.

---

#### 🧩 **Trabajo: Crear vistas y URLs para el CRUD**
- **Instrucciones:**
  1. Crea las vistas: `crear_empleado`, `actualizar_empleado`, `borrar_empleado`.
  2. Configura las URLs en `app_empleado/urls.py`.
  3. Crea las plantillas en la carpeta `templates`.
- **Entrega:** Código de `views.py` y `urls.py` (como archivo `.txt` o captura).
- **Fecha de entrega:** Martes

---

#### 🧪 **Actividad: Sistema CRUD funcionando**
- **Instrucciones:**
  1. Prueba todas las funciones: crear, editar, borrar.
  2. Graba un **video corto (1-2 min)** mostrando el sistema en acción.
- **Entrega:** Video (MP4) subido a Google Drive o YouTube (privado).
- **Fecha de entrega:** Jueves

---

### 📅 **Semana 4: Proyecto Final – Sistema de Productos con Imágenes**

#### 📢 **Anuncio: Proyecto Final 🏁**
> ¡Es hora de demostrar todo lo aprendido! Crea una nueva app para gestionar productos con fotos. Este será tu proyecto estrella.

---

#### 🏆 **Proyecto Final: Sistema de Gestión de Productos**
- **Instrucciones:**
  1. Crea una nueva app: `app_productos`.
  2. Modelo `Producto` con 6 campos, incluyendo `imagen`.
  3. Usa `Pillow` para subir fotos.
  4. Interfaz con Bootstrap.
  5. CRUD completo.
- **Entrega:** 
  - Carpeta comprimida en ZIP con todo el proyecto.
  - Documento PDF con capturas del sistema funcionando.
- **Fecha de entrega:** Sábado

📎 **Recursos adjuntos:**
- Plantilla del modelo `Producto` (código)
- Guía: "Cómo manejar imágenes en Django"
- Rúbrica de evaluación (PDF)

---

## 📎 **Recursos del Curso (Sección Fija en "Material del curso")**

### 📚 Archivos y enlaces
1. 📄 [Guía completa del curso en PDF](#) *(sube el archivo)*
2. 📂 [Estructura de carpetas ejemplo](#) *(sube un ZIP con carpetas vacías)*
3. 🔗 [Documentación oficial de Django](https://docs.djangoproject.com)
4. 🔗 [Bootstrap 5](https://getbootstrap.com)
5. 📹 [Playlist: Django para principiantes (YouTube)](#) *(opcional)*

---

## 📝 **Criterios de Evaluación (Rúbrica en PDF)**
- Lista de cotejo
- Rúbrica detallada (0-10)
- Autoevaluación para estudiantes

> ⬇️ Sube este PDF como recurso fijo.

---

## ✅ **Consejos para el docente**

- Usa la función **"Reciclador"** para reutilizar publicaciones en futuros ciclos.
- Activa **"Hasta"** en cada trabajo para permitir reentregas.
- Usa **"Calificaciones"** para registrar avances.
- Comparte **retroalimentación escrita** en cada entrega.
- Crea un **foro de dudas** con una publicación tipo "Pregunta":

> ❓ **¿Tienes dudas? Déjalas aquí y te responderé pronto.**

---

## 📥 ¿Quieres el archivo listo para importar?

Puedo ayudarte a:

1. 📥 **Generar un archivo `.zip`** con:
   - Todo el curso en PDF
   - Plantillas HTML
   - Rúbricas
   - Estructura de carpetas

2. 📤 **Crear un enlace de Google Classroom listo para unirte** (si me das acceso temporal).

3. 📧 **Enviar un archivo `.json` o CSV** para importar estudiantes.

---

👉 **Solo dime**:  
¿Quieres que te genere un **archivo ZIP con todo el curso listo para subir a Google Classroom**?  
Te lo preparo en minutos con carpetas, PDFs, rúbricas y todo organizado.
