¡Perfecto! A continuación, te presento una **secuencia didáctica completa** para un **curso de Django con Python** dirigido a estudiantes de nivel **principiante** (escolaridad: preparatoria), con una duración total de **15 horas**, distribuidas en tres momentos: **apertura, desarrollo y cierre**.

La secuencia incluye:
- Actividades **demostrativas** (guiadas por el docente)
- Actividades **autónomas** (realizadas por el estudiante)
- Glosario de términos
- Referencias y bibliografía
- Proyecto final con modelo `Producto` de 6 campos, incluyendo imagen

---

# 📘 **Secuencia Didáctica: Desarrollo Web con Django y Python**

**Tema:** Creación de aplicaciones web profesionales con Django  
**Duración:** 15 horas  
**Nivel:** Principiante  
**Público objetivo:** Estudiantes de preparatoria o principiantes en programación  
**Tecnologías:** Python, Django, HTML, CSS, JavaScript, Bootstrap, SQLite  
**Sistema operativo:** Windows  
**Software:** VS Code, Python, SQLite Viewer

---

## 🕒 **Distribución de Tiempo**

| Momento | Duración | Actividades clave |
|--------|----------|-------------------|
| **Apertura** | 4 horas | Introducción, instalación, primeros pasos |
| **Desarrollo** | 7 horas | Construcción del CRUD, modelos, vistas, plantillas |
| **Cierre** | 4 horas | Proyecto final, presentación, evaluación |

---

## 🧭 **Objetivo General**

Que el estudiante desarrolle una aplicación web funcional con Django, utilizando buenas prácticas de desarrollo, integrando modelos, vistas, plantillas y base de datos, para gestionar productos con imágenes, demostrando comprensión del framework y habilidades autónomas de programación.

---

## 🎯 **Objetivos Específicos**

- Instalar y configurar el entorno de desarrollo con Python y Django.
- Comprender la arquitectura MVC de Django.
- Crear modelos, vistas y URLs para gestionar datos.
- Implementar operaciones CRUD sin forms.py ni base.html.
- Utilizar Bootstrap para mejorar la interfaz.
- Gestionar imágenes en modelos con `ImageField`.
- Desarrollar un proyecto final funcional y atractivo.

---

# 🌅 **MOMENTO 1: APERTURA (4 horas)**

### 🎯 Objetivo:
Introducir a los estudiantes al desarrollo web con Django, configurar el entorno y crear el primer proyecto.

---

### ✅ Actividades Demostrativas (Docente)

| Tiempo | Actividad |
|-------|---------|
| 30 min | **Presentación del curso**: ¿Qué es Django? ¿Para qué sirve? Ejemplos reales (Instagram, Pinterest). |
| 30 min | **Instalación paso a paso**: Python, VS Code, extensiones, entorno virtual. |
| 1 h | **Crear proyecto `backend_empleado`**: `django-admin startproject`, estructura de carpetas, ejecutar servidor. |
| 30 min | **Panel de administración**: Crear superusuario, acceso, navegación. |

---

### ✅ Actividades Autónomas (Estudiante)

| Tiempo | Actividad |
|-------|---------|
| 1 h 30 min | **Replicar todo el proceso** en su máquina:  
- Crear carpeta `Curso_Django`  
- Instalar entorno virtual  
- Crear proyecto  
- Ejecutar servidor  
- Acceder al admin  
> ✅ Entregable: Captura de pantalla del servidor funcionando y del panel de admin. |

---

# 🔨 **MOMENTO 2: DESARROLLO (7 horas)**

### 🎯 Objetivo:
Construir una aplicación CRUD completa para gestionar empleados, comprendiendo modelos, vistas, URLs y plantillas.

---

### ✅ Actividades Demostrativas (Docente)

| Tiempo | Actividad |
|-------|---------|
| 1 h | **Crear app `app_empleado`**: Explicar apps en Django, registro en `settings.py`. |
| 1 h | **Modelos y migraciones**: Crear modelo `Empleado`, `makemigrations`, `migrate`, revisar SQLite. |
| 1 h | **Vistas con `render`**: Crear `listar_empleados`, usar contexto, plantillas. |
| 1 h | **CRUD básico**: Explicar `crear`, `editar`, `borrar` con `request.POST`. |
| 30 min | **Uso de Bootstrap**: Agregar estilos, botones, tablas atractivas. |

---

### ✅ Actividades Autónomas (Estudiante)

| Tiempo | Actividad |
|-------|---------|
| 2 h 30 min | **Construir el CRUD completo** de empleados:  
- Crear modelo  
- Registrar en admin  
- Hacer migraciones  
- Crear vistas y URLs  
- Diseñar plantillas HTML con Bootstrap  
> ✅ Entregable: Aplicación funcionando con todas las operaciones CRUD. |

---

# 🌅 **MOMENTO 3: CIERRE (4 horas)**

### 🎯 Objetivo:
Aplicar todo lo aprendido en un proyecto final: un sistema de gestión de **productos** con imagen.

---

### ✅ Actividad Demostrativa (Docente)

| Tiempo | Actividad |
|-------|---------|
| 1 h | **Presentar proyecto final**: Sistema de productos.  
Mostrar modelo con imagen, formulario de carga, vista de lista con fotos.  
Explicar `Pillow` para manejo de imágenes. |

---

