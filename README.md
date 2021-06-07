# Bienvenidos a la libreria de encuestas de django.
A continuación vamos a explicar la instalación del proyecto:

1. Descarga el codigo con el siguiente comando:
```
git clone https://github.com/cristophca/django_polls.git
```

2. Entramos en la carpeta descargada 'django_polls' y creamos el entorno virtual con el comando:

python3 -m venv .venv

3. Activamos el entorno virtual.
```
source .venv/bin/activate
```


4. Instalamos las librerias necesarias que se encuentran en el fichero 'requirements.txt':
```
pip install -r requirements.txt
```


5. Ejecutamos las migraciones.
```
python manager.py migrate
```


6. Cargamos los datos iniciales
```
python manage.py loaddata fixtures/polls_data.json
```
7. Configurar localhost como ip permitida para django. Editar el fichero 'django_polls/setings.py'. Añadir la ip local a la variable 'ALLOWED_HOSTS' (en la línea 28) de forma que quede así:

```
ALLOWED_HOST = ['192.168.33.10', '127.0.0.1']
```


8. Arrancamos el servidor.

## Cómo instalar el proyecto en un amáquina remota con Fabric.

1. Instalar la libreria de fabric
``
pip install fabric
``
2. Comprueba la ip del servidor remoto y las credenciales en las línea 11-15 del script fabfile.py
``
@task
def development(ctx):
    ctx.user = 'vagrant'
    ctx.host = '192.168.33.10'
    ctx.connect_kwargs = {"password": "vagrant"}
``
3. Ejecuta el script con el siguiente comando:
``
fab development deploy

``
