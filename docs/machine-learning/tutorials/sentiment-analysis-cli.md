---
title: Análisis de opiniones mediante la CLI de ML.NET
description: Generar automáticamente un modelo de ML y el código de C# relacionado desde un conjunto de datos de ejemplo
author: cesardl
ms.author: cesardl
ms.date: 12/23/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: caf12296b208b3d2e57c3a74300cced225e4db66
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738758"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a>Análisis de opiniones mediante la CLI de ML.NET

Aprenda a usar la CLI de ML.NET para generar automáticamente un modelo de ML.NET y el código de C# subyacente. Usted proporciona el conjunto de datos y la tarea de aprendizaje automático que desea implementar, y la CLI utiliza el motor de AutoML para crear el código fuente de implementación y generación de modelos, así como el modelo binario.

En este tutorial, llevará a cabo los pasos siguientes:
> [!div class="checklist"]
>
> - Preparar los datos para la tarea de aprendizaje automático seleccionada
> - Ejecutar el comando "mlnet auto-train" desde la CLI
> - Revisar los resultados de métrica de calidad
> - Comprender el código de C# generado para usar el modelo en la aplicación
> - Explorar el código de C# generado que se usó para entrenar el modelo

> [!NOTE]
> Este tema hace referencia a la herramienta de la CLI de ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

La CLI de ML.NET forma parte de ML.NET y su objetivo principal es "democratizar" ML.NET para desarrolladores de .NET durante el aprendizaje de ML.NET, por lo que no es necesario codificar desde cero para empezar a trabajar.

Puede ejecutar la CLI de ML.NET en cualquier símbolo del sistema (Windows, Mac o Linux) para generar modelos de ML.NET de buena calidad y el código fuente basado en los conjuntos de datos de entrenamiento que proporcione.

## <a name="pre-requisites"></a>Requisitos previos

- [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) o versiones posteriores
- (Opcional) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)
- [CLI de ML.NET](../how-to-guides/install-ml-net-cli.md)

Puede ejecutar los proyectos del código de C# generado desde Visual Studio o con `dotnet run` (CLI de .NET Core).

## <a name="prepare-your-data"></a>Preparar los datos

Vamos a usar un conjunto de datos existente utilizado para un escenario de "análisis de sentimiento", que es una tarea de aprendizaje automático de clasificación binaria. Puede usar su propio conjunto de datos de forma similar, y el modelo y el código se generarán automáticamente.

1. Descargue el [archivo ZIP del conjunto de datos UCI Sentiment Labeled Sentences (vea la referencia en la nota siguiente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo en la carpeta de su elección.

    > [!NOTE]
    > Los conjuntos de datos que se utilizan en este tutorial provienen de "From Group to Individual Labels using Deep Features", Kotzias et. al., KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ]. Irvine, CA: University of California, School of Information and Computer Science.

2. Copie el archivo `yelp_labelled.txt` en cualquier carpeta que haya creado anteriormente (como `/cli-test`).

3. Abra su símbolo del sistema preferido y muévalo a la carpeta donde copió el archivo del conjunto de datos. Por ejemplo:

    ```console
    cd /cli-test
    ```

    Con cualquier editor de texto como Visual Studio Code, puede abrir y explorar el archivo del conjunto de datos `yelp_labelled.txt`. Puede ver la estructura de la siguiente manera:

    - El archivo no tiene encabezado. Usará el índice de la columna.

    - Solo hay dos columnas:

        | Texto (índice de la columna 0) | Etiqueta (índice de la columna 1)|
        |--------------------------|-------|
        | ¡Anda! Me encantó el lugar. | 1 |
        | La corteza no es buena. | 0 |
        | No es sabrosa y la textura era simplemente desagradable. | 0 |
        | ...MUCHAS MÁS FILAS DE TEXTO... | ...(1 o 0)... |

    Asegúrese de cerrar el archivo del conjunto de datos desde el editor.

    Ya está listo para empezar a usar la CLI en este escenario de "análisis de sentimiento".

    > [!NOTE]
    > Al finalizar este tutorial, también puede probar con sus propios conjuntos de datos, siempre que estén listos para usarse en cualquiera de las tareas de ML compatibles actualmente con la versión preliminar de la CLI de ML.NET, que son *"Clasificación binaria", "Clasificación multiclase" y "Regresión"* ).

## <a name="run-the-mlnet-auto-train-command"></a>Ejecutar el comando "mlnet auto-train"

