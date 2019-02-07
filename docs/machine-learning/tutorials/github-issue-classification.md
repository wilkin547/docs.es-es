---
title: Uso de ML.NET en un escenario de clasificación de problemas multiclase de GitHub
description: Descubra cómo usar ML.NET en un escenario de clasificación multiclase para clasificar los problemas de GitHub y asignarlos a un área determinada.
ms.date: 01/24/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a951e884a7494b0dcc808fc3dafbfadebc5577dc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254995"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a>Tutorial: Uso de ML.NET en un escenario de clasificación multiclase para clasificar problemas de GitHub.

En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de problemas de GitHub a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
> * Preparar los datos
> * Crear la canalización de aprendizaje
> * Cargar un clasificador
> * Entrenar el modelo
> * Evaluar el modelo con otro conjunto de datos
> * Predecir una única instancia del resultado de datos de prueba con el modelo
> * Predecir los resultados de datos de prueba con un modelo cargado

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

## <a name="github-issue-sample-overview"></a>Información general sobre el ejemplo de problema de GitHub

El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice el área de etiqueta de un problema de GitHub. También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad. Los conjuntos de datos del problema proceden del repositorio de GitHub dotnet/corefx.

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* [Archivo de problemas de GitHub delimitado por pestañas (issues_train.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* [Prueba de problemas de GitHub delimitado por pestañas (issues_test.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

## <a name="machine-learning-workflow"></a>Flujo de trabajo del aprendizaje automático

En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.

Las fases del flujo de trabajo son las siguientes:

1. **Entender el problema**
2. **Preparar los datos**
   * **Cargar los datos**
   * **Extraer características (transformar los datos)**
3. **Compilar y entrenar** 
   * **Entrenar el modelo**
   * **Evaluar el modelo**
4. **Run**
   * **Consumo del modelo**

### <a name="understand-the-problem"></a>Entender el problema

Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema. Desglosar el problema en partes le permite predecir y evaluar los resultados.

El problema de este tutorial es comprender a qué área pertenecen los problemas de GitHub entrantes, de modo que se puedan etiquetar correctamente para priorizarlos y programarlos.

Puede desglosar el problema del siguiente modo:

* texto del título del problema
* texto de la descripción del problema
* valor de área para los datos de entrenamiento del modelo
* valor de predicción del área que se puede evaluar y usar de forma operativa

Después, deberá **determinar** el área, lo que lo ayudará con la selección de tareas de aprendizaje automático.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Con este problema, tiene constancia de los siguientes hechos:

Datos de entrenamiento:

Los problemas de GitHub se pueden etiquetar en varias áreas (**Área**), tal como se muestra en los siguientes ejemplos:

* area-System.Numerics
* area-System.Xml
* area-Infrastructure
* area-System.Linq
* area-System.IO

Prediga el **área** de un nuevo problema de GitHub, como en los siguientes ejemplos:

* Contract.Assert en comparación con Debug.Assert
* Establecimiento de los campos como de solo lectura en System.Xml

La tarea de aprendizaje automático de clasificación es ideal para este escenario.

### <a name="about-the-classification-task"></a>Acerca de la tarea de clasificación

La clasificación es una tarea de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos. Por ejemplo, puede utilizar la clasificación para:

* Identificar un sentimiento como positivo o negativo.
* Clasificar correo electrónico como correo no deseado o correo válido.
* Determinar si la muestra de laboratorio de un paciente es cancerosa.
* Categorizar a los clientes por su propensión a responder a una campaña de ventas.

Las tareas de clasificación son a menudo de uno de los siguientes tipos:

* Binario: A o B.
* Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.

Para este tipo de problema, use una tarea de clasificación multiclase, ya que su predicción de categoría de problema puede ser una de varias categorías (multiclase) en lugar de solo dos (binario).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

### <a name="create-a-project"></a>Crear un proyecto

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue los conjuntos de datos [issues_train.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) y guárdelos en la carpeta *Datos* que ha creado anteriormente. El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

Debe crear tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y una variable global para `TextLoader`:

* `_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.
* `_mlContext` es el elemento <xref:Microsoft.ML.MLContext> que proporciona el contexto de procesamiento.
* `_trainingDataView` es el elemento <xref:Microsoft.ML.Data.IDataView> que se usa para procesar el conjunto de datos de entrenamiento.
* `_predEngine` es el elemento <xref:Microsoft.ML.PredictionEngine%602> que se usa para las predicciones únicas.
* `_reader` es el <xref:Microsoft.ML.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *GitHubIssueData.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *GitHubIssueData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `GitHubIssue` y `IssuePrediction`, al archivo *GitHubIssueData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` es la clase de conjunto de datos de entrada y contiene los siguientes campos de <xref:System.String>:

* `ID` contiene un valor para el id. del problema de GitHub
* `Area` contiene un valor para la etiqueta `Area`
* `Title` contiene el título del problema de GitHub
* `Description` contiene la descripción del problema de GitHub

`IssuePrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene un solo elemento `string` (`Area`) y un atributo `PredictedLabel` `ColumnName`. `Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo. `PredictedLabel` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

Cuando se crea un modelo con ML.NET, empieza creando un elemento <xref:Microsoft.ML.MLContext>. Esto es comparable conceptualmente a usar `DbContext` en Entity Framework. El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Inicialice la variante global `_mlContext` con una nueva instancia de `MLContext` usando una inicialización aleatoria (`seed: 0`) para obtener resultados repetibles o deterministas en varios entrenamientos.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Carga de los datos

A continuación, inicialice la variable global `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> y cargue los datos con el parámetro `_trainDataPath`.

 Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.

En ML.NET, los datos son similares a `SQL view`. Se evalúan lentamente, se esquematizan y son heterogéneos. El objeto es la primera parte de la canalización y carga los datos. Para este tutorial, carga un conjunto de datos con los títulos y descripciones de los problemas, así como la etiqueta de GitHub del área correspondiente. El elemento `DataView` se usa para crear y entrenar el modelo.

Puesto que el tipo de modelo de datos `GitHubIssue` que ha creado anteriormente coincide con el esquema del conjunto de datos, puede combinar la inicialización, la asignación y la carga del conjunto de datos en una línea de código.

La primera parte de la línea (`CreateTextReader<GitHubIssue>(hasHeader: true)`) crea un elemento <xref:Microsoft.ML.Data.TextLoader> mediante la inferencia del esquema del conjunto de datos del tipo de modelo de datos `GitHubIssue` y el uso del encabezado del conjunto de datos.

Ha definido el esquema de datos anteriormente al crear la clase `GitHubIssue`. Para su esquema:

* `ID`, la primera columna (id. de problema de GitHub).
* `Area`, la segunda columna (la predicción para el entrenamiento).
* `Title`, la tercera columna (título del problema de GitHub), es la primera [característica](../resources/glossary.md##feature) usada para predecir el `Area`.
* `Description`, la cuarta columna, es la segunda característica usada para predecir el `Area`.

La segunda parte de la línea (`.Read(_trainDataPath)`) usa el método <xref:Microsoft.ML.Data.TextLoader.Read%2A> para cargar el archivo de texto del entrenamiento usando `_trainDataPath` en la variable global `IDataView` (`_trainingDataView`).  

Para inicializar y cargar la variable global `_trainingDataView` con el fin de volver a usarla para la canalización, agregue el siguiente código después de la inicialización de `mlContext`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


Agregue lo siguiente como la siguiente línea de código en el método `Main`:

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

El método `ProcessData` ejecuta las tareas siguientes:

* Extrae y transforma los datos.
* Devuelve la canalización de procesamiento.

Cree el método `ProcessData`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-and-transform-the-data"></a>Extraer y transformar los datos

El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático. Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores. El uso de datos sin estas tareas de modelado puede producir resultados engañosos.

Las canalizaciones de transformación de ML.NET crean un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba. El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos. Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML. Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).

En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `GitHubIssue`.

Si el modelo se ha entrenado y evaluado, de forma predeterminada, los valores de la columna **Label** se consideran valores correctos para predecir. Para predecir la etiqueta de área de GitHub para `GitHubIssue`, debe copiar la columna `Area` en la columna **Etiqueta**. Para ello, use `MLContext.Transforms.Conversion.MapValueToKey`, que es un contenedor para la clase de transformación <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.  `MapValueToKey` devuelve un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> que será efectivamente una canalización. Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`. Agregue esto como la siguiente línea de código:

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

El algoritmo que entrena el modelo requiere características **numéricas**. Por ejemplo, Siguiente llama a `mlContext.Transforms.Text.FeaturizeText`, que caracteriza las columnas de texto (`Title` y `Description`) en un vector numérico para cada columna con los nombres `TitleFeaturized` y `DescriptionFeaturized`. Con la caracterización, se asignan diferentes valores clave numéricos a distintos valores de cada una de las columnas. El algoritmo de aprendizaje automático aprovecha este proceso.
Anexe la caracterización para ambas columnas a la canalización usando el siguiente código:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `Concatenate`. De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**. Anexe esta transformación a la canalización usando el siguiente código:

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 A continuación, anexe <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> para almacenar en caché el objeto DataView, de modo que pueda obtener un mayor rendimiento al iterar los datos varias veces usando la caché, tal como se muestra en el siguiente código:

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

Devuelva la canalización al final del método `ProcessData`.

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

En este paso se controla el preprocesamiento y la caracterización. El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.

## <a name="build-and-train-the-model"></a>Creación y entrenamiento del modelo

Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

El método `BuildAndTrainModel` ejecuta las tareas siguientes:

* Crea la clase de algoritmo de entrenamiento.
* Entrena el modelo.
* Predice el área según los datos de entrenamiento.
* Guarda el modelo en un archivo `.zip`.
* Devuelve el modelo.

Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static void BuildAndTrainModel()
{

}
```

Tenga en cuenta que se pasan dos parámetros al método BuildAndTrainModel; un elemento `IDataView` para el conjunto de datos de entrenamiento (`trainingDataView`) y un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> para la canalización de procesamiento creada en ProcessData (`pipeline`).

 Agregue el código siguiente a la primera línea del método `BuildAndTrainModel`:

### <a name="choose-a-trainer-algorithm"></a>Elección de un algoritmo de entrenamiento

Para agregar el algoritmo de entrenamiento, llame al método contenedor `mlContext.Transforms.Text.FeaturizeText`, que devuelve un objeto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>. Esto es un aprendiz de árbol de decisión que usará en esta canalización. `SdcaMultiClassTrainer` se anexa a `pipeline` y acepta los elementos `Title` y `Description` (`Features`) caracterizados y los parámetros de entrada de `Label` para aprender de los datos históricos.

Agregue el código siguiente al método `BuildAndTrainModel`:

[!code-csharp[SdcaMultiClassTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SdcaMultiClassTrainer)]

Ahora que ha creado un algoritmo de entrenamiento, anéxelo a `pipeline`. También deberá asignar la etiqueta al valor para devolverlo a su estado de lectura original. Realice una de estas acciones con el siguiente código:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a>Entrenar el modelo

Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado. Una vez que se ha definido el estimador, entrenará el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados. Esto devuelve un modelo que se usa para las predicciones. `trainingPipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa. El experimento no se ejecuta hasta que esto suceda.

Agregue el código siguiente al método `BuildAndTrainModel`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales. <xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`. Vamos a agregar el código siguiente para crear `PredictionEngine` como la línea siguiente en el método `BuildAndTrainModel`:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

Puede usarlo para predecir la etiqueta `Area` de una instancia única de los datos del problema. Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="model-operationalization-prediction"></a>Puesta en marcha del modelo: predicción

Muestre `GitHubIssue` y la predicción de la etiqueta `Area` correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Guardado y devolución del modelo entrenado para su uso para la evaluación

En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Para guardar el modelo entrenado en un archivo .zip, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `BuildAndTrainModel`:

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

Devuelva el modelo al final del método `BuildAndTrainModel`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="save-the-model-as-azip-file"></a>Almacenamiento del modelo como un archivo .zip

Cree el método `SaveModelAsFile`, justo después del método `BuildAndTrainModel`, mediante el código siguiente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

El método `SaveModelAsFile` ejecuta las tareas siguientes:

* Guarda el modelo como un archivo .zip.

A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones. `ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>. Para guardar esto como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`. Agregue el siguiente código al método `SaveModelAsFile` como la siguiente línea:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>Evaluar el modelo

Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación. En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado. Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:

```csharp
public static void Evaluate()
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador multiclase.
* Evalúa el modelo y crea métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `BuildAndTrainModel`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

Como hizo anteriormente con el conjunto de datos de entrenamiento, puede combinar la inicialización, la asignación y la carga del conjunto de datos de prueba en una línea de código. Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad. Agregue el código siguiente al método `Evaluate`:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

`MulticlassClassificationContext.Evaluate` es un contenedor para el método <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> que calcula las métricas de calidad del modelo que usa el conjunto de datos especificado. Devuelve un objeto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación multiclase.
Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.
Tenga en cuenta el uso del método `Transform` de la variable global de aprendizaje automático `_trainedModel` (un transformador) para especificar características y devolver predicciones. Agregue el código siguiente al método `Evaluate` como la siguiente línea:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

Las siguientes métricas se evalúan para la clasificación multiclase:

* Microprecisión: todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión.  Le recomendamos que la microprecisión esté lo más cerca posible de 1.

* Macroprecisión: todas las clases contribuyen del mismo modo a la métrica de precisión. Las clases minoritarias tienen el mismo peso que las clases más grandes. Le recomendamos que la macroprecisión esté lo más cerca posible de 1.

* Pérdida de registro: vea [Pérdida de registro](../resources/glossary.md#log-loss). Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.

* Reducción de la pérdida de registro: parte de [-inf, 100], donde 100 equivale a una predicción perfecta, y 0 indica una predicción aproximada. Le recomendamos que la reducción de la pérdida de registro esté lo más cerca posible de 0.

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Predicción de los resultados de datos de prueba con el modelo guardado

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

Cree el método `PredictIssue`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void PredictIssue()
{

}
```

El método `PredictIssue` ejecuta las tareas siguientes:

* Crea un único problema de datos de prueba.
* Predice el área según los datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

En primer lugar, cargue el modelo que ha guardado anteriormente con el siguiente código:

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
Ahora que tiene un modelo, puede usarlo para predecir la etiqueta Área de GitHub de una única instancia de los datos del problema de GitHub. Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales. Agregue el código siguiente al método `PredictIssue` para las predicciones:

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

### <a name="model-operationalization-prediction"></a>Puesta en marcha del modelo: predicción

Muestre `Area` para poder categorizar el problema y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. A medida que la canalización procesa, muestra mensajes. Puede ver las advertencias o mensajes de procesamiento. Se han quitado de los siguientes resultados para mayor claridad.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir una etiqueta Área de un problema de GitHub. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
> * Preparar los datos
> * Crear la canalización de aprendizaje
> * Cargar un clasificador
> * Entrenar el modelo
> * Evaluar el modelo con otro conjunto de datos
> * Predecir los resultados de datos de prueba con el modelo

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Predictor de tarifa de taxi](taxi-fare.md)
