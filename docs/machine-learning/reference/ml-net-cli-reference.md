---
title: El comando de entrenamiento automático en la herramienta de la CLI de ML.NET
description: Información general, ejemplos y referencia del comando de entrenamiento automático en la herramienta de la CLI de ML.NET.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 28eb56eb018e3d1cc76f300ee78c298af77c9b91
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557935"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a>El comando de entrenamiento automático en la herramienta de la CLI de ML.NET

> [!NOTE]
> Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.

El comando `auto-train` es el comando principal proporcionado por la herramienta de la CLI de ML.NET. El comando permite generar un modelo de ML.NET de buena calidad (archivo .zip del modelo serializado) además del código de C# de ejemplo para ejecutar o calificar dicho modelo. Además, el código de C# para crear o entrenar dicho modelo también se genera automáticamente para que pueda investigar qué algoritmo y configuración usa para ese "mejor modelo" generado.

Puede generar dichos recursos desde sus propios conjuntos de datos sin necesidad de codificarlos usted, lo cual mejora también su productividad incluso si ya conoce ML.NET.

Actualmente, las tareas de Machine Learning compatibles con la CLI de ML.NET son:

- `binary-classification`
- `multiclass-classification`
- `regression`

- Futuro: Otras tareas de aprendizaje automático, como:
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

Ejemplo de uso en el símbolo del sistema:

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

El comando `mlnet auto-train` genera los siguientes recursos:

- Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse.
- El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).
- El código de C# con el código de entrenamiento utilizado para generar ese modelo (con fines de aprendizaje).

Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.

El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI y el motor de AutoML de ML.NET.

## <a name="the-auto-train-command-uses-the-automl-engine"></a>El comando de entrenamiento automático utiliza el motor de AutoML

La CLI utiliza el motor de AutoML de ML.NET (paquete NuGet) para buscar de forma inteligente los modelos de mejor calidad, tal como se muestra en el diagrama siguiente:

![imagen](./media/ml-net-automl-working-diagram.png "motor de AutoML trabajando dentro de la CLI de ML.NET")

Al ejecutar la herramienta de CLI de ML.NET con el comando de entrenamiento automático, verá que la herramienta intenta varias iteraciones con diferentes algoritmos y combinaciones de configuración.

## <a name="reference-for-auto-train-command"></a>Referencia para el comando de entrenamiento automático

## <a name="examples"></a>Ejemplos

El comando de CLI más sencillo para un problema de clasificación binaria (AutoML deberá inferir la mayor parte de la configuración de los datos proporcionados):

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

Otro comando de CLI sencillo para un problema de regresión:

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

Cree y entrene un modelo de clasificación binaria con un conjunto de datos de entrenamiento, un conjunto de datos de prueba y más argumentos explícitos de personalización:

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a>nombre

`mlnet auto-train`: entrena varios modelos ("n" iteraciones) según el conjunto de datos proporcionado y, por último, selecciona el mejor modelo, lo guarda como archivo ZIP serializado y genera código C# relacionado para el entrenamiento y la puntuación.

## <a name="synopsis"></a>Sinopsis