1. Ejecute el siguiente comando de la CLI de ML.NET:

    ```console
    mlnet auto-train --task binary-classification --dataset "yelp_labelled.txt" --label-column-index 1 --has-header false --max-exploration-time 10
    ```

    Este comando ejecuta el **comando `mlnet auto-train`** :
    - para una **tarea de ML** de tipo **`binary-classification`**
    - usa el **archivo del conjunto de datos `yelp_labelled.txt`** como conjunto de datos de entrenamiento y pruebas (internamente la CLI utilizará la validación cruzada o lo dividirá en dos conjuntos de datos: uno para el entrenamiento y otro para las pruebas)
    - donde la **columna de objetivo/destino** que desea predecir (comúnmente denominada **"etiqueta"** ) es la **columna con el índice 1** (que es la segunda columna, ya que el índice es de base cero)
    - **no usa un encabezado de archivo** con nombres de columna, puesto que este archivo de conjunto de datos concreto no tiene un encabezado
    - el **tiempo de exploración dirigida** para el experimento es de **10 segundos**

    Verá la salida de la CLI, similar a:

    <!-- markdownlint-disable MD023 MD025 -->

    # <a name="windowstabwindows"></a>[Windows](#tab/windows)

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-powershell.gif)

    # <a name="macos-bashtabmacosbash"></a>[Bash de macOS](#tab/macosbash)

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-bash.gif)

    En este caso en concreto, en solo 10 segundos y con el pequeño conjunto de datos proporcionado, la herramienta de la CLI fue capaz de ejecutar varias iteraciones, lo que implica entrenar varias veces según diferentes combinaciones de algoritmos o la configuración con diferentes transformaciones de datos internos e hiperparámetros del algoritmo.

    Por último, el modelo de "mejor calidad" que se encontró en 10 segundos es un modelo que usa un instructor o algoritmo concreto con cualquier configuración específica. Según el tiempo de exploración, el comando puede generar un resultado diferente. La selección se basa en las diversas métricas que se muestran, como `Accuracy`.

    **Descripción de las métricas de calidad del modelo**

    La primera métrica y la más sencilla para evaluar un modelo de clasificación binaria es la precisión, la cual es muy fácil de entender. "La precisión es la proporción de predicciones correctas con un conjunto de datos de prueba". Cuanto más cerca del 100 % (1,00), mejor.

    Sin embargo, hay casos en los que solo medir con la métrica de precisión no es suficiente, especialmente cuando la etiqueta (0 y 1 en este caso) está desequilibrada en el conjunto de datos de prueba.

    Para ver métricas adicionales e **información más detallada acerca de las métricas**, como la precisión, AUC, AUCPR y la puntuación F1 utilizada para evaluar los distintos modelos, lea [Descripción de las métricas de ML.NET](../resources/metrics.md).

    > [!NOTE]
    > Puede probar este mismo conjunto de datos y especificar unos minutos para `--max-exploration-time` (por ejemplo, tres minutos, por lo que se especifican 180 segundos) que encontrará un "mejor modelo" con una configuración de canalización de entrenamiento distinta para este conjunto de datos (que es bastante pequeño: 1000 filas).

    Para encontrar un modelo de "mejor o buena calidad" que sea un "modelo listo para la producción" dirigido a conjuntos de datos grandes, debe realizar experimentos con la CLI normalmente especificando mucho más tiempo de exploración según el tamaño del conjunto de datos. De hecho, en muchos casos es posible que necesite varias horas de exploración, sobre todo si el conjunto de datos es de gran tamaño en filas y columnas.

