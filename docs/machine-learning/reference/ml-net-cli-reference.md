---
title: Referencia de comandos de la CLI de ML.NET
description: Información general, ejemplos y referencia del comando de entrenamiento automático en la herramienta de la CLI de ML.NET.
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 6f07cd8b4237f8931bbc0ec97bc0bbe18c488f16
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856073"
---
# <a name="the-mlnet-cli-command-reference"></a>Referencia de comandos de la CLI de ML.NET

Los comandos `classification`, `regression` y `recommendation` son los comandos principales proporcionados por la herramienta CLI de ML.NET. Estos comandos permiten generar modelos de ML.NET de buena calidad que pueden usarse con fines de clasificación, regresión y recomendación mediante el aprendizaje automático automatizado (AutoML) y el código C# de ejemplo para ejecutar o calificar dicho modelo. Además, se genera código C# para entrenar el modelo y poder investigar el algoritmo y la configuración del modelo.

> [!NOTE]
> Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.

## <a name="overview"></a>Información general

Ejemplo de uso:

```console
mlnet regression --dataset "cars.csv" --label-col price
```

Los comandos de la tarea de ML `mlnet` (`classification`, `regression` y `recommendation`) generan los recursos siguientes:

- Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse.
- Código C# para ejecutar o puntuar el modelo generado.
- Código de C# con el código de entrenamiento utilizado para generar ese modelo.

Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, y mucho más) para realizar predicciones con el modelo.

El tercer recurso, el código de entrenamiento, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar el algoritmo y configuración específicos del modelo.

## <a name="examples"></a>Ejemplos

El comando de la CLI más sencillo para un problema de clasificación (AutoML infiere la mayor parte de la configuración de los datos proporcionados):

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

Otro comando de CLI sencillo para un problema de regresión:

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

Cree y entrene un modelo de clasificación con un conjunto de datos de entrenamiento, un conjunto de datos de prueba y más argumentos explícitos de personalización:

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a>Opciones de comando

Los comandos de la tarea de ML `mlnet` (`classification`, `regression` y `recommendation`) entrenan varios modelos basados en el conjunto de datos proporcionado y en las opciones de la CLI de ML.NET. Estos comandos también seleccionan el mejor modelo, lo guardan como un archivo .zip serializado y generan el código C# correspondiente para la puntuación y el entrenamiento.

### <a name="classification-options"></a>Opciones de clasificación

La ejecución de `mlnet classification` entrenará un modelo de clasificación. Elija este comando si quiere que un modelo de ML clasifique los datos en dos o más clases (por ejemplo, análisis de opiniones).

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a>Opciones de regresión

La ejecución de `mlnet regression` entrenará un modelo de regresión. Elija este comando si quiere que un modelo de ML prediga un valor numérico (por ejemplo, predicción de precio).

```console
mlnet regression

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a>Opciones de recomendación

La ejecución de `mlnet recommendation` entrenará un modelo de recomendación.  Elija este comando si quiere que un modelo de ML recomiende elementos a los usuarios en función de las clasificaciones (por ejemplo, recomendación de productos).

```console
mlnet recommendation

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

Las opciones de entrada no válidas hacen que la herramienta de la CLI emita una lista de entradas válidas y un mensaje de error.

## <a name="dataset"></a>Conjunto de datos

`--dataset | -d` (cadena)

Este argumento proporciona la ruta de acceso del archivo a cualquiera de las siguientes opciones:

- *A: el archivo de conjunto de datos entero:* si utiliza esta opción y el usuario no proporciona `--test-dataset` y `--validation-dataset`, se utilizarán internamente enfoques de validación cruzada (de K iteraciones, etc.) o división de datos automatizada para validar el modelo. En ese caso, el usuario solo deberá proporcionar la ruta de acceso al archivo del conjunto de datos.

