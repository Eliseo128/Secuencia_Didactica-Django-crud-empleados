¡Claro! A continuación, te presento una versión **elegante, atractiva y profesional** del prompt, manteniendo **todos los puntos numerados y las indicaciones técnicas con precisión**, pero con un diseño visual más claro, motivador y adecuado para entornos educativos o documentación técnica.

---

# 🌐 **Curso Práctico: Desarrollo Web Profesional con Django y Python**

> *"De cero a aplicación funcional: construye tu primer sistema web con Django en Windows"*

---

### 🎯 **Perfil del Estudiante**
- **Nivel:** Principiante  
- **Escolaridad:** Preparatoria (sin experiencia previa en desarrollo web)  
- **Sistema Operativo:** Windows  
- **Objetivo:** Aprender a crear aplicaciones web profesionales utilizando tecnologías modernas y buenas prácticas.

---

### 🛠️ **Tecnologías y Herramientas**
| Categoría | Tecnología |
|---------|-----------|
| Lenguaje | Python (última versión) |
| Framework | Django |
| Frontend | HTML5, CSS3, JavaScript, Bootstrap 5 |
| Editor | Visual Studio Code |
| Base de datos | SQLite (por defecto en Django) |

---

### 💻 **Software Requerido**
- ✅ **Python** (versión recomendada: 3.11 o superior)  
- ✅ **Visual Studio Code** (con las siguientes extensiones instaladas):
  - Python
  - Pylance
  - Django
  - HTML CSS Support
  - SQLite Viewer *(recomendado para inspeccionar la base de datos)*
  - Bracket Pair Colorizer *(opcional, mejora legibilidad)*
  - Live Server *(opcional, útil para previsualizar HTML)*

---

### 📁 **Estructura del Proyecto**
Todos los archivos se organizarán dentro de una carpeta principal para mantener el orden y facilitar el seguimiento del curso.

---

## 🧭 **Procedimiento Paso a Paso: Construcción de un Sistema CRUD con Django**

Sigue cada paso con atención. Al finalizar, tendrás una **aplicación web completa y funcional** para gestionar empleados, con interfaz atractiva y operaciones CRUD (Crear, Leer, Actualizar, Eliminar).

---

1. 🔹 **Crear carpeta de trabajo**  
   Crea una carpeta llamada `Curso_Django` en tu disco local (ej. `C:\Curso_Django`). Aquí se almacenarán todos los proyectos del curso.

2. 🔹 **Crear subcarpeta para el primer proyecto**  
   Dentro de `Curso_Django`, crea una subcarpeta llamada `practica_1`.

3. 🔹 **Abrir VS Code desde la carpeta `practica_1`**  
   Abre Visual Studio Code y carga la carpeta `practica_1` como espacio de trabajo.

4. 🔹 **Verificar versiones de Python y pip**  
   Abre una nueva terminal en VS Code (`Ctrl + Ñ`) y ejecuta:
   ```bash
   python --version
   pip --version
   ```
   Asegúrate de que Python esté instalado correctamente.

5. 🔹 **Crear entorno virtual**  
   En la terminal, ejecuta:
   ```bash
   python -m venv .venv
   ```
   Esto crea un entorno aislado para gestionar dependencias.

6. 🔹 **Activar el entorno virtual**  
   Ejecuta:
   ```bash
   .venv\Scripts\activate
   ```
   Verás que el prompt cambia, mostrando `(.venv)` al inicio.

7. 🔹 **Seleccionar intérprete de Python en VS Code**  
   Presiona `Ctrl + Shift + P`, busca **"Python: Select Interpreter"** y elige el que apunte a `.venv`.

8. 🔹 **Instalar Django y verificar versión**  
   Ejecuta:
   ```bash
   pip install django
   django-admin --version
   ```
   Verifica que se instale Django (ej. 4.2+).

9. 🔹 **Crear el proyecto Django**  
   Ejecuta:
   ```bash
   django-admin startproject backend_empleado .
   ```
   El punto (`.`) evita crear una carpeta extra.

10. 🔹 **Ejecutar el servidor de desarrollo**  
    ```bash
    python manage.py runserver
    ```

