
# Message Board - Gestor de Tareas en Django

Aplicación web desarrollada con Django para gestionar y visualizar tareas. Permite listar tareas, ver fechas de creación y actualización, y administrar desde el panel de Django.

---

## Tabla de Contenidos
1. [Características](#características)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Instalación y Ejecución](#instalación-y-ejecución)
4. [Modelo de Datos](#modelo-de-datos)
5. [Vistas y URLs](#vistas-y-urls)
6. [Personalización](#personalización)
7. [Administración](#administración)
8. [Dependencias](#dependencias)
9. [Licencia](#licencia)

---

## Características
- Listado de tareas con título, fecha de creación y última actualización.
- Uso de vistas genéricas (`ListView`).
- Base de datos SQLite3 por defecto.
- Panel de administración de Django.

## Estructura del Proyecto
```
message_board/
├── db.sqlite3                # Base de datos SQLite
├── manage.py                 # Script de gestión de Django
├── requirements.txt          # Dependencias
├── django_base/              # Configuración principal
│   ├── settings.py           # Configuración
│   ├── urls.py               # Rutas principales
│   └── ...
├── tasks/                    # App de tareas
│   ├── models.py             # Modelo Task
│   ├── views.py              # Vista de listado
│   ├── urls.py               # Rutas de la app
│   └── migrations/           # Migraciones
└── templates/
	 └── tasks_list.html       # Plantilla de tareas
```

## Instalación y Ejecución
1. **Clona el repositorio:**
	```powershell
	git clone <URL-del-repositorio>
	cd message_board
	```
2. **Instala las dependencias:**
	```powershell
	pip install -r requirements.txt
	```
3. **Aplica migraciones:**
	```powershell
	python manage.py migrate
	```
4. **Ejecuta el servidor de desarrollo:**
	```powershell
	python manage.py runserver
	```
5. **Accede a la aplicación:**
	[http://127.0.0.1:8000/](http://127.0.0.1:8000/)

## Modelo de Datos
Modelo principal: `Task`
```python
class Task(models.Model):
	 title = models.CharField(max_length=200)
	 created_at = models.DateTimeField(auto_now_add=True)
	 updated_at = models.DateTimeField(auto_now=True)
```

## Vistas y URLs
- Vista principal: `TaskListView` (tasks/views.py)
- Plantilla: `tasks_list.html` (templates/)
- URL raíz (`/`): muestra el listado de tareas

## Personalización
Puedes modificar el modelo `Task` en `tasks/models.py` para agregar más campos o funcionalidades según tus necesidades.

## Administración
Accede a `/admin` para gestionar tareas desde el panel de administración de Django.
Para crear un superusuario:
```powershell
python manage.py createsuperuser
```

## Dependencias
- Django==5.2.6
- asgiref==3.9.1
- sqlparse==0.5.3
- tzdata==2025.2

## Licencia
MIT
