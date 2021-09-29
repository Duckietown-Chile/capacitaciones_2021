# Capacitación 5: Localización

Durante la capacitación 5 se mostraron los conceptos de localizacion que se utilizan en la robótica móvil.

La misión para esta capacitación es localizarse dentro de un area. Para esto, deben utilizar el valor de f encontrado de manera experimental en el desafio anterior (freno de emergencia). 
Tambien se debe usar la libreria `pupil_apriltags`, que se utiliza para identificar los apriltags dentro del mapa.
Con la deteccion del apriltag, deben calcular la distancia del robot hasta el tag para corroborar que se encuentran dentro del area detectada.

Se agrega el archivo `localize.py`, el cual posee la estructura principal y funciones de utilidad con sus respectivos comentarios que servirán para poder completar la misión.

## Pasos previos
Se debe instalar la libreria apriltag, para eso, deben seguir los siguientes pasos:
```bash
conda activate gym-duckietown
pip install pupil-apriltags
```

## Funciones útiles
Estas funciones serán de utilidad para resolver el desafío:


`tags = at_detector.detect(gray_image, estimate_tag_pose=False, camera_params=None, tag_size=None)`: detecta los tags presentes en gray_image y los guarda en una lista de tags.

`tag.corners`: obtiene una matriz con las coordenadas de las cuatro esquinas del tag.

`tag.tag_id`: Obtiene la id correspondiente al tag detectado.

## Mapa para calibración
Además, se adjunta mapa (archivo `4tags.yaml`) que debe copiarse en la carpeta de mapas de `gym-duckietown`. Este mapa contiene 4 tags en cada esquina, el tamaño del cuadro que corresponde al tag es conocido (0.042 [m]), cada _tile_ mide 1 [m] y se pueden mover libremente por todo el espacio.

El código se corre de la siguiente forma:

`python localize.py`
