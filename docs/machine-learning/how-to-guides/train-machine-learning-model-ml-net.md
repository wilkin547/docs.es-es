---
title: Entrenamiento y evaluación de un modelo
description: Obtenga más información sobre cómo compilar modelos de aprendizaje automático, recopilar métricas y medir el rendimiento con ML.NET. Un modelo de aprendizaje automático identifica patrones en los datos de entrenamiento para realizar predicciones mediante datos nuevos.
ms.date: 03/31/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 51499f2c0ece615a99740bd9b27f99d4b5ed1d01
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523853"
---
# <a name="train-and-evaluate-a-model"></a>Entrenamiento y evaluación de un modelo

Obtenga más información sobre cómo compilar modelos de aprendizaje automático, recopilar métricas y medir el rendimiento con ML.NET. Aunque este ejemplo entrena un modelo de regresión, los conceptos se aplican en casi todos los demás algoritmos.

## <a name="split-data-for-training-and-testing"></a>Dividir datos para entrenamiento y pruebas

El objetivo de un modelo de aprendizaje automático es identificar patrones en los datos de entrenamiento. Estos patrones se usan para realizar predicciones con datos nuevos.

Los datos se pueden modelar mediante una clase como `HousingData`.

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

Empleando los siguientes datos que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

Use el método [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) para dividir los datos en conjuntos de entrenamiento y pruebas. El resultado será un objeto [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) que contiene dos miembros de [`IDataView`](xref:Microsoft.ML.IDataView): uno para el conjunto de entrenamiento y otro para el conjunto de pruebas. El porcentaje de división de datos viene determinado por el parámetro `testFraction`. El siguiente fragmento está reteniendo el 20 por ciento de los datos originales para el conjunto de pruebas.

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a>Preparar los datos

Los datos deben procesarse antes de entrenar un modelo de aprendizaje automático. Puede encontrar más información sobre la preparación de los datos en el [artículo de procedimientos de preparación de datos](prepare-data-ml-net.md), así como en la [`transforms page`](../resources/transforms.md).

Los algoritmos de ML.NET tienen restricciones en los tipos de columna de entrada. Además, se usan valores predeterminados para los nombres de columna de entrada y salida cuando no se especifica ningún valor.

### <a name="working-with-expected-column-types"></a>Trabajar con tipos de columna esperados

Los algoritmos de aprendizaje automático en ML.NET esperan un vector de punto flotante de tamaño conocido como entrada. Aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) al modelo de datos cuando todos los datos ya están en formato numérico y están pensados para procesarse juntos (es decir, píxeles de imagen).

Si todos los datos no son numéricos y desea aplicar diferentes transformaciones de datos en cada una de las columnas individualmente, utilice el método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) después de que todas las columnas se hayan procesado para combinar todas las columnas individuales en un vector de característica única que se genera en una nueva columna.

El siguiente fragmento de código combina las columnas `Size` y `HistoricalPrices` en un vector de característica única cuya salida es una nueva columna denominada `Features`. Dado que hay una diferencia en escalas, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) se aplica a la columna `Features` para normalizar los datos.

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a>Trabajar con nombres de columna predeterminados

Los algoritmos de ML.NET utilizan nombres de columna predeterminados cuando no se especifica ninguno. Todos los instructores tienen un parámetro denominado `featureColumnName` para las entradas del algoritmo y, si corresponde, también tienen un parámetro para el valor esperado `labelColumnName`. De forma predeterminada, estos valores son `Features` y `Label`, respectivamente.

Mediante el uso del método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) durante el preprocesamiento para crear una nueva columna denominada `Features`, no es necesario especificar el nombre de columna de característica en los parámetros del algoritmo porque ya existe en el `IDataView` procesado previamente. La columna de etiqueta es `CurrentPrice`, pero dado que el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) se usa en el modelo de datos, ML.NET cambia el nombre de la columna `CurrentPrice` a `Label`, lo cual elimina la necesidad de proporcionar el parámetro `labelColumnName` para el estimador de algoritmo de aprendizaje automático.

Si no desea usar los nombres de columna predeterminada, pase los nombres de las columnas de característica y etiqueta como parámetros al definir el estimador de algoritmo de aprendizaje automático, tal como se demuestra en el fragmento de código siguiente:

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="caching-data"></a>Almacenamiento de datos en caché

De forma predeterminada, cuando se procesan los datos se cargan o transmiten de forma diferida, lo que significa que los formadores pueden cargar los datos desde el disco e iterar varias veces durante el entrenamiento. Por lo tanto, se recomienda el almacenamiento en caché para los conjuntos de datos que quepan en la memoria a fin de reducir el número de veces que los datos se cargan desde el disco. El almacenamiento en caché se realiza como parte de un elemento [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) mediante el uso de [`AppendCacheCheckpoint`](xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A).

Se recomienda usar [`AppendCacheCheckpoint`](xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A) antes que los formadores de la canalización.

Con el elemento [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) siguiente, agregar [`AppendCacheCheckpoint`](xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A) antes que el formador de [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) almacena en caché los resultados de los estimadores anteriores para su uso posterior por parte del formador.

```csharp
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
// 3. Cache prepared data
// 4. Use Sdca trainer to train the model
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .AppendCacheCheckpoint(mlContext);
        .Append(mlContext.Regression.Trainers.Sdca());
```

## <a name="train-the-machine-learning-model"></a>Entrenar el modelo de Machine Learning

Una vez que se hayan procesado previamente los datos, utilice el método [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase%602.Fit%2A) para entrenar el modelo de aprendizaje automático con el algoritmo de regresión [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer).

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a>Extraer parámetros del modelo

Una vez entrenado el modelo, extraiga el elemento [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) aprendido para su inspección o para volver a entrenarlo. Los parámetros [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) proporcionan los coeficientes aprendidos y de sesgo, o los pesos del modelo entrenado.

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> Otros modelos disponen de parámetros que son específicos para sus tareas. Por ejemplo, el [algoritmo K-Means](xref:Microsoft.ML.Trainers.KMeansTrainer) coloca datos en clúster en función de centroides y [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contiene una propiedad que almacena estos centroides aprendidos. Para obtener más información, visite la [`Microsoft.ML.Trainers` documentación de la API](xref:Microsoft.ML.Trainers) y busque las clases que contienen `ModelParameters` en su nombre.

## <a name="evaluate-model-quality"></a>Evaluar la calidad del modelo

Para ayudar a elegir el mejor modelo de rendimiento, es esencial evaluar su rendimiento en datos de prueba. Use el método [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) para medir diversas métricas para el modelo entrenado.

> [!NOTE]
> El método `Evaluate` genera diferentes métricas en función de la tarea de aprendizaje automático que se realizó. Para obtener más información, visite la [`Microsoft.ML.Data` documentación de la API](xref:Microsoft.ML.Data) y busque las clases que contienen `Metrics` en su nombre.

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

En el ejemplo de código anterior:

1. El conjunto de datos de prueba está procesado previamente mediante transformaciones de preparación de datos definidas con anterioridad.
2. El modelo de aprendizaje automático entrenado se utiliza para realizar predicciones sobre los datos de prueba.
3. En el método `Evaluate`, los valores de la columna `CurrentPrice` del conjunto de datos de prueba se comparan con la columna `Score` de las predicciones recientemente generadas para calcular las métricas del modelo de regresión, una de las cuales, R cuadrado, se almacena en la variable `rSquared`.

> [!NOTE]
> En este pequeño ejemplo, el valor de R cuadrado es un número que no está comprendido entre 0 y 1, debido al tamaño limitado de los datos. En un escenario real, debería ver un valor comprendido entre 0 y 1.
