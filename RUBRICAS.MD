¡Claro! A continuación, te presento una **lista de cotejo** y una **rúbrica de evaluación** detalladas, alineadas con la **secuencia didáctica en tres momentos (apertura, desarrollo y cierre)** y enfocadas específicamente en el **proyecto final: Sistema de Gestión de Productos con Django**.

Estas herramientas permiten al docente evaluar de forma objetiva, clara y formativa el desempeño del estudiante, y al alumno conocer con anticipación los criterios de éxito.

---

# ✅ **Lista de Cotejo: Proyecto Final – Sistema de Gestión de Productos con Django**

> ✔️ **Sí / ❌ No** – Evaluación binaria de cumplimiento de elementos técnicos y funcionales.

| Criterio | Sí | No | Observaciones |
|--------|----|----|---------------|
| 1. Carpeta `proyecto_productos` creada dentro de `Curso_Django` | | | |
| 2. Entorno virtual `.venv` activado y configurado | | | |
| 3. Archivo `requirements.txt` generado con `pip freeze` | | | |
| 4. Proyecto Django `backend_productos` creado correctamente | | | |
| 5. Aplicación `app_productos` creada y registrada en `settings.py` | | | |
| 6. Modelo `Producto` con **6 campos**, incluyendo `imagen = models.ImageField` | | | |
| 7. Se instaló `Pillow` para manejo de imágenes | | | |
| 8. Se realizaron `makemigrations` y `migrate` correctamente | | | |
| 9. Configuración de `MEDIA_URL` y `MEDIA_ROOT` en `settings.py` | | | |
| 10. URLs configuradas en `backend_productos/urls.py` con `static()` para imágenes | | | |
| 11. Archivo `urls.py` en `app_productos` con rutas CRUD completas | | | |
| 12. Vistas: `listar_productos`, `crear_producto`, `editar_producto`, `borrar_producto` | | | |
| 13. Plantillas HTML en carpeta `templates` (independientes, sin `base.html`) | | | |
| 14. Formularios funcionales sin uso de `forms.py` | | | |
| 15. Interfaz con **Bootstrap 5** (tablas, botones, diseño responsive) | | | |
| 16. Imágenes de productos visibles en el listado (`<img src="{{ producto.imagen.url }}">`) | | | |
| 17. Operaciones CRUD funcionando correctamente | | | |
| 18. Comentarios en código Python y HTML | | | |
| 19. Proyecto ejecutable (`python manage.py runserver`) sin errores | | | |
| 20. Entrega ordenada, con estructura clara de carpetas y archivos | | | |

> ✅ **Total de ítems cumplidos:** ___ / 20  
> 📝 **Observaciones generales del docente:**  
> ___________________________________________________________  
> ___________________________________________________________

---

# 📊 **Rúbrica de Evaluación: Proyecto Final – Sistema de Gestión de Productos**

> Evaluación por niveles: **Excelente (4), Bueno (3), Satisfactorio (2), En desarrollo (1), Insuficiente (0)**

| Criterio | Excelente (4) | Bueno (3) | Satisfactorio (2) | En desarrollo (1) | Insuficiente (0) | Puntaje |
|--------|---------------|-----------|-------------------|-------------------|------------------|--------|
| **Funcionalidad del CRUD**<br>Creación, lectura, actualización y eliminación completas y sin errores. | Todas las operaciones funcionan perfectamente. | 3 de 4 operaciones funcionan bien. | 2 operaciones funcionan. | 1 operación funciona. | Ninguna funciona. | /4 |
| **Modelo `Producto`**<br>6 campos correctos, incluyendo `ImageField`, `__str__`, `Meta`. | Modelo completo, bien estructurado y con metadatos. | 5 campos correctos, falta uno menor. | 4 campos correctos. | Menos de 4 campos o sin imagen. | No existe o está vacío. | /4 |
| **Manejo de imágenes**<br>Subida, almacenamiento y visualización correcta en el listado. | Imágenes se suben, guardan y muestran correctamente. | Imágenes se suben pero no se muestran bien. | Imágenes se suben, pero no se guardan en `media/`. | No se muestra imagen, pero hay campo. | No hay campo ni funcionalidad. | /4 |
| **Interfaz de usuario**<br>Diseño atractivo con Bootstrap, tablas, botones, responsividad. | Interfaz moderna, profesional y usable. | Uso claro de Bootstrap, buen diseño. | Diseño básico con algunos estilos. | Uso mínimo de CSS. | Solo HTML plano sin estilo. | /4 |
| **Estructura del proyecto**<br>Carpeta `templates`, `urls.py`, `views.py`, etc., bien organizados. | Estructura limpia, lógica y completa. | Mayoría de archivos en su lugar. | Algunas carpetas faltantes o mal ubicadas. | Estructura desordenada. | Archivos dispersos o faltantes. | /4 |
| **Código limpio y comentado**<br>Comentarios breves en Python y HTML que explican el funcionamiento. | Comentarios claros en todas las partes clave. | Comentarios en la mayoría de archivos. | Algunos comentarios presentes. | Muy pocos comentarios. | Sin comentarios. | /4 |
| **Configuración técnica**<br>`settings.py`, `urls.py`, `MEDIA_ROOT`, migraciones, etc. | Todo configurado correctamente. | 1 error menor (ej. ruta de media). | 2 errores técnicos. | Varios errores de configuración. | No se ejecuta el proyecto. | /4 |
| **Autonomía y creatividad**<br>Uso de iconos, mensajes personalizados, validaciones simples, etc. | Muestra iniciativa, diseño personalizado. | Pequeñas mejoras propias. | Cumple lo básico sin extras. | Copia directa sin adaptación. | No muestra esfuerzo propio. | /4 |

> **Puntaje total:** ___ / 32  
> **Calificación final (escala 0-10):**  
> \( \text{Calificación} = \frac{\text{Puntaje obtenido}}{32} \times 10 \)

---

## 📝 **Niveles de dominio sugeridos**

| Rango | Nivel |
|------|-------|
| 9.0 – 10.0 | **Excelente** – Domina el tema y aplica buenas prácticas. |
| 7.0 – 8.9 | **Bueno** – Cumple con los objetivos, con algunos errores menores. |
| 5.0 – 6.9 | **Satisfactorio** – Aprende, pero necesita apoyo en algunos aspectos. |
| 0.0 – 4.9 | **En desarrollo** – Requiere retroalimentación y refuerzo. |

---

## 🎯 **Conexión con la Secuencia Didáctica**

| Momento | Evaluado en |
|--------|------------|
| **Apertura** | Lista de cotejo: puntos 1–8 (configuración del entorno) |  
| **Desarrollo** | Rúbrica: funcionalidad CRUD, modelo, vistas, URLs |  
| **Cierre** | Rúbrica: interfaz, imágenes, estructura, creatividad, entrega final |

---

## 📎 Recomendaciones para el docente

- Entrega la **lista de cotejo** al inicio del proyecto como guía de trabajo.
- Proporciona la **rúbrica** con anticipación para que los estudiantes conozcan los criterios.
- Usa ambas herramientas para retroalimentación escrita y verbal.
- Fomenta la **autoevaluación** y **coevaluación** entre pares.

---

¿Te gustaría que te genere una **versión imprimible en PDF** de esta lista de cotejo y rúbrica, lista para entregar a los estudiantes?  
Puedo ayudarte a estructurarla como un documento oficial con logo, título y espacio para firma del estudiante y docente.

También puedo crear una **plantilla de Google Forms** para que los estudiantes la autoevalúen. ¿Te interesa?