### ✅ Actividad Autónoma (Estudiante)

| Tiempo | Actividad |
|-------|---------|
| 3 h | **Desarrollar proyecto final**:  
> ✅ Entregable: Proyecto funcional con:  
- Modelo `Producto` (6 campos, incluyendo imagen)  
- CRUD completo  
- Interfaz con Bootstrap  
- Imágenes visibles en listado  

> 📂 Carpeta entregable: `proyecto_productos` (dentro de `Curso_Django`)

---

## 📂 **Proyecto Final: Sistema de Gestión de Productos**

### 🧱 Modelo: `Producto` (app: `app_productos`)

Crea una nueva app:

```bash
python manage.py startapp app_productos
```

Agrega a `INSTALLED_APPS` en `settings.py`.

---

### 📄 `app_productos/models.py`

```python
from django.db import models

class Producto(models.Model):
    nombre = models.CharField(max_length=100, verbose_name="Nombre")
    descripcion = models.TextField(verbose_name="Descripción", blank=True)
    precio = models.DecimalField(max_digits=10, decimal_places=2, verbose_name="Precio")
    stock = models.PositiveIntegerField(verbose_name="Stock")
    fecha_creacion = models.DateTimeField(auto_now_add=True, verbose_name="Fecha de Creación")
    imagen = models.ImageField(upload_to='productos/', verbose_name="Foto", blank=True, null=True)

    def __str__(self):
        return self.nombre

    class Meta:
        verbose_name = "Producto"
        verbose_name_plural = "Productos"
        ordering = ['-fecha_creacion']
```

> ⚠️ **Requisito**: Instalar `Pillow` para manejar imágenes:

```bash
pip install Pillow
```

Y después:

```bash
python manage.py makemigrations
python manage.py migrate
```

---

### 🖼️ Configurar imágenes en `settings.py`

Agrega al final del archivo:

```python
# Configuración de archivos estáticos y medios
import os

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```

---

### 🔗 Configurar URLs generales en `backend_empleado/urls.py`

```python
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('app_productos.urls')),
]

# Sirve archivos de medios en desarrollo
if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

### 🖼️ En plantillas, muestra la imagen así:

```html
<img src="{{ producto.imagen.url }}" alt="{{ producto.nombre }}" width="100" class="img-thumbnail">
```

> Asegúrate de que la carpeta `media/productos/` se crea automáticamente al subir imágenes.

---

## 📚 **Glosario de Términos**

| Término | Definición |
|--------|-----------|
| **Django** | Framework web de Python para desarrollar aplicaciones rápidamente. |
| **CRUD** | Create, Read, Update, Delete: operaciones básicas sobre datos. |
| **Modelo** | Representación de una tabla en la base de datos. |
| **Vista** | Función que procesa una solicitud y devuelve una respuesta. |
| **URLs** | Rutas que conectan direcciones web con vistas. |
| **Template** | Archivo HTML con lógica dinámica (Django Template Language). |
| **ORM** | Object-Relational Mapping: permite interactuar con la BD sin SQL. |
| **Entorno virtual** | Espacio aislado para instalar paquetes sin afectar al sistema. |
| **Migración** | Proceso para actualizar la base de datos según los modelos. |
| **Bootstrap** | Framework CSS para diseño web responsive y atractivo. |
| **ImageField** | Campo de modelo que almacena archivos de imagen. |
| **MEDIA_ROOT** | Carpeta donde se guardan los archivos subidos por el usuario. |

---

## 🔗 **Referencias y Recursos**

1. **Documentación Oficial de Django**  
   [https://docs.djangoproject.com](https://docs.djangoproject.com)

2. **Bootstrap 5**  
   [https://getbootstrap.com](https://getbootstrap.com)

3. **VS Code + Python**  
   [https://code.visualstudio.com/docs/python/python-tutorial](https://code.visualstudio.com/docs/python/python-tutorial)

4. **SQLite Viewer en VS Code**  
   Buscar extensión: "SQLite Viewer"

5. **Pillow (PIL)**  
   [https://pillow.readthedocs.io](https://pillow.readthedocs.io)

---

## 📚 **Bibliografía Recomendada**

- Django for Beginners (William S. Vincent) – Ideal para principiantes.
- Python Crash Course (Eric Matthes) – Base sólida de Python.
- Automate the Boring Stuff with Python (Al Sweigart) – Enfoque práctico.
- Documentación oficial de Django (en inglés, pero muy completa).

---

## 🏁 **Evaluación Final**

| Criterio | Puntaje |
|--------|--------|
| Instalación y entorno | 10 pts |
| Proyecto CRUD de empleados | 30 pts |
| Proyecto final de productos (modelo, CRUD, imágenes) | 40 pts |
| Interfaz atractiva (Bootstrap) | 10 pts |
| Entrega completa y ordenada | 10 pts |
| **Total** | **100 pts** |

---

## 🎉 **Conclusión**

Esta secuencia permite al estudiante **aprender haciendo**, desde cero, con actividades progresivas que van de lo simple a lo complejo. Al final, tendrá un **portafolio con dos proyectos funcionales**, listos para mostrar a futuros empleadores o continuar aprendiendo.

---

¿Quieres que te genere un **archivo ZIP estructurado** con todo el proyecto final listo para descargar?  
Puedo ayudarte a empaquetarlo con carpetas, archivos y un `README.md`.
