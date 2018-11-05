---
title: Uso de ML.NET para agrupar flores de iris en clústeres (agrupación en clústeres)
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bb41fd317507c14b46aea94e1ce576e390932a65
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453195"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a>Tutorial: Uso de ML.NET para agrupar flores de iris en clústeres (agrupación en clústeres)

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Entender el problema
> - Seleccionar la tarea de aprendizaje automático adecuada
> - Preparar los datos
> - Cargar y transformar los datos
> - Elegir un algoritmo de aprendizaje
> - Entrenar el modelo
> - Usar el modelo para las predicciones

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="understand-the-problem"></a>Entender el problema

Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor. Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo. Para este tutorial, se supone que el tipo de cada flor es desconocido. Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning). Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "IrisClustering" y después haga clic en el botón **Aceptar**.

1. Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

1. Instale el paquete NuGet **Microsoft.ML**:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="prepare-the-data"></a>Preparar los datos

1. Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior. Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

El archivo *iris.data* contiene cinco columnas que representan lo siguiente:

- La longitud del sépalo en centímetros.
- El ancho del sépalo en centímetros.
- La longitud del pétalo en centímetros.
- El ancho del pétalo en centímetros.
- El tipo de flor de iris.

Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.

## <a name="create-data-classes"></a>Crear clases de datos

Cree clases para los datos de entrada y las predicciones:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*. A continuación, seleccione el botón **Agregar**.
1. Agregue la directiva `using` siguiente al archivo nuevo:

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

`IrisData` es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos. Use el atributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.

La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`. Use el atributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente. En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:

- La columna **PredictedLabel** contiene el identificador del clúster previsto.
- La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster. La longitud de la matriz es igual al número de clústeres.

> [!NOTE]
> Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.

## <a name="define-data-and-model-paths"></a>Definir rutas de acceso de datos y modelos

Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:

- `_dataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.
- `_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.

Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a>Crear una canalización de aprendizaje

Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

En el método `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

El método `Train` entrena el modelo. Cree ese método justo debajo del método `Main`, mediante el código siguiente:

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo. Agregue el código siguiente al método `Train`:

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a>Cargar y transformar datos

El primer paso que se va a realizar es cargar el conjunto de datos de aprendizaje. En nuestro caso, el conjunto de datos de aprendizaje se almacena en el archivo de texto con una ruta de acceso definida por el campo `_dataPath`. En el archivo, las columnas se separan mediante una coma (","). Agregue el código siguiente al método `Train`:

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

El siguiente paso consiste en combinar todas las columnas de característica en la columna **Features** mediante la clase de transformación <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>. De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**. Agregue el código siguiente:

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**). El aprendiz entrena el modelo. ML.NET proporciona un aprendiz <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> que implementa el [algoritmo k-means](https://en.wikipedia.org/wiki/K-means_clustering) con un método mejorado para elegir los centroides de clúster iniciales.

Agregue el código siguiente al método `Train` después del código de procesamiento de datos que ha agregado en el paso anterior:

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

Use la propiedad <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> para especificar el número de clústeres. En el código anterior se especifica que el conjunto de datos se debe dividir en tres clústeres.

## <a name="train-the-model"></a>Entrenar el modelo

Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno. El método `pipeline.Train<TInput, TOutput>` genera el modelo que usa una instancia del tipo `TInput` para generar una instancia del tipo `TOutput`. Agregue el código siguiente al método `Train`:

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a>Guardado del modelo

En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main` debajo de la llamada al método `Train`:

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

El uso de `await` en el método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

También tiene que agregar la directiva `using` siguiente a la parte superior del archivo *Program.cs*:

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

Debido a que el método `async Main` es una característica agregada en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior. Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*. A continuación, seleccione el botón **Agregar**.
1. Modifique la clase para que sea estática, como en el ejemplo siguiente:

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

En este tutorial se presenta una instancia de datos de iris dentro de esta clase. Puede agregar otros escenarios para experimentar con el modelo. Agregue el código siguiente a la clase `TestIrisData`:

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster. Los resultados deberían ser similares a los indicados a continuación. A medida que se procesa la canalización, es posible que se muestren advertencias o mensajes de procesamiento. Se han quitado de los resultados siguientes para mayor claridad.

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

¡Enhorabuena! Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones. Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) de GitHub.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
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
