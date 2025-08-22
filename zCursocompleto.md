¡Con mucho gusto! A continuación, te presento el **curso completo de Django con Python**, desarrollado **módulo por módulo**, con **explicaciones claras**, **código listo para usar**, **ejercicios prácticos** y diseñado especialmente para **estudiantes de nivel principiante** (escolaridad: preparatoria) en **Windows**.

Este curso sigue el índice que creamos, y cada módulo incluye:
- 🎯 Objetivo
- 📘 Explicación sencilla
- 💻 Código paso a paso
- 🧪 Ejercicio práctico
- ✅ Solución del ejercicio (opcional)

---

# 📘 **Curso Completo: Desarrollo Web Profesional con Django y Python**

> **Dirigido a principiantes – Windows – VS Code – Sin experiencia previa**

---

## 🧭 **Módulo 1: Preparación del Entorno de Desarrollo**

### 🎯 Objetivo
Configurar correctamente el entorno de desarrollo con Python, VS Code y las herramientas necesarias para comenzar con Django.

---

### 📘 Explicación
Antes de programar, necesitas tener las herramientas instaladas. En este módulo aprenderás a preparar tu computadora para desarrollar aplicaciones web con Django.

---

### 💻 Pasos a seguir

1. **Crea la carpeta principal**
   ```bash
   C:\Curso_Django\
   ```

2. **Dentro, crea la carpeta del proyecto**
   ```
   C:\Curso_Django\practica_1
   ```

3. **Abre VS Code**
   - Abre la carpeta `practica_1` en VS Code.

4. **Instala extensiones recomendadas**
   - Ve a la pestaña de extensiones (`Ctrl+Shift+X`) y busca:
     - `Python`
     - `Pylance`
     - `Django`
     - `HTML CSS Support`
     - `SQLite Viewer`
     - `Bracket Pair Colorizer`

5. **Abre la terminal en VS Code**
   - `Ctrl + Ñ`

6. **Verifica Python**
   ```bash
   python --version
   # Debe mostrar: Python 3.x.x
   ```

7. **Verifica pip**
   ```bash
   pip --version
   # Debe mostrar: pip 23.x o superior
   ```

---

### 🧪 Ejercicio 1
1. Crea la carpeta `Curso_Django` y dentro `practica_1`.
2. Abre VS Code y verifica que Python esté instalado.
3. Toma una captura de pantalla de la terminal mostrando `python --version`.

---

### ✅ Solución
- Asegúrate de que la versión de Python sea 3.8 o superior.
- Si no aparece, reinstala Python y marca "Add Python to PATH" durante la instalación.

---

## 🔌 **Módulo 2: Entorno Virtual y Configuración Inicial**

### 🎯 Objetivo
Crear un entorno virtual para aislar las dependencias del proyecto y evitar conflictos con otros proyectos.

---

### 📘 Explicación
Un **entorno virtual** es como una "caja aislada" donde instalas solo lo que necesitas para un proyecto. Así, no afectas a otros programas.

---

### 💻 Pasos a seguir

1. **Crea el entorno virtual**
   ```bash
   python -m venv .venv
   ```

2. **Actívalo**
   ```bash
   .venv\Scripts\activate
   ```
   > Verás: `(.venv) C:\...`

3. **Selecciona el intérprete en VS Code**
   - `Ctrl + Shift + P` → "Python: Select Interpreter"
   - Elige el que diga: `.venv`

4. **Instala Django**
   ```bash
   pip install django
   ```

5. **Verifica instalación**
   ```bash
   django-admin --version
   # Ejemplo: 4.2.7
   ```

6. **Guarda dependencias**
   ```bash
   pip freeze > requirements.txt
   ```

---

### 🧪 Ejercicio 2
1. Activa el entorno virtual.
2. Instala Django y verifica la versión.
3. Confirma que el archivo `requirements.txt` se haya creado.

---

### ✅ Solución
El archivo `requirements.txt` debe contener:
```
Django==4.2.7
sqlparse==0.4.4
asgiref==3.7.2
```

---

## 🏗️ **Módulo 3: Creación del Proyecto Django**

### 🎯 Objetivo
Crear el proyecto principal `backend_empleado` y ejecutar el servidor de desarrollo.

---

### 📘 Explicación
Un **proyecto Django** es la base de tu aplicación web. Contiene la configuración general, URLs principales y archivos de arranque.

---

### 💻 Pasos a seguir

1. **Crea el proyecto**
   ```bash
   django-admin startproject backend_empleado .
   ```

2. **Estructura del proyecto**
   ```
   practica_1/
   ├── backend_empleado/
   │   ├── __init__.py
   │   ├── settings.py
   │   ├── urls.py
   │   └── wsgi.py
   ├── manage.py
   └── .venv/
   ```

3. **Ejecuta el servidor**
   ```bash
   python manage.py runserver
   ```

