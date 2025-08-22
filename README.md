# Secuencia_Didactica-Django-crud-empleados
secuencia didáctica
¡Perfecto! A continuación, te presento un **curso paso a paso de Django con Python** para crear una **aplicación web profesional de empleados**, ideal para estudiantes con nivel **principiante** y escolaridad de **preparatoria**, usando **Windows**, **VS Code**, y tecnologías como **Python, Django, HTML, CSS, JavaScript y Bootstrap**.

Este curso está diseñado para que aprendas **haciendo**, con explicaciones claras, estructura limpia y resultados visibles. Además, cumplimos con todos tus requisitos: sin `forms.py`, sin `base.html`, comentarios en código, y una interfaz atractiva con Bootstrap.

---

## ✅ **Requisitos previos instalados**
- ✅ Python (última versión, ej. 3.11 o superior)
- ✅ VS Code
- ✅ Extensiones en VS Code:
  - Python
  - Pylance
  - Django
  - HTML CSS Support
  - Live Server (opcional)
  - SQLite Viewer (recomendado)
  - Bracket Pair Colorizer (opcional, ayuda visual)
- ✅ Conexión a internet

---

## 📁 1. Crear carpeta de trabajo

```bash
Crea manualmente en tu disco C: o donde prefieras:
C:\Curso_Django\
```

> Esta será tu carpeta principal del curso.

---

## 📂 2. Crear subcarpeta para el primer proyecto

Dentro de `Curso_Django`, crea:
```
C:\Curso_Django\practica_1
```

---

## 💻 3. Abrir VS Code desde `practica_1`

1. Abre VS Code.
2. Haz clic en **File > Open Folder**.
3. Navega a `C:\Curso_Django\practica_1` y ábrelo.

---

## 🖥️ 4. Abrir terminal y verificar Python y pip

En VS Code, abre la terminal:

```bash
Ctrl + Ñ   (o Terminal > New Terminal)
```

Verifica versiones:

```bash
python --version
pip --version
```

> Debe mostrar algo como:
> ```
> Python 3.11.5
> pip 23.2.1
> ```

---

## 🧪 5. Crear entorno virtual `.venv`

En la terminal:

```bash
python -m venv .venv
```

Esto crea una carpeta `.venv` con tu entorno aislado.

---

## 🔌 6. Activar entorno virtual

```bash
.venv\Scripts\activate
```

> Verás que el prompt cambia a:
> ```
> (.venv) C:\Curso_Django\practica_1>
> ```

---

## 🐍 7. Seleccionar intérprete de Python en VS Code

1. Presiona `Ctrl + Shift + P`
2. Escribe: **Python: Select Interpreter**
3. Elige el que diga:  
   `Python 3.x.x ('.venv': venv)`  
   (asegúrate de que apunte al `.venv`)

---

## 📦 8. Instalar Django y verificar versión

```bash
pip install django
```

Verifica instalación:

```bash
django-admin --version
```

> Ejemplo de salida: `4.2.7`

> 💡 Recomendación: Guarda las dependencias
```bash
pip freeze > requirements.txt
```

---

## 🏗️ 9. Crear el proyecto Django: `backend_empleado`

```bash
django-admin startproject backend_empleado .
```

> El punto `.` evita crear una carpeta extra.

Estructura actual:
```
practica_1/
├── backend_empleado/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
├── .venv/
└── requirements.txt
```

---

## ▶️ 10. Ejecutar servidor integrado

```bash
python manage.py runserver
```

---

## 🌐 11. Ver página web

Abre el navegador y ve a:

```
http://127.0.0.1:8000
```

> Deberás ver la página de bienvenida de Django:  
> **"The install worked successfully! Congratulations."**

---

## ⏹️ 12. Detener servidor

En la terminal, presiona:

```bash
Ctrl + C
```

Y confirma con `Y`.

---

## 🔄 13. Realizar migración (crear tablas iniciales)

```bash
python manage.py migrate
```

> Esto crea la base de datos `db.sqlite3` con tablas como `auth_user`, `admin`, etc.

---

## 📂 14. Hacer migraciones (aunque no hay cambios aún)

