---
title: 'Tutorial: Clasificación de flores de iris (agrupación en clústeres k-means)'
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 8ee8b177dc9cc89c4f54956b8c0a274b1d093ece
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282091"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a>Tutorial: Clasificación de flores de iris mediante la agrupación en clústeres k-means con ML.NET

En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Entender el problema
> - Seleccionar la tarea de aprendizaje automático adecuada
> - Preparar los datos
> - Cargar y transformar los datos
> - Elegir un algoritmo de aprendizaje
> - Entrenar el modelo
> - Usar el modelo para las predicciones

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="understand-the-problem"></a>Entender el problema

Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor. Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo. Para este tutorial, se supone que el tipo de cada flor es desconocido. Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning). Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** . En el cuadro de texto **Nombre**, escriba "IrisFlowerClustering" y después haga clic en el botón **Aceptar**.

1. Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

1. Instale el paquete NuGet **Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML** y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="prepare-the-data"></a>Preparar los datos

1. Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior. Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

El archivo *iris.data* contiene cinco columnas que representan lo siguiente:

- La longitud del sépalo en centímetros
- El ancho del sépalo en centímetros
- La longitud del pétalo en centímetros
- El ancho del pétalo en centímetros
- El tipo de flor de iris.

Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.

## <a name="create-data-classes"></a>Crear clases de datos

Cree clases para los datos de entrada y las predicciones:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*. A continuación, seleccione el botón **Agregar**.
1. Agregue la directiva `using` siguiente al archivo nuevo:

   [!code-csharp[Add necessary usings](./snippets/iris-clustering/csharp/IrisData.cs#Usings)]

Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:

[!code-csharp[Define data classes](./snippets/iris-clustering/csharp/IrisData.cs#ClassDefinitions)]

`IrisData` es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos. Use el atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.

La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`. Use el atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente. En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:

- La columna **PredictedLabel** contiene el identificador del clúster previsto.
- La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster. La longitud de la matriz es igual al número de clústeres.

> [!NOTE]
> Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.

## <a name="define-data-and-model-paths"></a>Definir rutas de acceso de datos y modelos

Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:

- `_dataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.
- `_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.

Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:

[!code-csharp[Initialize paths](./snippets/iris-clustering/csharp/Program.cs#Paths)]

Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[Add usings for paths](./snippets/iris-clustering/csharp/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a>Creación del contexto de ML

Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[Add Microsoft.ML usings](./snippets/iris-clustering/csharp/Program.cs#MLUsings)]

En el método `Main`, reemplace la línea `Console.WriteLine("Hello World!");` con el código siguiente:

[!code-csharp[Create ML context](./snippets/iris-clustering/csharp/Program.cs#CreateContext)]

La clase <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> representa el entorno de aprendizaje automático y proporciona mecanismos para puntos de entrada y de registro para la carga de datos, entrenamiento del modelo, predicción y otras tareas. Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.

## <a name="set-up-data-loading"></a>Configuración de la carga de datos

Agregue el código siguiente al método `Main` para configurar la manera de cargar los datos:

[!code-csharp[Create text loader](./snippets/iris-clustering/csharp/Program.cs#CreateDataView)]

El [`MLContext.Data.LoadFromTextFile` método de extensión](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) genérico deduce el esquema del conjunto de datos del tipo `IrisData` proporcionado y devuelve <xref:Microsoft.ML.IDataView>, que se puede usar como entrada para los transformadores.

## <a name="create-a-learning-pipeline"></a>Crear una canalización de aprendizaje

Para este tutorial, la canalización de aprendizaje de la tarea de agrupación en clústeres consta de los dos pasos siguientes:

- concatenar las columnas cargadas en una columna **Características**, que usa un instructor de agrupación en clústeres;
- usar un instructor <xref:Microsoft.ML.Trainers.KMeansTrainer> para entrenar el modelo mediante el algoritmo de agrupación en clústeres k-means++.

Agregue el código siguiente al método `Main`:

[!code-csharp[Create pipeline](./snippets/iris-clustering/csharp/Program.cs#CreatePipeline)]

En el código se especifica que el conjunto de datos se debe dividir en tres clústeres.

## <a name="train-the-model"></a>Entrenar el modelo

Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno. Agregue la línea siguiente al método `Main` para realizar la carga de datos y el entrenamiento del modelo:

[!code-csharp[Train the model](./snippets/iris-clustering/csharp/Program.cs#TrainModel)]

### <a name="save-the-model"></a>Guardado del modelo

En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main`:

[!code-csharp[Save the model](./snippets/iris-clustering/csharp/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

Para realizar predicciones, use la clase <xref:Microsoft.ML.PredictionEngine%602>, que toma instancias del tipo de entrada a través de la canalización de transformador y genera instancias del tipo de salida. Agregue la línea siguiente al método `Main` para crear una instancia de esa clase:

[!code-csharp[Create predictor](./snippets/iris-clustering/csharp/Program.cs#Predictor)]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*. A continuación, seleccione el botón **Agregar**.
1. Modifique la clase para que sea estática, como en el ejemplo siguiente:

   [!code-csharp[Make class static](./snippets/iris-clustering/csharp/TestIrisData.cs#Static)]

En este tutorial se presenta una instancia de datos de iris dentro de esta clase. Puede agregar otros escenarios para experimentar con el modelo. Agregue el código siguiente a la clase `TestIrisData`:

[!code-csharp[Test data](./snippets/iris-clustering/csharp/TestIrisData.cs#TestData)]

Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:

[!code-csharp[Predict and output results](./snippets/iris-clustering/csharp/Program.cs#PredictionExample)]

Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster. Los resultados deberían ser similares a los indicados a continuación:

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

¡Enhorabuena! Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones. Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) de GitHub.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Entender el problema
> - Seleccionar la tarea de aprendizaje automático adecuada
> - Preparar los datos
> - Cargar y transformar los datos
> - Elegir un algoritmo de aprendizaje
> - Entrenar el modelo
> - Usar el modelo para las predicciones

Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.
> [!div class="nextstepaction"]
> [Repositorio de GitHub de dotnet/machinelearning](https://github.com/dotnet/machinelearning/)