11. 🔹 **Ver la página web inicial**  
    Abre el navegador y visita:  
    [http://127.0.0.1:8000](http://127.0.0.1:8000)  
    Deberás ver la página de bienvenida de Django.

12. 🔹 **Detener el servidor**  
    En la terminal, presiona `Ctrl + C` para detener el servidor.

13. 🔹 **Realizar migración inicial**  
    Ejecuta:
    ```bash
    python manage.py migrate
    ```
    Esto crea la base de datos `db.sqlite3` con tablas predeterminadas.

14. 🔹 **Hacer migraciones** *(preparar cambios del modelo)*  
    Aunque no hay cambios aún, este paso será clave más adelante.

15. 🔹 **Crear superusuario**  
    Ejecuta:
    ```bash
    python manage.py createsuperuser
    ```
    Ingresa:
    - **Username:** admin  
    - **Email:** (opcional)  
    - **Password:** mínimo 8 caracteres (ej. `12345678`)

16. 🔹 **Acceder al panel de administración**  
    Inicia el servidor y ve a:
    [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)  
    Inicia sesión con el superusuario creado.

17. 🔹 **Detener el servidor nuevamente**  
    Usa `Ctrl + C` en la terminal.

18. 🔹 **Crear la aplicación `app_empleado`**  
    ```bash
    python manage.py startapp app_empleado
    ```

19. 🔹 **Crear archivo `urls.py` en `app_empleado`**  
    Dentro de la app, crea el archivo `app_empleado/urls.py` para gestionar rutas.

20. 🔹 **Crear vista `ver_pagina` con `HttpResponse`**  
    En `views.py`, define una función que devuelva un mensaje simple usando `HttpResponse`.

21. 🔹 **Registrar la app en `settings.py`**  
    Agrega `'app_empleado'` a la lista `INSTALLED_APPS` en `backend_empleado/settings.py`.

22. 🔹 **Incluir las URLs de la app en el proyecto principal**  
    En `backend_empleado/urls.py`, usa `include()` para enrutar a `app_empleado.urls`.

23. 🔹 **Ejecutar servidor y probar `ver_pagina`**  
    Accede a `http://127.0.0.1:8000` y verifica que se muestre el mensaje.

24. 🔹 **Inspeccionar la página web**  
    Usa las herramientas del navegador (F12) para explorar el HTML generado.

25. 🔹 **Crear modelo `Empleado` en `models.py`**  
    Define una clase con:
    - `nombre = models.CharField(max_length=100)`
    - `edad = models.PositiveIntegerField()`
    - Constructor `__str__` y clase `Meta` para metadatos.

26. 🔹 **Registrar el modelo en `admin.py`**  
    Usa `admin.site.register(Empleado)` para que aparezca en el panel de administración.

27. 🔹 **Generar migraciones del modelo**  
    ```bash
    python manage.py makemigrations
    ```

28. 🔹 **Aplicar migraciones a la base de datos**  
    ```bash
    python manage.py migrate
    ```

29. 🔹 **Usar visor de base de datos para SQLite**  
    Instala la extensión **SQLite Viewer** en VS Code y abre `db.sqlite3` para verificar la tabla `app_empleado_empleado`.

30. 🔹 **Acceder nuevamente al panel de administración**  
    Inicia el servidor y ve al `/admin` para agregar empleados manualmente.

31. 🔹 **Detener el servidor**  
    `Ctrl + C` en la terminal.

32. 🔹 **Crear vista `listar_empleados` con `render`**  
    En `views.py`, obtén todos los empleados y renderiza una plantilla HTML.

33. 🔹 **Crear carpeta `templates`**  
    Dentro de `app_empleado`, crea una carpeta llamada `templates`.

34. 🔹 **Crear archivo `listar_empleados.html`**  
    Dentro de `templates`, crea el archivo HTML para mostrar la lista.

35. 🔹 **Diseñar tabla con botones de acción**  
    Usa HTML, CSS y Bootstrap para crear una tabla con botones:  
    ✏️ **Editar** y 🗑️ **Borrar** (con enlaces a rutas futuras).

36. 🔹 **Actualizar `urls.py` de `app_empleado`**  
    Añade rutas para: listar, crear, editar y borrar empleados.

37. 🔹 **Ejecutar servidor y probar listado**  
    Verifica que la tabla se muestre correctamente con los datos.

38. 🔹 **Detener el servidor**  
    `Ctrl + C`.

39. 🔹 **Crear funciones CRUD en `views.py`**  
    Implementa:
    - `crear_empleado`
    - `actualizar_empleado`
    - `borrar_empleado`  
    Usa `request.POST`, `get_object_or_404`, y redirecciones.

40. 🔹 **Crear archivos HTML para cada vista**  
    Dentro de `templates`, crea:
    - `crear_empleado.html`
    - `editar_empleado.html`
    - `borrar_empleado.html`

41. 🔹 **Actualizar `urls.py` con todas las rutas**  
    Asegúrate de que cada función tenga su URL correspondiente.

42. 🔹 **Ejecutar servidor y probar todo el sistema**  
    Verifica que todas las operaciones CRUD funcionen correctamente.

---

## ✅ **Restricciones y Buenas Prácticas Aplicadas**

43. ❌ **No utilizar `forms.py`**  
    Todo el manejo de formularios se hará directamente en las vistas.

44. ❌ **No usar `base.html` (plantilla base)**  
    Cada archivo HTML será independiente, ideal para principiantes.

45. ✅ **Incluir comentarios en el código**  
    Agrega comentarios breves en:
    - Archivos Python (`#`)
    - Archivos HTML (`<!-- -->`)  
    Explica qué hace cada bloque.

46. ✅ **Crear estructura de carpetas completa**  
    Asegúrate de que la estructura final sea clara y organizada.

47. ✅ **Hacer el proyecto atractivo para estudiantes**  
    Usa **Bootstrap 5** para:
    - Diseño responsive
    - Tablas con sombras y hover
    - Botones con iconos
    - Fuentes modernas
    - Colores profesionales

---

## 🎓 **Resultado Esperado**

Al finalizar, el estudiante tendrá:
- Un **proyecto Django funcional** con CRUD completo.
- Experiencia práctica en **modelos, vistas, URLs y plantillas**.
- Una **interfaz web atractiva y usable**.
- Conocimientos para continuar con proyectos más avanzados.

---

> 💡 **Consejo final:**  
> Este proyecto puede incluirse en un portafolio personal o currículum como evidencia de habilidades técnicas en desarrollo web.

---

¿Te gustaría que convierta este prompt en un **documento PDF listo para imprimir o compartir**?  
O ¿deseas un **archivo ZIP con la estructura de carpetas y código base** para que los estudiantes lo descarguen y empiecen más rápido? Puedo ayudarte a generarlo.