Este paso es redundante ahora, pero más adelante será clave.  
Solo recuerda:  
- `makemigrations`: prepara cambios del modelo
- `migrate`: aplica cambios a la base de datos

---

## 👤 15. Crear superusuario

```bash
python manage.py createsuperuser
```

Ingresa:
- **Username**: admin
- **Email**: admin@example.com
- **Password**: 12345678 (mínimo 8 caracteres)
- **Password (again)**: 12345678

> ⚠️ Django no muestra la contraseña al escribir.

---

## ▶️ 16. Ejecutar servidor y acceder al panel de administración

```bash
python manage.py runserver
```

Ve al navegador:

```
http://127.0.0.1:8000/admin
```

Inicia sesión con:
- Usuario: `admin`
- Contraseña: `12345678`

> Verás el panel de administración de Django.

---

## ⏹️ 17. Detener servidor

```bash
Ctrl + C
```

---

## 🧱 18. Crear aplicación `app_empleado`

```bash
python manage.py startapp app_empleado
```

Estructura ahora:
```
app_empleado/
├── migrations/
├── __init__.py
├── admin.py
├── apps.py
├── models.py
├── tests.py
└── views.py
```

---

## 🔗 19. En `app_empleado` crear `urls.py`

Dentro de `app_empleado`, crea el archivo:

```
app_empleado/urls.py
```

Contenido:

```python
# URLs de la app_empleado
from django.urls import path
from . import views

urlpatterns = [
    path('', views.ver_pagina, name='ver_pagina'),
    path('listar/', views.listar_empleados, name='listar_empleados'),
    path('crear/', views.crear_empleado, name='crear_empleado'),
    path('editar/<int:id>/', views.actualizar_empleado, name='actualizar_empleado'),
    path('borrar/<int:id>/', views.borrar_empleado, name='borrar_empleado'),
]
```

---

## 💬 20. En `views.py` crear función `ver_pagina`

Abre `app_empleado/views.py`:

```python
# Vista simple con HttpResponse
from django.http import HttpResponse

def ver_pagina(request):
    # Página de inicio simple
    return HttpResponse("<h1>¡Bienvenido al Sistema de Empleados!</h1><p><a href='/listar'>Ver empleados</a></p>")
```

---

## 🧩 21. Agregar `app_empleado` en `settings.py`

Abre `backend_empleado/settings.py`

Busca `INSTALLED_APPS` y agrega:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app_empleado',  # ← Agrega esta línea
]
```

---

## 🔗 22. Incluir ruta en `backend_empleado/urls.py`

Abre `backend_empleado/urls.py`:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('app_empleado.urls')),  # Incluye las URLs de la app
]
```

---

## ▶️ 23. Ejecutar servidor y ver `ver_pagina`

```bash
python manage.py runserver
```

Ve a:

```
http://127.0.0.1:8000
```

> Deberás ver el mensaje de bienvenida con el enlace.

---

## 🔍 24. Inspeccionar página web

Haz clic derecho > "Inspeccionar" en el navegador.  
Observa el HTML generado.

---

## 🗃️ 25. Crear modelo `Empleado` en `models.py`

Abre `app_empleado/models.py`:

```python
from django.db import models

class Empleado(models.Model):
    nombre = models.CharField(max_length=100, verbose_name="Nombre del Empleado")
    edad = models.PositiveIntegerField(verbose_name="Edad")

    def __str__(self):
        return f"{self.nombre} ({self.edad} años)"

    class Meta:
        verbose_name = "Empleado"
        verbose_name_plural = "Empleados"
        ordering = ['nombre']
```

---

## 📂 26. Registrar modelo en `admin.py`

Abre `app_empleado/admin.py`:

```python
from django.contrib import admin
from .models import Empleado

# Registra el modelo Empleado en el panel de admin
admin.site.register(Empleado)
```

---

## 🔄 27. Hacer migraciones

```bash
python manage.py makemigrations
```

> Salida: `Migrations for 'app_empleado': ...`

---

## 💾 28. Aplicar migraciones

```bash
python manage.py migrate
```

> Crea la tabla `app_empleado_empleado` en `db.sqlite3`

---

## 🔍 29. Usar visor de base de datos (SQLite)