- *B: el archivo del conjunto de datos de entrenamiento:* si el usuario también proporciona conjuntos de datos para la validación del modelo (con `--test-dataset` y, opcionalmente, `--validation-dataset`), el argumento `--dataset` significa tener solo el "conjunto de datos de entrenamiento". Por ejemplo, cuando se usa un enfoque de 80-20 % para validar la calidad del modelo y obtener métricas de precisión, el "conjunto de datos de entrenamiento" tendrá un 80 % de los datos y el "conjunto de datos de prueba" tendría un 20 % de los datos.

## <a name="test-dataset"></a>Conjunto de datos de prueba

`--test-dataset | -t` (cadena)

Ruta de acceso al archivo que apunta al archivo del conjunto de datos de prueba, por ejemplo, cuando se usa un enfoque de 80-20 % al realizar validaciones regulares para obtener métricas de precisión.

Si usa `--test-dataset`, también se requiere `--dataset`.

El argumento `--test-dataset` es opcional, a menos que se utilice --validation-dataset. En ese caso, el usuario debe utilizar los tres argumentos.

## <a name="validation-dataset"></a>Conjunto de datos de validación

`--validation-dataset | -v` (cadena)

Ruta de acceso al archivo que apunta al archivo del conjunto de datos de validación. El conjunto de datos de validación es opcional, en cualquier caso.

Si usa un `validation dataset`, el comportamiento debería ser el siguiente:

- Los argumentos `test-dataset` y `--dataset` también son necesarios.

- El conjunto de datos `validation-dataset` se usa para calcular el error de predicción en la selección del modelo.

- El `test-dataset` se usa para la valoración del error de generalización del último modelo elegido. Idealmente, el conjunto de pruebas se debe mantener en un "almacén" y extraerse solo al final del análisis de datos.

Básicamente, cuando se usa un `validation dataset`, además del `test dataset`, la fase de validación se divide en dos partes:

1. En la primera parte, simplemente mira los modelos y selecciona el enfoque con mejor rendimiento mediante los datos de validación (=validación)
2. A continuación, calcula la precisión del enfoque seleccionado (=prueba).

Por lo tanto, la separación de datos podría ser 80/10/10 o 75/15/10. Por ejemplo:

- el archivo `training-dataset` debe tener un 75 % de los datos.
- el archivo `validation-dataset` debe tener un 15 % de los datos.
- el archivo `test-dataset` debe tener un 10 % de los datos.

En cualquier caso, el usuario decidirá los porcentajes mediante la CLI que proporcionará los archivos ya divididos.

## <a name="label-column"></a>Columna de etiqueta

`--label-col` (entero o cadena)

Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se quiere predecir) utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).

Este argumento se usa para problemas de *clasificación* y *regresión*.

## <a name="item-column"></a>Columna de elementos

`--item-col` (entero o cadena)

La columna de elementos contiene la lista de elementos que los usuarios califican (los elementos se recomiendan a los usuarios). Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).

Este argumento solo se usa para la tarea de *recomendación*.

## <a name="rating-column"></a>Columna de clasificación

`--rating-col` (entero o cadena)

La columna de clasificación contiene la lista de clasificaciones que los usuarios otorgan a los elementos. Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).

Este argumento solo se usa para la tarea de *recomendación*.

## <a name="user-column"></a>Columna de usuarios

`--user-col` (entero o cadena)

La columna de usuarios contiene la lista de usuarios que califican elementos. Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).

Este argumento solo se usa para la tarea de *recomendación*.

## <a name="ignore-columns"></a>Omisión de columnas

`--ignore-columns` (cadena)

Con este argumento, puede omitir las columnas existentes en el archivo del conjunto de datos, de modo que los procesos de entrenamiento no las carguen ni utilicen.

Especifique los nombres de las columnas que desea omitir. Use ", " (coma con espacio) o " " (espacio) para separar varios nombres de columna. Puede usar comillas para los nombres de columna que contienen espacios en blanco (por ejemplo, "inicio de sesión").