1. La ejecución del comando anterior ha generado los siguientes recursos:

    - Un .zip de modelo serializado ("mejor modelo") listo para usarse.
    - El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).
    - El código de entrenamiento de C# utilizado para generar ese modelo (con fines de aprendizaje).
    - Un archivo de registro con todas las iteraciones exploradas con información detallada específica acerca de cada algoritmo que se ha intentado con su combinación de hiperparámetros y transformaciones de datos.

    Los dos primeros recursos (modelo de archivo ZIP y el código de C# para ejecutar ese modelo) se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.

    El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI.

Esos recursos enumerados se explican en los pasos siguientes del tutorial.

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a>Explorar el código de C# generado que se usará para ejecutar el modelo a fin de realizar predicciones

1. En Visual Studio (2017 o 2019), abra la solución generada en la carpeta denominada `SampleBinaryClassification` dentro de la carpeta de destino original (en el tutorial se denominaba `/cli-test`). Debería ver una solución similar a esta:

    > [!NOTE]
    > En el tutorial, se recomienda usar Visual Studio, pero también puede explorar el código de C# generado (dos proyectos) con cualquier editor de texto y ejecutar la aplicación de consola generada con la `dotnet CLI` en macOS, máquina Linux o Windows.

    ![Solución de VS generada por la CLI](./media/mlnet-cli/generated-csharp-solution-detailed.png)

    - La **biblioteca de clases** generada que contiene el modelo serializado de ML (archivo .zip) y las clases de datos (modelo de datos) es algo que puede usar directamente en la aplicación del usuario final, incluso haciendo referencia directamente a esa biblioteca de clases (o moviendo el código, como desee).
    - La **aplicación de consola** generada contiene un código de ejecución que debe revisar. Después, normalmente reutiliza el "código de puntuación" (el código que ejecuta el modelo de ML para realizar predicciones) moviendo ese código sencillo (unas cuantas líneas) a la aplicación del usuario final en la que quiere realizar las predicciones.

1. Abra los archivos de clase **ModelInput.cs** y **ModelOutput.cs** en el proyecto de la biblioteca de clases. Verá que estas clases son "clases de datos" o clases POCO que se usan para almacenar datos. Se trata de "código reutilizable", pero resulta útil generarlo si el conjunto de datos tiene decenas o incluso centenares de columnas.
    - La clase `ModelInput` se usa al leer los datos del conjunto de datos.
    - La clase `ModelOutput` se utiliza para obtener el resultado de la predicción (datos de predicción).

1. Abra el archivo Program.cs y explore el código. En unas cuantas líneas, podrá ejecutar el modelo y realizar una predicción de ejemplo.

    ```csharp
    static void Main(string[] args)
    {
        MLContext mlContext = new MLContext();

        // Training code used by ML.NET CLI and AutoML to generate the model
        //ModelBuilder.CreateModel();

        ITransformer mlModel = mlContext.Model.Load(MODEL_FILEPATH, out DataViewSchema inputSchema);
        var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // Create sample data to do a single prediction with it
        ModelInput sampleData = CreateSingleDataSample(mlContext, DATA_FILEPATH);

        // Try a single prediction
        ModelOutput predictionResult = predEngine.Predict(sampleData);

        Console.WriteLine($"Single Prediction --> Actual value: {sampleData.Label} | Predicted value: {predictionResult.Prediction}");
    }
    ```

- La primera línea de código crea simplemente un objeto `MLContext` necesario cada vez que se ejecuta el código de ML.NET.

- La segunda línea de código está comentada porque no es necesario entrenar el modelo debido a que la herramienta de la CLI ya lo ha entrenado y guardado en el archivo ZIP serializado del modelo. Pero si desea ver *"cómo la CLI entrenó el modelo"* , puede quitar la marca del comentario en esa línea y ejecutar o depurar el código de aprendizaje para ese modelo particular de ML.

- En la tercera línea de código, cargue el modelo desde el archivo ZIP del modelo serializado con la API `mlContext.Model.Load()` proporcionando la ruta de acceso al archivo ZIP de ese modelo.

- En la cuarta línea de código, cree el objeto `PredictionEngine` con la API `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)`. Necesitará el objeto `PredictionEngine` cada vez que desee realizar una predicción dirigida a una única muestra de datos (en este caso, un fragmento único de texto para su opinión).

- La quinta línea de código es donde creará esos *datos de ejemplo únicos* que se usarán para la predicción mediante una llamada a la función `CreateSingleDataSample()`. Dado que la herramienta de la CLI no sabe qué tipo de datos de ejemplo se usarán, dentro de esa función se carga la primera fila del conjunto de datos. Sin embargo, en este caso también puede crear sus propios datos "codificados de forma rígida", en lugar de la implementación actual de la función `CreateSingleDataSample()` mediante la actualización de este código más sencillo implementando esa función:

    ```csharp
    private static ModelInput CreateSingleDataSample()
    {
        ModelInput sampleForPrediction = new ModelInput() { Col0 = "The ML.NET CLI is great for getting started. Very cool!", Label = true };
        return sampleForPrediction;
    }
    ```

1. Ejecute el proyecto, ya sea mediante los datos de ejemplo originales cargados desde la primera fila del conjunto de datos o proporcionando sus propios datos de ejemplo codificados de forma rígida y personalizados. Debería obtener una predicción comparable a esta:

    # <a name="windowstabwindows"></a>[Windows](#tab/windows)

    Ejecute la aplicación de consola desde Visual Studio presionando F5 (botón de reproducción):

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/sample-cli-prediction-execution.png))

    # <a name="macos-bashtabmacosbash"></a>[Bash de macOS](#tab/macosbash)

    Ejecute la aplicación de consola desde el símbolo del sistema escribiendo los siguientes comandos:

     ```bash
     cd SampleBinaryClassification
     cd SampleBinaryClassification.ConsoleApp

     dotnet run
     ```

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/sample-cli-prediction-execution-bash.png))

    ---