**Recomendado:**
- Extensión de VS Code: **SQLite Viewer**
- O software externo: **DB Browser for SQLite** (gratis)

Pasos:
1. Abre `db.sqlite3` en VS Code (aparece en la carpeta del proyecto).
2. Haz clic derecho sobre el archivo → "Open in SQLite Viewer".
3. Ve a la pestaña "Tables" y busca `app_empleado_empleado`.

> Ahora puedes ver la estructura de tu tabla.

---

## ▶️ 30. Acceder al panel de administración

```bash
python manage.py runserver
```

Ve a:

```
http://127.0.0.1:8000/admin
```

Inicia sesión y haz clic en **Empleados** → **Añadir Empleado**.

Agrega algunos empleados:
- Nombre: Juan Pérez, Edad: 30
- Nombre: Ana Gómez, Edad: 25

---

## ⏹️ 31. Detener servidor

```bash
Ctrl + C
```

---

## 📋 32. Crear vista `listar_empleados` con `render`

En `app_empleado/views.py`:

```python
from django.shortcuts import render, redirect
from .models import Empleado

def listar_empleados(request):
    # Obtiene todos los empleados de la base de datos
    empleados = Empleado.objects.all()
    # Renderiza la plantilla con los datos
    return render(request, 'listar_empleados.html', {'empleados': empleados})
```

---

## 📁 33. Crear carpeta `templates`

Dentro de `app_empleado`, crea:

```
app_empleado/templates/
```

---

## 📄 34. Crear `listar_empleados.html`

Archivo: `app_empleado/templates/listar_empleados.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Listado de Empleados</title>
    <!-- Bootstrap CDN -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
    <div class="container mt-5">
        <h1 class="text-center text-primary">📋 Empleados Registrados</h1>
        <div class="d-grid gap-2 d-md-flex justify-content-md-end mb-3">
            <a href="/crear" class="btn btn-success">➕ Agregar Empleado</a>
        </div>

        <!-- Tabla de empleados -->
        <table class="table table-striped table-hover shadow">
            <thead class="table-dark">
                <tr>
                    <th>Nombre</th>
                    <th>Edad</th>
                    <th>Acciones</th>
                </tr>
            </thead>
            <tbody>
                {% for empleado in empleados %}
                <tr>
                    <td>{{ empleado.nombre }}</td>
                    <td>{{ empleado.edad }}</td>
                    <td>
                        <a href="/editar/{{ empleado.id }}" class="btn btn-warning btn-sm">✏️ Editar</a>
                        <a href="/borrar/{{ empleado.id }}" class="btn btn-danger btn-sm">🗑️ Borrar</a>
                    </td>
                </tr>
                {% empty %}
                <tr>
                    <td colspan="3" class="text-center text-muted">No hay empleados registrados.</td>
                </tr>
                {% endfor %}
            </tbody>
        </table>
    </div>
</body>
</html>
```

---

## 🔗 35. Actualizar `urls.py` de `app_empleado`

Ya está hecho en el paso 19. Confirma que tenga todas las rutas.

---

## ▶️ 36. Ejecutar y ver `listar_empleados`

```bash
python manage.py runserver
```

Ve a:

```
http://127.0.0.1:8000/listar
```

> Deberás ver la tabla con los empleados agregados desde el admin.

---

## ⏹️ 37. Detener servidor

```bash
Ctrl + C
```

---

## ✏️ 39. Crear funciones CRUD en `views.py`

Actualiza `app_empleado/views.py`:

```python
from django.shortcuts import render, redirect, get_object_or_404
from .models import Empleado

def ver_pagina(request):
    return HttpResponse("<h1>¡Bienvenido al Sistema de Empleados!</h1><p><a href='/listar'>Ver empleados</a></p>")

def listar_empleados(request):
    empleados = Empleado.objects.all()
    return render(request, 'listar_empleados.html', {'empleados': empleados})

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

## 📄 40. Crear archivos HTML adicionales

### 🟢 `crear_empleado.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Crear Empleado</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
    <div class="container mt-5">
        <h2 class="text-success">➕ Crear Nuevo Empleado</h2>
        <form method="post">
            {% csrf_token %}
            <div class="mb-3">
                <label>Nombre:</label>
                <input type="text" name="nombre" class="form-control" required>
            </div>
            <div class="mb-3">
                <label>Edad:</label>
                <input type="number" name="edad" class="form-control" required>
            </div>
            <button type="submit" class="btn btn-success">Guardar</button>
            <a href="/listar" class="btn btn-secondary">Cancelar</a>
        </form>
    </div>
