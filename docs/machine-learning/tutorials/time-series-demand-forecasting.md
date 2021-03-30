---
title: 'Tutorial: Previsión de la demanda de alquiler de bicicletas: serie temporal'
description: En este tutorial se muestra cómo prever la demanda de un servicio de alquiler de bicicletas mediante el análisis de serie temporal de variable única y ML.NET.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: aea264036ab4766696699980f464cca3d8229499
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875595"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a>Tutorial: Previsión de la demanda de servicio de alquiler de bicicletas con análisis de serie temporal y ML.NET

Obtenga información sobre cómo prever la demanda de un servicio de alquiler de bicicletas mediante el análisis de serie temporal de variable única en los datos almacenados en una base de datos SQL Server con ML.NET.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Entender el problema
> * Cargar datos desde una base de datos
> * Crear un modelo de previsión
> * Evaluar un modelo de previsión
> * Guardar un modelo de previsión
> * Usar un modelo de previsión

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="time-series-forecasting-sample-overview"></a>Información general de un ejemplo de previsión de serie temporal

Este ejemplo es una **aplicación de consola de .NET Core de C#** que prevé la demanda de alquileres de bicicletas con un algoritmo de análisis de serie temporal de variable única conocido como "análisis de un solo espectro". El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/Forecasting_BikeSharingDemand) en GitHub.

## <a name="understand-the-problem"></a>Entender el problema

Para ejecutar una operación eficaz, la administración de inventario desempeña un rol clave. Tener en existencia una cantidad excesiva de un producto significa que los productos no vendidos que se encuentran en las estanterías no generan ingresos. Tener una cantidad reducida de un producto hace que se pierdan ventas y que los clientes compren a la competencia. Por lo tanto, la pregunta constante es ¿cuál es la cantidad óptima de inventario que debe mantenerse a mano? El análisis de serie temporal lo ayuda a proporcionar una respuesta a estas preguntas examinando los datos históricos, identificando patrones y usando esta información para prever valores en el futuro.

La técnica para analizar los datos que usa este tutorial es el análisis de serie temporal de variable única. El análisis de serie temporal de variante única examina una única observación numérica durante un período de tiempo a intervalos específicos, como las ventas mensuales.

