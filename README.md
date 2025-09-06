# Message Board - Django Task Manager

Este proyecto es una aplicación web desarrollada con Django para la gestión y visualización de tareas.

## Características principales

- Listado de tareas con título, fecha de creación y última actualización.
- Estructura basada en Django 5.2.6.
- Uso de vistas genéricas para mostrar las tareas.
- Base de datos SQLite3 por defecto.

## Estructura del proyecto

```
message_board/
├── db.sqlite3                # Base de datos SQLite
├── manage.py                 # Script de gestión de Django
├── requirements.txt          # Dependencias del proyecto
├── django_base/              # Configuración principal de Django
│   ├── settings.py           # Configuración del proyecto
│   ├── urls.py               # Rutas principales
│   └── ...
├── tasks/                    # Aplicación de tareas
│   ├── models.py             # Modelo Task
│   ├── views.py              # Vista de listado de tareas
│   ├── urls.py               # Rutas de la app
│   └── migrations/           # Migraciones de la base de datos
└── templates/
	 └── tasks_list.html       # Plantilla para mostrar tareas
```

## Instalación y ejecución

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
	Abre tu navegador y visita [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

## Modelo de datos

El modelo principal es `Task`:

```python
class Task(models.Model):
	 title = models.CharField(max_length=200)
	 created_at = models.DateTimeField(auto_now_add=True)
	 updated_at = models.DateTimeField(auto_now=True)
```

## Vistas y URLs

- La vista principal es `TaskListView`, que muestra todas las tareas en la plantilla `tasks_list.html`.
- La URL raíz (`/`) muestra el listado de tareas.

## Personalización

Puedes modificar el modelo `Task` en `tasks/models.py` para agregar más campos o funcionalidades.

## Administración

Accede a `/admin` para gestionar tareas desde el panel de administración de Django. Para crear un superusuario:

```powershell
python manage.py createsuperuser
```

## Dependencias principales

- Django==5.2.6
- asgiref==3.9.1
- sqlparse==0.5.3
- tzdata==2025.2

## Licencia

Este proyecto se distribuye bajo la licencia MIT.