</body>
</html>
```

### 🟡 `editar_empleado.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Editar Empleado</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
    <div class="container mt-5">
        <h2 class="text-warning">✏️ Editar Empleado</h2>
        <form method="post">
            {% csrf_token %}
            <div class="mb-3">
                <label>Nombre:</label>
                <input type="text" name="nombre" value="{{ empleado.nombre }}" class="form-control" required>
            </div>
            <div class="mb-3">
                <label>Edad:</label>
                <input type="number" name="edad" value="{{ empleado.edad }}" class="form-control" required>
            </div>
            <button type="submit" class="btn btn-warning">Actualizar</button>
            <a href="/listar" class="btn btn-secondary">Cancelar</a>
        </form>
    </div>
</body>
</html>
```

### 🔴 `borrar_empleado.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Eliminar Empleado</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
    <div class="container mt-5">
        <h2 class="text-danger">🗑️ ¿Eliminar Empleado?</h2>
        <p>¿Estás seguro de que deseas eliminar a <strong>{{ empleado.nombre }}</strong>?</p>
        <form method="post">
            {% csrf_token %}
            <button type="submit" class="btn btn-danger">Sí, eliminar</button>
            <a href="/listar" class="btn btn-secondary">Cancelar</a>
        </form>
    </div>
</body>
</html>
```

---

## 🔗 41. Actualizar `urls.py` de `app_empleado`

Ya está completo desde el paso 19. Solo verifica que tenga todas las rutas.

---

## ▶️ 42. Ejecutar y probar todo el sistema

```bash
python manage.py runserver
```

Prueba todas las funciones:
- `/crear` → Agregar empleado
- `/listar` → Ver todos
- Botón ✏️ → Editar
- Botón 🗑️ → Confirmar eliminación

> ✅ ¡Tu sistema CRUD está funcionando!

---

## ✅ 43. No usar `forms.py` → ✔️ Cumplido
## ✅ 44. No usar `base.html` → ✔️ Cumplido (plantillas independientes)
## ✅ 45. Comentarios en código → ✔️ Incluidos en Python y HTML
## ✅ 46. Estructura completa:

```
practica_1/
├── backend_empleado/
│   ├── settings.py
│   ├── urls.py
│   └── ...
├── app_empleado/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── admin.py
│   └── templates/
│       ├── listar_empleados.html
│       ├── crear_empleado.html
│       ├── editar_empleado.html
│       └── borrar_empleado.html
├── manage.py
├── db.sqlite3
├── requirements.txt
└── .venv/
```

## 🎉 47. Proyecto atractivo → ✔️ Con Bootstrap, colores, iconos, diseño limpio

---

## 📚 Consejos finales

- Usa **Live Server** en VS Code para previsualizar HTML.
- Guarda copias de seguridad.
- Practica modificando estilos o agregando campos (ej: salario, puesto).
- Explora más de Bootstrap: [https://getbootstrap.com](https://getbootstrap.com)

---

## 🎓 ¿Qué aprendiste?

- Entornos virtuales
- Estructura de Django
- MVC (Modelo-Vista-Controlador)
- ORM de Django
- Sistema CRUD completo
- Uso de plantillas y variables
- Interacción con base de datos SQLite
- Diseño web con Bootstrap

---

¡Felicidades! Has completado tu **primer proyecto profesional con Django** 💪  
Ahora puedes expandirlo: agregar búsqueda, filtros, imágenes, o autenticación de usuarios.

¿Quieres el siguiente paso?  
👉 **Agregar login de usuarios** o **desplegar en internet con Render o Railway**.

¿Te gustaría que te lo envíe como un archivo ZIP listo para usar?  
Puedo ayudarte a estructurarlo.