4. **Abre el navegador**
   - Ve a: [http://127.0.0.1:8000](http://127.0.0.1:8000)
   - Debes ver: *"The install worked successfully!"*

5. **Detén el servidor**
   ```bash
   Ctrl + C
   ```

---

### 🧪 Ejercicio 3
1. Crea el proyecto `backend_empleado`.
2. Inicia el servidor y verifica que la página funcione.
3. Detén el servidor y vuelve a iniciarlo.

---

### ✅ Solución
Si todo funciona, puedes continuar. Si hay error, revisa que estés en el entorno virtual.

---

## 🗄️ **Módulo 4: Base de Datos y Panel de Administración**

### 🎯 Objetivo
Configurar la base de datos SQLite y acceder al panel de administración de Django.

---

### 📘 Explicación
Django usa **SQLite** por defecto (una base de datos ligera). Con las **migraciones**, creamos las tablas necesarias para el sistema.

---

### 💻 Pasos a seguir

1. **Realiza la migración inicial**
   ```bash
   python manage.py migrate
   ```
   > Crea `db.sqlite3`

2. **Crea un superusuario**
   ```bash
   python manage.py createsuperuser
   ```
   - Username: `admin`
   - Email: (opcional)
   - Password: `12345678` (mínimo 8 caracteres)

3. **Inicia el servidor**
   ```bash
   python manage.py runserver
   ```

4. **Accede al admin**
   - Ve a: [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)
   - Inicia sesión con `admin` y tu contraseña.

5. **Usa un visor de SQLite**
   - Abre `db.sqlite3` en VS Code.
   - Haz clic derecho → "Open with SQLite Viewer".

---

### 🧪 Ejercicio 4
1. Crea el superusuario.
2. Accede al panel de admin.
3. Usa el visor para ver las tablas creadas.

---

### ✅ Solución
Debes ver tablas como `auth_user`, `django_admin_log`, etc.

---

## 🧱 **Módulo 5: Creación de la Aplicación y Modelos**

### 🎯 Objetivo
Crear una app para gestionar empleados y definir el modelo `Empleado`.

---

### 💻 Pasos a seguir

1. **Crea la app**
   ```bash
   python manage.py startapp app_empleado
   ```

2. **Registra la app en `settings.py`**
   ```python
   # backend_empleado/settings.py
   INSTALLED_APPS = [
       'django.contrib.admin',
       'django.contrib.auth',
       # ... otros
       'app_empleado',  # ← Agrega esta línea
   ]
   ```

3. **Crea el modelo `Empleado`**
   ```python
   # app_empleado/models.py
   from django.db import models

   class Empleado(models.Model):
       nombre = models.CharField(max_length=100, verbose_name="Nombre")
       edad = models.PositiveIntegerField(verbose_name="Edad")

       def __str__(self):
           return self.nombre

       class Meta:
           verbose_name = "Empleado"
           verbose_name_plural = "Empleados"
           ordering = ['nombre']
   ```

4. **Registra el modelo en el admin**
   ```python
   # app_empleado/admin.py
   from django.contrib import admin
   from .models import Empleado

   admin.site.register(Empleado)
   ```

5. **Haz migraciones**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

---

### 🧪 Ejercicio 5
1. Crea un empleado desde el panel de admin.
2. Verifica en el visor de SQLite que se haya guardado.

---

### ✅ Solución
La tabla `app_empleado_empleado` debe tener al menos un registro.

---

## 💡 **Módulo 6: Vistas y Respuestas Web**

### 🎯 Objetivo
Crear vistas que muestren información al usuario usando `HttpResponse` y `render`.

---

### 💻 Pasos a seguir

1. **Crea una vista simple**
   ```python
   # app_empleado/views.py
   from django.http import HttpResponse

   def ver_pagina(request):
       return HttpResponse("<h1>¡Bienvenido!</h1><p><a href='/listar'>Ver empleados</a></p>")
   ```

2. **Crea la vista de listado**
   ```python
   from django.shortcuts import render
   from .models import Empleado

   def listar_empleados(request):
       empleados = Empleado.objects.all()
       return render(request, 'listar_empleados.html', {'empleados': empleados})
   ```

3. **Crea la carpeta de plantillas**
   ```
   app_empleado/templates/
   ```

---

### 🧪 Ejercicio 6
Crea un archivo `inicio.html` y haz que `ver_pagina` lo renderice (en lugar de `HttpResponse`).

---

### ✅ Solución
```python
def ver_pagina(request):
    return render(request, 'inicio.html')
```

---

## 🔗 **Módulo 7: Enrutamiento y Navegación**

### 🎯 Objetivo
Configurar las URLs para que el usuario pueda navegar entre páginas.

---

### 💻 Pasos a seguir

1. **Crea `urls.py` en la app**
   ```python
   # app_empleado/urls.py
   from django.urls import path
   from . import views

   urlpatterns = [
       path('', views.ver_pagina, name='ver_pagina'),
       path('listar/', views.listar_empleados, name='listar_empleados'),
   ]
   ```

2. **Incluye las URLs en el proyecto**
   ```python
   # backend_empleado/urls.py
   from django.urls import path, include

   urlpatterns = [
       path('admin/', admin.site.urls),
       path('', include('app_empleado.urls')),
   ]
   ```

---

### 🧪 Ejercicio 7
Agrega una ruta `/about` que muestre una página con información del curso.

---

### ✅ Solución
Crea vista `about` y agrega ruta en `urls.py`.

---

## ✏️ **Módulo 8: Sistema CRUD Básico (Sin Forms.py)**

### 🎯 Objetivo
Implementar operaciones CRUD completas sin usar `forms.py`.

---

### 💻 Código completo en `views.py`

```python
from django.shortcuts import render, redirect, get_object_or_404
from .models import Empleado

def crear_empleado(request):
    if request.method == 'POST':
        nombre = request.POST['nombre']
        edad = request.POST['edad']
        Empleado.objects.create(nombre=nombre, edad=edad)
        return redirect('listar_empleados')
    return render(request, 'crear_empleado.html')

def actualizar_empleado(request, id):
    empleado = get_object_or_404(Empleado, id=id)
    if request.method == 'POST':
        empleado.nombre = request.POST['nombre']
        empleado.edad = request.POST['edad']
        empleado.save()
        return redirect('listar_empleados')
    return render(request, 'editar_empleado.html', {'empleado': empleado})

def borrar_empleado(request, id):
    empleado = get_object_or_404(Empleado, id=id)
    if request.method == 'POST':
        empleado.delete()
        return redirect('listar_empleados')
    return render(request, 'borrar_empleado.html', {'empleado': empleado})
```

---

### 🧪 Ejercicio 8
Agrega un campo `puesto` al modelo `Empleado` y actualiza el CRUD.

---

### ✅ Solución
1. Agrega `puesto = models.CharField(...)` en el modelo.
2. Haz migraciones.
3. Actualiza formularios y vistas.

---

## 🎨 **Módulo 9: Interfaz Web Atractiva (Frontend con Bootstrap)**

### 🎯 Objetivo
Diseñar una interfaz moderna y atractiva usando Bootstrap 5.

---

### 💻 Ejemplo: `listar_empleados.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>Empleados</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
  <div class="container mt-5">
    <h1 class="text-center">📋 Empleados</h1>
    <a href="/crear" class="btn btn-success mb-3">➕ Agregar</a>
    <table class="table table-striped">
      <thead class="table-dark">
        <tr>
          <th>Nombre</th>
          <th>Edad</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody>
        {% for emp in empleados %}
        <tr>
          <td>{{ emp.nombre }}</td>
          <td>{{ emp.edad }}</td>
          <td>
            <a href="/editar/{{ emp.id }}" class="btn btn-warning btn-sm">✏️</a>
            <a href="/borrar/{{ emp.id }}" class="btn btn-danger btn-sm">🗑️</a>
          </td>
        </tr>
        {% endfor %}
      </tbody>
    </table>
  </div>
</body>
</html>
```

---

### 🧪 Ejercicio 9
Cambia los colores del botón "Agregar" a azul (`btn-primary`) y agrega un pie de página.

---

### ✅ Solución
Usa `btn-primary` y agrega `<footer>` al final.

---

## 📁 **Módulo 10: Estructura Final del Proyecto**

### 🎯 Objetivo
Organizar todo el proyecto de forma profesional y lista para entregar.

---

### ✅ Estructura final

```
practica_1/
├── backend_empleado/
├── app_empleado/
│   ├── templates/
│   │   ├── listar_empleados.html
│   │   ├── crear_empleado.html
│   │   ├── editar_empleado.html
│   │   └── borrar_empleado.html
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── manage.py
├── db.sqlite3
├── requirements.txt
└── .venv/
```

---

## 🏁 **Proyecto Final: Sistema de Gestión de Productos**

### 🎯 Objetivo
Aplicar todo lo aprendido en un nuevo proyecto con imágenes.

---

### 💻 Modelo `Producto`

```python
# models.py
class Producto(models.Model):
    nombre = models.CharField(max_length=100)
    descripcion = models.TextField()
    precio = models.DecimalField(max_digits=10, decimal_places=2)
    stock = models.PositiveIntegerField()
    fecha_creacion = models.DateTimeField(auto_now_add=True)
    imagen = models.ImageField(upload_to='productos/', null=True, blank=True)
```

### 💡 Recuerda:
```bash
pip install Pillow
```

Y en `settings.py`:
```python
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

En `urls.py` principal:
```python
from django.conf import settings
from django.conf.urls.static import static

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

## 📚 **Recursos Finales**

- 📘 [Documentación Django](https://docs.djangoproject.com)
- 🎨 [Bootstrap 5](https://getbootstrap.com)
- 🐍 [Python para principiantes](https://www.python.org/about/gettingstarted/)

---

✅ **¡Felicidades!** Has completado el curso.  
Ahora puedes crear tus propias aplicaciones web con Django.

---

## 📥 ¿Qué sigue?

¿Te gustaría que te genere:
- ✅ Un **archivo ZIP** con todo el proyecto final funcionando?
- ✅ Un **PDF imprimible** del curso completo?
- ✅ Una **plantilla de Google Classroom** o **Canvas** para impartirlo?
- ✅ Un **certificado de finalización** para tus estudiantes?

Dime qué necesitas y te lo preparo en minutos.
