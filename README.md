# Olor a Éxito: Clasificación de Fragancias Populares con Aprendizaje Automático.
Integrantes: Brandon Ramirez y Cristóbal Soto.



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

Data set utilizado : https://www.kaggle.com/datasets/olgagmiufana1/fragrantica-com-fragrance-dataset
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

La metodología que se utilizo para abordar este problema fue Clasificación Random Forest dado que nuestro estudio es predecir el puntaje que se le dará a un perfume en un futuro tomado en cuenta las familias olfativas que este posee.
Otro beneficio que nos significó utilizar random forest es que, a diferencia de usar un solo árbol de decisión, Random Forest promedia múltiples árboles, lo que genera que también se reduzca la varianza y el overfiting.
Las variables que elegimos para entrenar nuestro modelo fueron; Rating Value (que fue modificada a Rating), “Top”, “Middle y “Base” siendo estas 3 las notas que poseen los perfumes, “Familia” sobre la familia olfativa , “Gender” que representa el genero y “Brand” que es la marca.
La familia olfativa es una variable categórica por lo que se debió aplicar feature engieneering para transformar las variables de los puntajes y las notas para que así sea variables categóricas. Pasamos los puntajes de 1 a 5 a 3 secciones “Pesima”, “No recomendable”, “Recomendable”. Tambien transformamos las variables “Top”, “Middle” y “Base” siendo estas las notas principales del perfume a matrices con One-Hot Encoding. La variable “Gender” se toma valores [0,1,2] 0 femenino, 1 masculino y 2 unisex. Y por ultimo la Variable “Brand” se le dieron valores numéricos enteros.

Procedimiento.
Primeramente, nos encargamos de cargar el dataset y analizar; columnas, cantidad de filas y variables, tipos de variables. Luego al darnos cuenta de que poseía datos nulos procedimos a eliminarlos.
Utilizamos un histograma para analizar la distribución de los datos de la variable “Rating value” y otro para analizar la distribución de la cantidad de votos.

No precisamos de reducción de dimensionalidad debido a que consideramos que la cantidad de filas era necesaria para el desarrollo de nuestro modelo. El data set original contaba con 24.063 filas y luego de limpiar la base de datos nulos nos quedó de 23.082 filas. Para finalmente eliminar los perfumes que tenían menos de 100 votos y quedarnos con 13.230 filas.
Al momento del entrenamiento requerimos de las librerías; “pandas”, “numpy”, “matplotlib.pyplot”, “seaborn”, “sklearn”.

El modelo desarrollado para predecir el rating de perfumes enfrenta desafíos debido a la naturaleza del problema y las características del dataset. El rating, muestra poca variabilidad y está altamente concentrada en valores cercanos (entre 3.9 y 4.1), lo que dificulta que el modelo distinga claramente entre diferentes categorías. Además, las notas y familias  representan una gran cantidad de características dispersas, aumentando la dimensionalidad y el ruido, lo que afecta la capacidad predictiva. Los resultados obtenidos, con el accuracy bajo indicaa que la información disponible no es suficiente para predecir las opiniones de los usuarios. 
Esto como tal no significa que el modelo sea inútil, sino que refleja que el rating está influenciado por múltiples factores externos no presentes en los datos, como marketing, preferencias personales o tendencias sociales. 
Por tanto, el modelo es más adecuado para la exploración y generación de hipótesis sobre qué notas o familias olfativas se asocian a mejores valoraciones, en lugar de realizar predicciones precisas para toma de decisiones. 
Para mejorar el rendimiento sería ideal contar con datos adicionales. En conclusión, el proyecto aporta valor al entender las posibles relaciones entre características químicas y opiniones, pero las limitaciones del dataset y la complejidad del gusto humano limitan la exactitud predictiva del modelo.