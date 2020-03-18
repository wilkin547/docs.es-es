---
title: 'Tutorial: Predicción de precios mediante regresión con el Generador de modelos'
description: En este tutorial se muestra cómo compilar un modelo de regresión con el Generador de modelos de ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc, mlnet-tooling
ms.openlocfilehash: c027fe57f571c791784b0bdb7ad9503fc49daa1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187695"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a>Tutorial: Predicción de precios mediante regresión con el Generador de modelos

Obtenga información sobre cómo usar el Generador de modelos de ML.NET con el fin de compilar un modelo de regresión para predecir precios.  La aplicación de consola de .NET que desarrolla en este tutorial predice las tarifas de taxi en función de los datos históricos de tarifas de taxi de Nueva York.

La plantilla de predicción de precios del Generador de modelos puede usarse para cualquier escenario que requiera la predicción de un valor numérico. Algunos escenarios de ejemplo son: predicción del precio de la vivienda, predicción de la demanda y previsión de ventas.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Preparar y entender los datos
> - Elección de un escenario
> - Carga de los datos
> - Entrenar el modelo
> - Evaluar el modelo
> - Usar el modelo para las predicciones

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="pre-requisites"></a>Requisitos previos

Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola .NET Core de C#** denominada "TaxiFarePrediction". Asegúrese de que **Colocar la solución y el proyecto en el mismo directorio** está **desactivado** (VS 2019) o que **Crear directorio para la solución** está **activado** (VS 2017).

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Cree un directorio denominado *Datos* en el proyecto para almacenarlos archivos del conjunto de datos.

1. El conjunto de datos que se usa para entrenar y evaluar el modelo de Machine Learning procede originalmente del conjunto de datos NYC TLC Taxi Trip.

    1. Para descargar el conjunto de datos, vaya al [vínculo de descarga de taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).

    1. Cuando se cargue la página, haga clic con el botón derecho en cualquier parte de la página y seleccione **Guardar como**.

    1. Use el **cuadro de diálogo Guardar como** para guardar el archivo en la carpeta *Data* que creó en el paso anterior.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *taxi-fare-train.csv* y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

Cada fila del conjunto de datos `taxi-fare-train.csv` contiene los detalles de los viajes realizados por un taxi.

1. Abra el conjunto de datos **train.csv de taxi y tarifas**.

    El conjunto de datos proporcionado contiene las columnas siguientes:

    - **vendor_id:** el identificador del taxista es una característica.
    - **rate_code:** el tipo de tarifa del viaje en taxi es una característica.
    - **passenger_count:** el número de pasajeros en el recorrido es una característica.
    - **trip_time_in_secs:** la cantidad de tiempo que tardó el viaje. Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine y aún no conoce la duración del viaje, el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.
    - **trip_distance:** la distancia del viaje es una característica.
    - **payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.
    - **fare_amount:** la tarifa de taxi total pagada es la etiqueta.

`label` es la columna que quiere predecir. Al realizar una tarea de regresión, el objetivo es predecir un valor numérico. En este escenario de predicción de precio, se predice el coste de un viaje de taxi. Por lo tanto, **fare_amount** es la etiqueta. Los valores de `features` identificados son las entradas que se proporcionan al modelo para predecir `label`. En este cas, el resto de las columnas, con la excepción de **trip_time_in_secs**, se usan como características o entradas para predecir el importe de la tarifa.

## <a name="choose-a-scenario"></a>Elección de un escenario

Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos. En este caso, el escenario es `Price Prediction`.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Agregar** > **Machine Learning**.
1. En el paso del escenario de la herramienta Generador de modelos, seleccione el escenario *Predicción de precio*.

## <a name="load-the-data"></a>Carga de los datos

El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato .csv o .tsv.

1. En el paso de datos de la herramienta Generador de modelos, seleccione *Archivo* en la lista desplegable origen de datos.
1. Seleccione el botón junto al cuadro de texto *Seleccionar un archivo* y use el Explorador de archivos para examinar y seleccionar *taxi-fare-test.csv* en el directorio *Datos*.
1. Elija *fare_amount* en el menú desplegable *Column to Predict (Label)* (Columna para la predicción [etiqueta]).
1. Expanda la lista desplegable *Input Columns (Features)* (Columnas de entrada [características]) y desactive la columna *trip_time_in_secs* para excluirla como característica durante el entrenamiento.  Vaya al paso de entrenamiento de la herramienta Generador de modelos.

## <a name="train-the-model"></a>Entrenar el modelo

La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la regresión. Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes usando diferentes opciones y algoritmos de regresión para encontrar el modelo con mejor rendimiento para el conjunto de datos.

El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos. El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.

1. Deje el valor predeterminado como está para *Tiempo de entrenamiento (segundos)* , a menos que prefiera entrenar durante más tiempo.
2. Seleccione *Iniciar entrenamiento*.

Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.

- En Estado se muestra el grado de finalización del proceso de entrenamiento.
- En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento. Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.
- En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.
- En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.

Una vez completado el entrenamiento, vaya al paso de evaluación.

## <a name="evaluate-the-model"></a>Evaluar el modelo

El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento. En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada *Mejor modelo* junto con las métricas en *Modelo de mayor calidad (RSquared)* . Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.

Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos. En caso contrario, vaya al paso de código.

## <a name="add-the-code-to-make-predictions"></a>Incorporación del código para hacer predicciones

Se crearán dos proyectos como resultado del proceso de entrenamiento.

- TaxiFarePredictionML.ConsoleApp: Una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de consumo de ejemplo.
- TaxiFarePredictionML.Model: Una biblioteca de clase de .NET Standard que contiene los modelos de datos que definen el esquema de los datos de modelo de entrada y salida, la versión guardada del modelo con mejor rendimiento durante el entrenamiento y una clase auxiliar llamada `ConsumeModel` para hacer predicciones.

1. En el paso de código de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar a la solución los proyectos generados automáticamente.
1. Abra el archivo *Program.cs* en el proyecto *TaxiFarePrediction*.
1. Agregue la instrucción using siguiente para hacer referencia al proyecto *TaxiFarePredictionML.Model*:

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. Para hacer una predicción según los datos nuevos con el modelo, cree una instancia nueva de la clase `ModelInput` dentro del método `Main` de la aplicación. Observe que el importe de la tarifa no forma parte de la entrada. Esto se debe a que el modelo generará la predicción para él.

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. Use el método `Predict` de la clase `ConsumeModel`. El método `Predict` carga el modelo entrenado, crea un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para el modelo y lo usa para realizar predicciones según los datos nuevos.

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. Ejecute la aplicación.

    La salida generada por el programa debe ser similar al siguiente fragmento de código:

    ```bash
    Predicted Fare: 14.96086
    ```

Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Preparar y entender los datos
> - Elección de un escenario
> - Carga de los datos
> - Entrenar el modelo
> - Evaluar el modelo
> - Usar el modelo para las predicciones

### <a name="additional-resources"></a>Recursos adicionales

Para más información sobre los temas mencionados en este tutorial, visite estos recursos:

- [Escenarios del Generador de modelos](../automate-training-with-model-builder.md#scenarios)
- [Regresión](../resources/glossary.md#regression)
- [Métricas de regresión del modelo](../resources/metrics.md#evaluation-metrics-for-regression-and-recommendation)
- [Conjunto de datos NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