```console
> mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

Las opciones de entrada no válidas deben hacer que la herramienta de la CLI emita una lista de entradas válidas y un mensaje de error que explique qué argumento está ausente, si ese es el caso.

## <a name="options"></a>Opciones

 ----------------------------------------------------------

`--task | --mltask | -T` (cadena)

Una sola cadena que proporciona el problema de ML que debe resolverse. Por ejemplo, cualquiera de las siguientes tareas (la CLI finalmente será compatible con todas las tareas que se admiten en AutoML):

- `regression`: elija si se usará el modelo de ML para predecir un valor numérico
- `binary-classification`: elija si el resultado del modelo de ML tiene dos posibles valores booleanos categóricos (0 o 1).
- `multiclass-classification`: elija si el resultado del modelo de ML tiene varios valores posibles categóricos.

En las versiones futuras, se admitirán otros escenarios y tareas de ML, como `recommendations`, `clustering` y `ranking`.

 Solo debe proporcionarse una sola tarea de ML en este argumento.

 ----------------------------------------------------------

`--dataset | -d` (cadena)

Este argumento proporciona la ruta de acceso del archivo a cualquiera de las siguientes opciones:

- *A: el archivo de conjunto de datos entero:* si utiliza esta opción y el usuario no proporciona `--test-dataset` y `--validation-dataset`, se utilizarán internamente enfoques de validación cruzada (de K iteraciones, etc.) o división de datos automatizada para validar el modelo. En ese caso, el usuario solo deberá proporcionar la ruta de acceso al archivo del conjunto de datos.

- *B: el archivo del conjunto de datos de entrenamiento:* si el usuario también proporciona conjuntos de datos para la validación del modelo (con `--test-dataset` y, opcionalmente, `--validation-dataset`), el argumento `--dataset` significa tener solo el "conjunto de datos de entrenamiento". Por ejemplo, cuando se usa un enfoque de 80-20 % para validar la calidad del modelo y obtener métricas de precisión, el "conjunto de datos de entrenamiento" tendrá un 80 % de los datos y el "conjunto de datos de prueba" tendría un 20 % de los datos.

----------------------------------------------------------

`--test-dataset | -t` (cadena)

Ruta de acceso al archivo que apunta al archivo del conjunto de datos de prueba, por ejemplo, cuando se usa un enfoque de 80-20 % al realizar validaciones regulares para obtener métricas de precisión.

Si usa `--test-dataset`, también se requiere `--dataset`.

El argumento `--test-dataset` es opcional, a menos que se utilice --validation-dataset. En ese caso, el usuario debe utilizar los tres argumentos.

----------------------------------------------------------

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

----------------------------------------------------------

`--label-column-name | -n` (cadena)

Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se desea predecir) utilizando el nombre de la columna establecido en el encabezado del conjunto de datos.

Este argumento se utiliza solo para tareas de ML supervisadas, como un *problema de clasificación*. No se puede usar para tareas de ML no supervisadas, como *clústeres*.

----------------------------------------------------------

`--label-column-index | -i` (int)

Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se desea predecir) utilizando el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 1).

*Nota:* Si el usuario también usa el `--label-column-name`, el `--label-column-name` es el que se va a usar.

Este argumento se utiliza solo para una tarea de ML supervisada, como un *problema de clasificación*. No se puede usar para tareas de ML no supervisadas, como *clústeres*.

----------------------------------------------------------

`--ignore-columns | -I` (cadena)

Con este argumento, puede omitir las columnas existentes en el archivo del conjunto de datos, de modo que los procesos de entrenamiento no las carguen ni utilicen.

Especifique los nombres de las columnas que desea omitir. Use ", " (coma con espacio) o " " (espacio) para separar varios nombres de columna. Puede usar comillas para los nombres de columna que contienen espacios en blanco (por ejemplo, "inicio de sesión").

Ejemplo:

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

`--has-header | -h` (bool)

Especifique si los archivos del conjunto de datos tienen una fila de encabezado.
Los valores posibles son:
- `true`
- `false`

El valor predeterminado es `true` si el usuario no especifica este argumento.

Para poder usar el argumento `--label-column-name`, debe tener un encabezado en el archivo del conjunto de datos y `--has-header` establecido en `true` (el cual es el valor predeterminado).

----------------------------------------------------------

`--max-exploration-time | -x` (cadena)

De forma predeterminada, el tiempo máximo de exploración es de 10 segundos.

Este argumento establece el tiempo máximo (en segundos) para que el proceso explore varios instructores y configuraciones. El tiempo configurado puede superarse so el tiempo proporcionado es demasiado corto (por ejemplo, 2 segundos) para una sola iteración. En este caso, el tiempo real es el tiempo necesario para producir una configuración de modelo en una sola iteración.

El tiempo necesario para las iteraciones puede variar según el tamaño del conjunto de datos.

----------------------------------------------------------

`--cache | -c` (cadena)

Si usa almacenamiento en caché, el conjunto de datos de entrenamiento completo se cargará en memoria.

Para conjuntos de datos pequeños y medianos, el uso de memoria caché puede mejorar significativamente el rendimiento del entrenamiento, lo que significa que el tiempo de entrenamiento puede ser más corto que cuando no se usa memoria caché.

Sin embargo, para conjuntos de datos grandes, cargar todos los datos en memoria puede tener un impacto negativo ya que podría obtener memoria insuficiente. Cuando se entrene con archivos de conjuntos de datos grandes y no se use la memoria caché, ML.NET transmitirá fragmentos de datos desde la unidad cuando necesite cargar más datos durante el entrenamiento.

Puede especificar los siguientes valores:

`on`: Fuerza el uso de la memoria caché durante el entrenamiento.
`off`: Fuerza el no uso de la memoria caché durante el entrenamiento.
`auto`: Según la heurística de AutoML, se usará o no la memoria caché. Normalmente, los conjuntos de datos pequeños y medianos utilizarán la memoria caché y los conjuntos de datos grandes no la usarán si se usa la opción `auto`.

Si no especifica el parámetro `auto`, la configuración `--cache` de la memoria caché se utilizara de manera predeterminada.

----------------------------------------------------------

`--name | -N` (cadena)

El nombre de la solución o el proyecto de la salida creada. Si no se especifica ningún nombre, se usará el nombre `sample-{mltask}`.

El archivo del modelo de ML.NET (archivo ZIP) obtendrá el mismo nombre también.

----------------------------------------------------------

`--output-path | -o` (cadena)

Ubicación o carpeta para colocar la salida generada. El valor predeterminado es el directorio actual.

----------------------------------------------------------

`--verbosity | -V` (cadena)

Establece el nivel de detalle de la salida estándar.

Los valores permitidos son:

- `q[uiet]`
- `m[inimal]` (de manera predeterminada)
- `diag[nostic]` (nivel de información de registro)

De forma predeterminada, la herramienta de la CLI debe mostrar un mínimo de comentarios cuando trabaja, como mencionar que está trabajando y, de ser posible, cuánto tiempo queda o qué porcentaje de tiempo lleva completado.

----------------------------------------------------------

`-h|--help`

Imprime la ayuda para el comando con una descripción para el parámetro de cada comando.

----------------------------------------------------------

## <a name="see-also"></a>Vea también

- [Cómo instalar la herramienta de la CLI de ML.NET](../how-to-guides/install-ml-net-cli.md)
- [Automatizar el entrenamiento del modelo con la CLI de ML.NET](../automate-training-with-cli.md)
- [Tutorial: Generación automática de un clasificador binario mediante la CLI de ML.NET](../tutorials/mlnet-cli.md)
- [Telemetría en la CLI de ML.NET](../resources/ml-net-cli-telemetry.md)