1. Pruebe a cambiar los datos de ejemplo codificados de forma rígida a otras frases con diferentes opiniones y vea cómo el modelo predice opiniones positivas o negativas.

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a>Incorporar las aplicaciones del usuario final con predicciones del modelo de ML

Puede usar un "código de puntuación del modelo de ML" similar para ejecutar el modelo en la aplicación del usuario final y realizar predicciones.

Por ejemplo, podría mover directamente ese código a cualquier aplicación de escritorio de Windows como **WPF** y **WinForms** y ejecutar el modelo de la misma manera que se realizó en la aplicación de consola.

Sin embargo, la forma de implementar esas líneas de código para ejecutar un modelo de ML debe optimizarse (es decir, copie en caché el archivo .zip del modelo y cárguelo una vez) y debe tener objetos singleton en lugar de crearlos en cada solicitud, especialmente si la aplicación debe ser escalable como una aplicación web o un servicio distribuido, tal como se explica en la sección siguiente.

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a>Ejecución de modelos de ML.NET en aplicaciones web y servicios escalables de ASP.NET Core (aplicaciones multiproceso)

La creación del objeto de modelo (`ITransformer` cargado desde el archivo .zip de un modelo) y el objeto `PredictionEngine` debe optimizarse especialmente cuando se ejecuta en aplicaciones web escalables y servicios distribuidos. En el primer caso, el objeto de modelo (`ITransformer`), la optimización es sencilla. Puesto que el objeto `ITransformer` es seguro para subprocesos, puede copiar en caché el objeto como un singleton o un objeto estático para cargar el modelo una vez.

En el segundo objeto, el objeto `PredictionEngine`, no es tan fácil porque el objeto `PredictionEngine` no es seguro para subprocesos, por lo que no se puede crear una instancia de este objeto como singleton u objeto estático en una aplicación de ASP.NET Core. Este problema de escalabilidad y seguridad para subprocesos se describe detalladamente en esta [entrada de blog](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).

Sin embargo, las cosas ahora son mucho más fáciles de lo que se explica en esa entrada de blog. Hemos trabajado en un enfoque más sencillo para usted y hemos creado un buen **"paquete de integración de .NET Core"** que puede usar fácilmente en sus servicios y aplicaciones de ASP.NET Core registrándolos en los servicios de DI de la aplicación (servicios de inserción de dependencias) y usándolos directamente desde el código. Consulte el siguiente tutorial y ejemplo para hacerlo:

- [Tutorial: Ejecución de modelos de ML.NET en aplicaciones web escalables de ASP.NET Core y WebAPI](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Ejemplo: Modelo de ML.NET escalable en ASP.NET Core WebAPI](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a>Explorar el código de C# generado que se usó para entrenar el modelo de "mejor calidad"

Para fines de aprendizaje más avanzados, también puede explorar el código de C# generado que utilizó la herramienta de la CLI para entrenar el modelo generado.

Dicho "código de modelo de entrenamiento" se genera actualmente en la clase personalizada generada denominada `ModelBuilder` para que pueda investigar el código de entrenamiento.

Más importante aún, para este escenario en particular (modelo de análisis de sentimiento) también puede comparar dicho código de entrenamiento generado con el código que se explica en el tutorial siguiente:

- Comparación: [Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento](sentiment-analysis.md).

Resulta interesante comparar el algoritmo elegido y la configuración de canalización en el tutorial con el código generado por la herramienta de la CLI. Según cuánto tiempo dedique a iterar y buscar modelos mejores, el algoritmo elegido podría ser diferente, junto con su configuración de canalización e hiperparámetros determinados.

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Preparar los datos para la tarea de ML seleccionada (problema para resolver)
> - Ejecutar el comando "mlnet auto-train" en la herramienta de la CLI
> - Revisar los resultados de métrica de calidad
> - Comprender el código de C# generado para ejecutar el modelo (código para usar en la aplicación del usuario final)
> - Explorar el código de C# generado que se usó para entrenar el modelo de "mejor calidad" (con fines de aprendizaje)

## <a name="see-also"></a>Vea también

- [Automatizar el entrenamiento del modelo con la CLI de ML.NET](../automate-training-with-cli.md)
- [Tutorial: Ejecución de modelos de ML.NET en aplicaciones web escalables de ASP.NET Core y WebAPI](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Ejemplo: Modelo de ML.NET escalable en ASP.NET Core WebAPI](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [Guía de referencia de comandos de entrenamiento automático de la CLI de ML.NET](../reference/ml-net-cli-reference.md)
- [Telemetría en la CLI de ML.NET](../resources/ml-net-cli-telemetry.md)