Ejemplo:

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a>Tiene encabezado

`--has-header` (bool)

Especifique si los archivos del conjunto de datos tienen una fila de encabezado.
Los valores posibles son:

- `true`
- `false`

La CLI de ML.NET intentará detectar esta propiedad si el usuario no especifica este argumento.

## <a name="train-time"></a>Tiempo de entrenamiento

`--train-time` (cadena)

De forma predeterminada, el tiempo máximo de exploración o entrenamiento es de 30 minutos.

Este argumento establece el tiempo máximo (en segundos) para que el proceso explore varios instructores y configuraciones. El tiempo configurado puede superarse so el tiempo proporcionado es demasiado corto (por ejemplo, 2 segundos) para una sola iteración. En este caso, el tiempo real es el tiempo necesario para producir una configuración de modelo en una sola iteración.

El tiempo necesario para las iteraciones puede variar según el tamaño del conjunto de datos.

## <a name="cache"></a>instancias y claves

`--cache` (cadena)

Si usa almacenamiento en caché, el conjunto de datos de entrenamiento completo se cargará en memoria.

Para conjuntos de datos pequeños y medianos, el uso de memoria caché puede mejorar significativamente el rendimiento del entrenamiento, lo que significa que el tiempo de entrenamiento puede ser más corto que cuando no se usa memoria caché.

Sin embargo, para conjuntos de datos grandes, cargar todos los datos en memoria puede tener un impacto negativo ya que podría obtener memoria insuficiente. Cuando se entrene con archivos de conjuntos de datos grandes y no se use la memoria caché, ML.NET transmitirá fragmentos de datos desde la unidad cuando necesite cargar más datos durante el entrenamiento.

Puede especificar los siguientes valores:

`on`: Fuerza el uso de la memoria caché durante el entrenamiento.
`off`: Fuerza el no uso de la memoria caché durante el entrenamiento.
`auto`: Según la heurística de AutoML, se usará o no la memoria caché. Normalmente, los conjuntos de datos pequeños y medianos utilizarán la memoria caché y los conjuntos de datos grandes no la usarán si se usa la opción `auto`.

Si no especifica el parámetro `auto`, la configuración `--cache` de la memoria caché se utilizara de manera predeterminada.

## <a name="name"></a>NOMBRE

`--name` (cadena)

El nombre de la solución o el proyecto de la salida creada. Si no se especifica ningún nombre, se usará el nombre `sample-{mltask}`.

El archivo del modelo de ML.NET (archivo ZIP) obtendrá el mismo nombre también.

## <a name="output-path"></a>Ruta de acceso de salida

`--output | -o` (cadena)

Ubicación o carpeta para colocar la salida generada. El valor predeterminado es el directorio actual.

## <a name="verbosity"></a>Nivel de detalle

`--verbosity | -v` (cadena)

Establece el nivel de detalle de la salida estándar.

Los valores permitidos son:

- `q[uiet]`
- `m[inimal]` (de manera predeterminada)
- `diag[nostic]` (nivel de información de registro)

De forma predeterminada, la herramienta CLI debe mostrar un mínimo de comentarios (`minimal`) cuando trabaja, como mencionar que está trabajando y, a ser posible, cuánto tiempo queda o qué porcentaje de tiempo lleva completado.

## <a name="help"></a>Ayuda

`-h |--help`

Imprime la ayuda para el comando con una descripción para el parámetro de cada comando.

## <a name="see-also"></a>Vea también

- [Cómo instalar la herramienta de la CLI de ML.NET](../how-to-guides/install-ml-net-cli.md)
- [Introducción a la CLI de ML.NET](../automate-training-with-cli.md)
- [Tutorial: Análisis de opiniones mediante la CLI de ML.NET](../tutorials/sentiment-analysis-cli.md)
- [Telemetría en la CLI de ML.NET](../resources/ml-net-cli-telemetry.md)
