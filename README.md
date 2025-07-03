En la industria del marketing y el diseño de productos, entender qué hace que un producto sea exitoso en el mercado es un elemento clave para la toma de decisiones estratégicas. 
En el caso específico del mercado de la perfumeria, existen múltiples factores que influyen en la percepción y aceptación de un perfume, 
como el género al que está dirigido, las notas olfativas, la duración del aroma y al sillage (la estela o rastro de aroma que un perfume deja a su paso). 
Identificar patrones comunes en perfumes bien valorados por los consumidores puede ofrecer ventajas competitivas tanto para marcas 
como para equipos de marketing que buscan lanzar productos con alto potencial de éxito.

Fragrantica es una plataforma dedicada al mundo de la perfumeria, es la comunidad online mas grande de consumidores de perfumes. El objetivo de su creacion fue compartir, discutir, calificar y descubirir perfumes, es decir, los usuarios son los mismos consumidores amantes de este mundo, los cuales son los encargados de puntuar, discutir y opinar sobre las fragancias. 
Esto permite que nuevos compradores o personas interesadas en este mundo tener la oportunidad de tomar decisiones leyendo las reseñas, comentarios de la pagina y de descubrir perfumes similares a sus gustos.

En la industria del marketing y el diseño de productos, entender qué hace que un producto sea exitoso en el mercado es un elemento clave para la toma de decisiones estratégicas. 
En el caso específico del mercado de la perfumeria, existen múltiples factores que influyen en la percepción y aceptación de un perfume, 
como el género al que está dirigido, las notas olfativas, la duración del aroma y al sillage (la estela o rastro de aroma que un perfume deja a su paso). 
Identificar patrones comunes en perfumes bien valorados por los consumidores puede ofrecer ventajas competitivas tanto para marcas 
como para equipos de marketing que buscan lanzar productos con alto potencial de éxito.

Fragrantica es una plataforma dedicada al mundo de la perfumeria, es la comunidad online mas grande de consumidores de perfumes. El objetivo de su creacion fue compartir, discutir, calificar y descubirir perfumes, es decir, los usuarios son los mismos consumidores amantes de este mundo, los cuales son los encargados de puntuar, discutir y opinar sobre las fragancias. 
Esto permite que nuevos compradores o personas interesadas en este mundo tener la oportunidad de tomar decisiones leyendo las reseñas, comentarios de la pagina y de descubrir perfumes similares a sus gustos. 

El dataset utilizado proviene de Kaggle y corresponde a un conjunto de datos obtenidos desde la pagina de Fragrantica que contiene 24063 fragancias unicas.
Se tiene como objetivo construir un modelo predictivo que permita clasificar si un perfume será popular en función de sus notas. 
Desde el punto de vista del marketing, esta información no solo es valiosa para diseñar fragancias atractivas, sino también para segmentar mejor a los consumidores, personalizar recomendaciones y optimizar campañas publicitarias basadas en preferencias reales del público.

El dataset cuenta con las siguientes variables:
 
URL: El enlace a la página de la fragancia.
Perfume: El nombre del perfume.
Brand: Nombres de la marca.
Country: Nombres de los paises de donde provienen.
Gender: Género comercializado de la fragancia (Hombre, mujer, unisex).
Ratin Value: Nota promedio del perfume. 
Rating Count: Cantidad de usuarios que votaron.
Year: El año de lanzamiento.
Top: Notas olfativas.
Middle: Notas medias.
Base: Notas de base.
Perfumer1, Perfumer2: Nombres de los perfumistas.
mainaccord 1-5: Familias olfativas.

Con estos datos se buscara crear una nueva variable, que correspondera a la popularidad real del producto basado en su nota promedio como tambien en la cantidad de personas que participaron,
lo que ayudara a reflejar la percepcion del producto.

Para resolver el problema de clasificación, se emplearan dos modelos de aprendizaje supervisado vistos en clases:

Árbol de Decisión, por su facilidad de interpretación y su utilidad para identificar las reglas lógicas que conducen a la predicción.

Random Forest, por su robustez ante el sobreajuste y su capacidad para mejorar la precisión al combinar múltiples árboles entrenados sobre subconjuntos aleatorios del dataset.

Ademas por los tipos de variables que se presentan, ambos modelos pueden manejar tanto variables numéricas como categóricas, permitiendo
que se logren encontrar relaciones no lineales y patrones complejos entre las fragancias. Además, permiten observar de manera grafica e intuitiba la importancia de cada variable predictora,
es decir permite interpretar fácilmente el camino que lleva a clasificar un perfume como popular lo cual es valioso desde una perspectiva empresarial.