El algoritmo que se usa en este tutorial es el [análisis de un solo espectro (SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf). SSA sirve para descomponer una serie temporal en un conjunto de componentes principales. Estos componentes se pueden interpretar como partes de una señal que corresponde a tendencias, ruido, estacionalidad y muchos otros factores. Después, estos componentes se reconstruyen y se usan para pronosticar valores en el futuro.

## <a name="create-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core de C#** denominada "BikeDemandForecasting".
1. Instale el paquete NuGet versión **Microsoft.ML**.

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    1. En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.
    1. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar** y busque **Microsoft.ML**.
    1. Active la casilla **Incluir versión preliminar**.
    1. Seleccione el botón **Instalar**.
    1. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.
    1. Repita estos pasos para **System.Data.SqlClient** y **Microsoft.ML.TimeSeries**.

### <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Cree un directorio denominado *Data*.
1. Descargue el [archivo de base de datos *DailyDemand.mdf*](https://github.com/dotnet/machinelearning-samples/raw/main/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) y guárdelo en el directorio *Data*.

> [!NOTE]
> Los datos que se usan en este tutorial provienen del conjunto de datos [UCI Bike Sharing Dataset](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [vínculo web](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).

El conjunto de datos original contiene varias columnas correspondientes a la estacionalidad y al clima. Con el fin de ser breves y como el algoritmo que se usa en este tutorial solo requiere los valores de una columna numérica única, el conjunto de datos original se ha condensado para incluir solo las columnas siguientes:

- **dteday**: la fecha de la observación.
- **year**: el año codificado de la observación (0=2011, 1=2012).
- **cnt**: el número total de alquileres de bicicletas para ese día.

El conjunto de datos original se asigna a una tabla de base de datos con el esquema siguiente en una base de datos de SQL Server.

```sql
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

A continuación se muestra un ejemplo de los datos:

| RentalDate | Año | TotalRentals |
| --- | --- | --- |
|1/1/2011|0|985|
|1/2/2011|0|801|
|1/3/2011|0|1349|

### <a name="create-input-and-output-classes"></a>Creación de las clases de entrada y salida

1. Abra el archivo *Program.cs* y reemplace las instrucciones `using` existentes por las siguientes:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. Cree la clase `ModelInput`. Debajo de la clase `Program`, agregue el código siguiente.

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    La clase `ModelInput` contiene las columnas siguientes:

    - **RentalDate**: la fecha de la observación.
    - **Year**: el año codificado de la observación (0=2011, 1=2012).
    - **TotalRentals**: el número total de alquileres de bicicletas para ese día.

1. Cree la clase `ModelOutput` debajo de la clase `ModelInput` recién creada.

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    La clase `ModelOutput` contiene las columnas siguientes:

    - **ForecastedRentals**: los valores de predicción del período previsto.
    - **LowerBoundRentals**: los valores mínimos de predicción del período previsto.
    - **UpperBoundRentals**: los valores máximos de predicción del período previsto.

### <a name="define-paths-and-initialize-variables"></a>Definición de rutas de acceso e inicialización de variables

1. Dentro del método `Main`, defina las variables para almacenar la ubicación de los datos, la cadena de conexión y dónde guardar el modelo entrenado.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. Inicialice la variable `mlContext` con una instancia nueva de [`MLContext`](xref:Microsoft.ML.MLContext) mediante la incorporación de la línea siguiente en el método `Main`.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    La clase [`MLContext`](xref:Microsoft.ML.MLContext) es un punto inicial para todas las operaciones de ML.NET. Al inicializar mlContext, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

## <a name="load-the-data"></a>Carga de los datos

1. Cree `DatabaseLoader` que cargue los registros de tipo `ModelInput`.

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. Defina la consulta para cargar los datos de la base de datos.

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    Los algoritmos de ML.NET esperan que los datos sean de tipo [`Single`](xref:System.Single). Por lo tanto, los valores numéricos que provienen de la base de datos que no son de tipo [`Real`](xref:System.Data.SqlDbType), un valor de punto flotante de precisión sencilla, se deben convertir en [`Real`](xref:System.Data.SqlDbType).

    Las columnas `Year` y `TotalRental` son tipos enteros en la base de datos. Con la función integrada `CAST`, ambos se convierten en `Real`.

1. Cree un `DatabaseSource` para conectarse a la base de datos y ejecutar la consulta.

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. Cargue los datos en un `IDataView`.

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. El conjunto de datos contiene datos de dos años. Solo se usan los datos del primer año para el entrenamiento, el segundo año se mantiene para comparar los valores reales con el pronóstico generado por el modelo. Filtre los datos con la transformación [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    Para el primer año, se seleccionan solo los valores de la columna `Year` menores que 1 al establecer el parámetro `upperBound` en 1. A la inversa, para el segundo año, se seleccionan los valores mayores o iguales que 1 al establecer el parámetro `lowerBound` en 1.

## <a name="define-time-series-analysis-pipeline"></a>Definición de la canalización de análisis de serie temporal

1. Defina una canalización que use [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) para pronosticar valores en un conjunto de datos de serie temporal.

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    `forecastingPipeline` toma 365 puntos de datos para el primer año y muestrea o divide el conjunto de datos de serie temporal en intervalos de 30 días (mensualmente) según lo especificado en el parámetro `seriesLength`. Cada uno de estos ejemplos se analiza durante una ventana semanal o de 7 días. A la hora de determinar cuál es el valor de previsión para el período siguiente, se usan los valores de los siete días anteriores para realizar una predicción. El modelo se establece para pronosticar siete períodos en el futuro, tal como se define en el parámetro `horizon`. Como una previsión es una estimación informada, no siempre es 100  precisa. Por lo tanto, es conveniente conocer el intervalo de valores en los mejores y peores escenarios, tal como se define en los límites superior e inferior. En este caso, el nivel de confianza de los límites inferior y superior se establece en 95 %. El nivel de confianza se puede aumentar o reducir en consecuencia. Cuanto mayor sea el valor, más amplio será el intervalo entre los límites superior e inferior para lograr el nivel de confianza deseado.

1. Use el método [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit%2A) para entrenar el modelo y ajustar los datos a la `forecastingPipeline` definida previamente.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Evalúe el rendimiento del modelo al prever los datos del año siguiente y comparándolos con los valores reales.

1. Debajo del método `Main`, cree un método de utilidad denominado `Evaluate`.

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. Dentro del método `Evaluate`, prevea los datos del segundo año a través del método [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) con el modelo entrenado.

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. Obtenga los valores reales de los datos a través del método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A).

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. Use el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) para obtener los valores de previsión.

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. Calcule la diferencia entre los valores reales y los de previsión, lo que se conoce a menudo como "error".

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. Para medir el rendimiento, calcule los valores de error medio absoluto y medio y error cuadrático medio.

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    Para evaluar el rendimiento, se usan las métricas siguientes:

    - **Error medio absoluto**: mide la cercanía de las predicciones respecto del valor real. Este valor va de 0 a infinito. Cuanto más se acerque a 0, mejor es la calidad del modelo.
    - **Error cuadrático medio**: resume el error del modelo. Este valor va de 0 a infinito. Cuanto más se acerque a 0, mejor es la calidad del modelo.

1. Genere las métricas en la consola.

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. Use el método `Evaluate` dentro del método `Main`.

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a>Guardado del modelo

Si está satisfecho con el modelo, guárdelo para usarlo más adelante en otras aplicaciones.

1. En el método `Main`, cree un [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602). [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) es un método útil para hacer predicciones únicas.

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. Guarde el modelo en un archivo denominado `MLModel.zip`, según lo especificado en la variable `modelPath` definida anteriormente. Use el método [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint%2A) para guardar el modelo.

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a>Uso del modelo para pronosticar la demanda

1. Debajo del método `Evaluate`, cree un método de utilidad denominado `Forecast`.

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. En el método `Forecast`, use el método [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict%2A) para pronosticar los alquileres durante los próximos siete días.

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. Alinee los valores reales y los valores de previsión durante siete períodos.

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. Recorra en iteración la salida del pronóstico y muéstrela en la consola.

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a>Ejecutar la aplicación

1. En el método `Main`, llame al método `Forecast`.

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. Ejecute la aplicación. En la consola debería aparecer una salida similar a la siguiente. Por motivos de brevedad, la salida se ha resumido.

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

La inspección de los valores reales y previstos muestra las relaciones siguientes:

![Comparación de valores reales y valores previstos](./media/time-series-demand-forecasting/forecast.png)

Aunque los valores pronosticados no predicen el número exacto de alquileres, sí proporcionan un intervalo más acotado de valores que permite que una operación optimice el uso de los recursos.

¡Enhorabuena! Creó correctamente un modelo de Machine Learning de serie temporal para predecir la demanda de alquileres de bicicletas.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/Forecasting_BikeSharingDemand).

## <a name="next-steps"></a>Pasos siguientes

- [Tareas de aprendizaje automático en ML.NET](../resources/tasks.md)
- [Mejora de la precisión del modelo](../resources/improve-machine-learning-model-ml-net.md)
