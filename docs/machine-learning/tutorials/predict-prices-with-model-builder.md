---
title: Predicción de precios mediante regresión con el Generador de modelos
description: En este tutorial se muestra cómo compilar un modelo de regresión con el Generador de modelos de ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d9a6f193d877fc1a679b7a3cafd7491e021cb2ad
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539632"
---
# <a name="predict-prices-using-regression-with-model-builder"></a>Predicción de precios mediante regresión con el Generador de modelos

Obtenga información sobre cómo usar el Generador de modelos de ML.NET para crear un [modelo de regresión](../resources/glossary.md#regression) para predecir precios.  La aplicación de consola de .NET que desarrolla en este tutorial predice las tarifas de taxi en función de los datos históricos de tarifas de taxi de Nueva York.

La plantilla de predicción de precios del Generador de modelos puede usarse para cualquier escenario que requiera la predicción de un valor numérico. Algunos escenarios de ejemplo son: predicción del precio de la vivienda, predicción de la demanda y previsión de ventas.

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Preparar y entender los datos
> * Elección de un escenario
> * Carga de los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Usar el modelo para las predicciones

> [!NOTE]
> El Generador de modelos se encuentra en versión preliminar.

## <a name="pre-requisites"></a>Requisitos previos

Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core** denominada "TaxiFarePrediction".

1. Instale el paquete NuGet **Microsoft.ML**:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Cree un directorio denominado *Datos* en el proyecto para almacenarlos archivos del conjunto de datos.

1. Descargue el conjunto de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior. Este conjunto de datos se usa para entrenar y evaluar el modelo de aprendizaje automático. Este conjunto de datos procede originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *taxi-fare-train.csv* y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

Cada fila del conjunto de datos `taxi-fare-train.csv` contiene los detalles de los viajes realizados por un taxi.

1. Abra el conjunto de datos **train.csv de taxi y tarifas**.

    El conjunto de datos proporcionado contiene las columnas siguientes:

    * **vendor_id:** el identificador del taxista es una característica.
    * **rate_code:** el tipo de tarifa del viaje en taxi es una característica.
    * **passenger_count:** el número de pasajeros en el recorrido es una característica.
    * **trip_time_in_secs:** la cantidad de tiempo que tardó el viaje. Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine y aún no conoce la duración del viaje, el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.
    * **trip_distance:** la distancia del viaje es una característica.
    * **payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.
    * **fare_amount:** la tarifa de taxi total pagada es la etiqueta.

`label` es la columna que quiere predecir. Al realizar una tarea de regresión, el objetivo es predecir un valor numérico. En este escenario de predicción de precio, se predice el coste de un viaje de taxi. Por lo tanto, **fare_amount** es la etiqueta. Los valores de `features` identificados son las entradas que se proporcionan al modelo para predecir `label`. En este caso, el resto de columnas se usan como entradas o características para predecir el importe de la tarifa.

## <a name="choose-a-scenario"></a>Elección de un escenario

Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos. En este caso, el escenario es `Price Prediction`. Para obtener una lista más amplia, visite el [artículo de información general del Generador de modelos](../automate-training-with-model-builder.md#scenarios).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Agregar** > **Machine Learning**.
1. En el paso del escenario de la herramienta Generador de modelos, seleccione el escenario *Predicción de precio*.

## <a name="load-the-data"></a>Carga de los datos

El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local csv o tsv. Para obtener más información sobre los requisitos de formato de datos, visite el siguiente [vínculo](../how-to-guides/install-model-builder.md#limitations).

1. En el paso de datos de la herramienta Generador de modelos, seleccione *Archivo* en la lista desplegable origen de datos.
1. Seleccione el botón junto al cuadro de texto *Seleccionar un archivo* y use el Explorador de archivos para examinar y seleccionar *taxi-fare-test.csv* en el directorio *Datos*.
1. Elija *fare_amount* en la lista desplegable *Etiqueta o columna para la predicción* y vaya al paso de entrenamiento de la herramienta Generador de modelos.

## <a name="train-the-model"></a>Entrenar el modelo

La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la regresión. Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes usando diferentes opciones y algoritmos de regresión para encontrar el modelo con mejor rendimiento para el conjunto de datos.

El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos. Use este gráfico como guía para seleccionar un valor adecuado para el campo `Time to train (seconds)`:

*Tamaño del conjunto de datos  | Tipo de conjunto de datos       | Prom. Tiempo de entrenamiento*
------------- | ------------------ | --------------
0 - 10 MB     | Numérico y texto   | 10 s
10 - 100 MB   | Numérico y texto   | 10 min
100 - 500 MB  | Numérico y texto   | 30 min
500 - 1 GB    | Numérico y texto   | 60 min
1 GB o más         | Numérico y texto   | Más de 3 horas

1. Dado que el archivo de datos de entrenamiento es mayor de 10 MB, use 600 segundos (10 minutos) como valor en *Tiempo para entrenar (segundos)* .
2. Seleccione *Iniciar entrenamiento*.

Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.

- En Estado se muestra el grado de finalización del proceso de entrenamiento.
- En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento. Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.
- En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.
- En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.

Una vez completado el entrenamiento, vaya al paso de evaluación.

## <a name="evaluate-the-model"></a>Evaluar el modelo

El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento. En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada *Mejor modelo* junto con las métricas en *Modelo de mayor calidad (RSquared)* . Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas. Visite el vínculo siguiente para obtener más información sobre las [métricas de evaluación de modelos](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).

Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

Se crearán dos proyectos como resultado del proceso de entrenamiento.

- TaxiFarePredictionML.ConsoleApp: Una aplicación de consola de .NET que contiene el entrenamiento del modelo y el código de consumo.
- TaxiFarePredictionML.Model: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión persistente del modelo con mejor rendimiento durante el entrenamiento.

1. En la sección de código de la herramienta Generador de modelos, seleccione **Proyectos agregados** para agregar los proyectos a la solución.
2. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto *TaxiFarePrediction*. A continuación, seleccione **Agregar > Elemento existente**. Para la lista desplegable de tipos de archivo, seleccione `All Files`, vaya hasta el directorio del proyecto *TaxiFarePredictionML.Model* y seleccione el archivo `MLModel.zip`. A continuación, haga clic con el botón derecho en el archivo agregado recientemente `MLModel.zip` y seleccione *Propiedades*. Para la opción Copiar en el directorio de resultados, seleccione *Copiar si es más reciente* en la lista desplegable.
3. Haga clic con el botón derecho en el proyecto *TaxiFarePrediction*. A continuación, **Agregar > Referencia**. Elija el nodo **Proyectos > Solución** y, en la lista, marque el proyecto *TaxiFarePredictionML.Model* y haga clic en Aceptar.

4. Abra el archivo *Program.cs* en el proyecto *TaxiFarePrediction*.
5. Agregue las siguientes instrucciones using:

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. Agregue el método `ConsumeModel` a la clase `Program`. `ConsumeModel` creará un `PredictionEngine` según el modelo generado por el Generador de modelos para realizar predicciones sobre nuevos datos y los imprimirá en la consola.

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. Agregue el siguiente código al método `Main` y ejecute la aplicación.

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    La salida generada por el programa debe ser similar al siguiente fragmento de código:

    ```bash
    Predicted Fare: 16.82245
    ```

Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Preparar y entender los datos
> * Elección de un escenario
> * Carga de los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Usar el modelo para las predicciones

Vaya a cualquiera de los siguientes artículos de procedimientos para aprender a implementar el modelo.

> [!div class="nextstepaction"]
> [Implementación de un modelo en Azure Functions](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [Implementación de un modelo en una API Web](../how-to-guides/serve-model-web-api-ml-net.md)
