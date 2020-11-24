---
title: Tutorial de análisis de sentimiento con .NET para Apache Spark y ML.NET
description: En este tutorial, aprenderá a usar ML.NET con .NET para Apache Spark con fin de realizar análisis de sentimiento.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 1c2c966a4ff50a9d2f6951e20d909c5c20c75bfb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688246"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a>Tutorial: Análisis de sentimiento con .NET para Apache Spark y ML.NET

En este tutorial aprenderá a realizar análisis de sentimiento de las reseñas en línea con ML.NET y .NET para Apache Spark. [ML.NET](http://dot.net/ml) es un marco de aprendizaje automático gratuito multiplataforma y de código abierto. Puede usar ML.NET con .NET para Apache Spark para escalar el entrenamiento y la predicción de los algoritmos de aprendizaje automático.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> * Crear un modelo de análisis de sentimiento mediante la herramienta Model Builder de ML.NET disponible en Visual Studio
> * Crear una aplicación de consola de .NET para Apache Spark
> * Escribir e implementar una función definida por el usuario
> * Ejecutar una aplicación de consola de .NET para Apache Spark

## <a name="prerequisites"></a>Requisitos previos

* Si nunca ha desarrollado una aplicación de .NET para Apache Spark, comience con el [tutorial de introducción](get-started.md) para familiarizarse con los aspectos básicos. Complete todos los requisitos previos del tutorial de introducción antes de continuar con este tutorial.

* En este tutorial se usa la herramienta Model Builder de ML.NET (versión preliminar), una interfaz visual que está disponible en Visual Studio. Si aún no tiene Visual Studio, puede [descargar la versión Community de Visual Studio](https://visualstudio.microsoft.com/downloads/) de forma gratuita.

* [Descargue e instale](https://marketplace.visualstudio.com/items?itemName=MLNET.07) la herramienta Model Builder de ML.NET (versión preliminar).

* Descargue los conjuntos de datos de reseñas de Yelp [yelptest. csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) y [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv).

## <a name="review-the-data"></a>Revisión de los datos

El conjunto de datos de reseñas de Yelp contiene reseñás en línea de Yelp sobre varios servicios. Abra [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) y observe la estructura de los datos. La primera columna contiene el texto de la reseña, y la segunda, puntuaciones de opinión. Si la puntuación de opinión es 1, la reseña es positiva y, si es 0, la reseña es negativa.

La siguiente tabla contiene datos de ejemplo:

|ReviewText|Opinión|
|-|-|
|¡Ah! Me encantó el lugar.|    1|
|La corteza no es buena.|    0|

## <a name="build-your-machine-learning-model"></a>Compilación de un modelo de Machine Learning propio

1. Abra Visual Studio y cree una aplicación de consola C# (.NET Core). Asigne al proyecto el nombre *MLSparkModel*.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *MLSparkModel*. A continuación, seleccione **Agregar > Machine Learning**.

1. En la herramienta Model Builder de ML.NET, seleccione el icono de escenario **Sentiment Analysis** (Análisis de sentimiento).

1. En la página **Add data** (Agregar datos), cargue el conjunto de datos *yelptrain.csv*.

1. Elija *Sentiment* (Sentimiento) en la lista desplegable **Columns to Predict** (Columnas para predecir).

1. En la página **Train** (Entrenar), establezca la hora de entrenamiento en *60 segundos* y seleccione **Start training** (Iniciar entrenamiento). Observe el estado del entrenamiento en **Progress** (Progreso).

1. Una vez que Model Builder finaliza el entrenamiento, **evalúe** los resultados del entrenamiento. Puede escribir frases en el cuadro de texto que aparece a continuación **Try your model** (Probar el modelo) y seleccionar **Predict** (Predecir) para ver el resultado.

1. Seleccione **Code** (Código) y, a continuación, seleccione **Add Projects** (Agregar proyectos) para agregar el modelo de aprendizaje automático a la solución.

1. Tenga en cuenta que se agregan dos proyectos a las soluciones: **MLSparkModelML.ConsoleApp** y **MLSparkModelML.Model**.

1. Haga doble clic en el proyecto *MLSpark* de C# y observe que se ha agregado la siguiente referencia de proyecto.

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a>Crear una aplicación de consola

Model Builder crea una aplicación de consola automáticamente.

1. Haga clic con el botón derecho en **MLSparkModelML.Console** en el Explorador de soluciones y seleccione **Administrar paquetes NuGet**.

1. Busque **Microsoft.Spark** e instale el paquete. Model Builder instala automáticamente **Microsoft.ML**.

### <a name="create-a-sparksession"></a>Creación de una SparkSession

1. Abra el archivo *Program.cs* de **MLSparkModelML.ConsoleApp**. Model Builder generó automáticamente ese archivo. Elimine las instrucciones `using`, el contenido del método Main() y la región `CreateSingleDataSample`.

1. Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. Cambie `DATA_FILEPATH` a la ruta de acceso de *yelptest.csv*.

1. Agregue el código siguiente al método `Main` para crear una nueva `SparkSession`. La sesión de Spark es el punto de entrada para programar Spark con la API de DataFrame y DataSet.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   Llamar al objeto *spark* creado anteriormente le permite tener acceso a la funcionalidad de DataFrame y Spark a través del programa.

### <a name="create-a-dataframe-and-print-to-console"></a>Creación de un objeto DataFrame e impresión en la consola

Lea los datos de reseñas de Yelp del archivo *yelptest.csv* como `DataFrame`. Incluya las opciones `header` y `inferSchema`. La opción `header` lee la primera línea de *yelptest.csv* como nombres de columna en lugar de como datos. La opción `inferSchema` deduce los tipos de columna en función de los datos.

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a>Registro de una función definida por el usuario

Puede usar UDF, *funciones definidas por el usuario*, en aplicaciones Spark para realizar cálculos y análisis de los datos. En este tutorial, usará ML.NET con UDF para evaluar cada reseña de Yelp.

Agregue el siguiente código a su método `Main` para registrar una UDF llamada `MLudf`.

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

Esta función UDF toma una cadena de reseña de Yelp como entrada y genera valores "true" o "false" para las opiniones positivas o negativas, respectivamente. Usa el método *predict()* que se define en un paso posterior.

### <a name="use-spark-sql-to-call-the-udf"></a>Uso de Spark SQL para llamar a la función UDF

Ahora que ha leído los datos y ha incorporado el aprendizaje automático, use Spark SQL para llamar a la función UDF que ejecutará el análisis de sentimiento en cada fila del objeto DataFrame. Agregue el código siguiente al método `Main`:

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a>Creación del método predict()

Agregue el código siguiente al método `Main()`. Este código es similar al que genera Model Builder en *ConsumeModel.cs*. Al mover este método a la consola, se carga el modelo cada vez que se ejecuta la aplicación.

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a>Incorporación del modelo a la aplicación de consola

En el Explorador de soluciones, copie el archivo *MLModel.zip* del proyecto **MLSparkModelML.Model** y péguelo en el proyecto **MLSparkModelML.ConsoleApp**. Se agrega automáticamente una referencia en *MLSparkModelML.ConsoleApp. csproj*.

## <a name="run-your-code"></a>Ejecución del código

Use `spark-submit` para ejecutar el código. Vaya a la carpeta raíz de la aplicación de consola mediante el símbolo del sistema y ejecute los siguientes comandos.

En primer lugar, limpie y publique la aplicación.

```dotnetcli
dotnet clean
dotnet publish
```

Después, vaya a la carpeta de publicación de la aplicación de consola y ejecute el siguiente comando: `spark-submit`. Asegúrese de actualizar el comando anterior con la ruta de acceso real al archivo .jar de Microsoft Spark.

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2-4_2.11-1.0.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a>Obtención del código

Este tutorial es similar al código del ejemplo del [análisis de sentimiento con macrodatos](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment).

## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para aprender a realizar flujos estructurados con .NET para Apache Spark.
> [!div class="nextstepaction"]
> [Tutorial: Streaming estructurado con .NET para Apache Spark](streaming.md)
