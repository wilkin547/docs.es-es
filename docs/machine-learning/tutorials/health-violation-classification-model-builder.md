---
title: 'Tutorial: Clasificación de infracciones sanitarias con el Generador de modelos'
description: En este tutorial se muestra cómo crear un modelo de clasificación multiclase mediante el Generador de modelos de ML.NET para clasificar la gravedad de infracciones sanitarias en restaurantes de San Francisco.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 6a36989f9453208e436ef8a4db2d4440aa0a1382
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438190"
---
# <a name="tutorial-classify-the-severity-of-restaurant-health-violations-with-model-builder"></a>Tutorial: Clasificación de la gravedad de las infracciones sanitarias en restaurantes con el Generador de modelos

Aprenda a crear un modelo de clasificación multiclase mediante el generador de modelos para categorizar el nivel de riesgo de las infracciones de restaurantes detectadas durante inspecciones sanitarias.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> - Preparar y entender los datos
> - Elección de un escenario
> - Cargar datos desde una base de datos
> - Entrenar el modelo
> - Evaluar el modelo
> - Usar el modelo para las predicciones

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="prerequisites"></a>Requisitos previos

Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).

## <a name="model-builder-multiclass-classification-overview"></a>Información general de clasificación multiclase del Generador de modelos

En este ejemplo se crea una aplicación de consola .NET Core de C# que categoriza el riesgo de las infracciones sanitarias mediante un modelo de aprendizaje automático creado con el Generador de modelos. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) de GitHub.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola .NET Core de C#** denominada "RestaurantViolations". Asegúrese de que **Colocar la solución y el proyecto en el mismo directorio** está **desactivado** (VS 2019) o que **Crear directorio para la solución** está **activado** (VS 2017).

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

> El conjunto de datos que se usa para entrenar y evaluar el modelo de aprendizaje automático proviene originalmente de [San Francisco Department of Public Health Restaurant Safety Scores](https://www.sfdph.org/dph/EH/Food/score/default.asp) (Puntuaciones de seguridad de restaurantes del Departamento de Sanidad Pública de San Francisco). Para mayor comodidad, el conjunto de datos se ha condensado para incluir solo las columnas relevantes a fin de entrenar el modelo y realizar las predicciones. Visite el sitio web siguiente para obtener más información sobre el [conjunto de datos](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i?row_index=0).

[Descargue el conjunto de datos Restaurant Safety Scores](https://github.com/luisquintanilla/machinelearning-samples/raw/AB1608219/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantScores.zip) y descomprímalo.

Cada fila del conjunto de datos contiene información relacionada con las infracciones observadas durante una inspección del Departamento de Sanidad y una evaluación del riesgo de la amenaza de esas infracciones para la salud pública y la seguridad.

| InspectionType | ViolationDescription | RiskCategory |
| --- | --- | --- |
| Rutina: no programada | Superficies de contacto para alimentos limpiadas o desinfectadas incorrectamente | Riesgo moderado |
| Nuevo propietario | Riesgo alto de infestación por parásitos | Riesgo alto |
| Rutina: no programada | Paños de limpieza sucios o incorrectamente almacenados o desinfectados | Riesgo bajo |

- **InspectionType**: el tipo de inspección. Esto puede ser una inspección inicial de un nuevo establecimiento, una inspección rutinaria, una inspección de quejas y otros muchos tipos.
- **ViolationDescription**: descripción de la infracción detectada durante la inspección.
- **RiskCategory**: gravedad del riesgo que supone una infracción para la seguridad y la sanidad pública.

`label` es la columna que quiere predecir. Al realizar una tarea de clasificación, el objetivo es asignar una categoría (de texto o numérica). En este escenario de clasificación, se asigna a la gravedad de la infracción el valor de riesgo bajo, moderado o alto. Por tanto, **RiskCategory** es la etiqueta. Los valores de `features` son las entradas que se proporcionan al modelo para predecir `label`. En este caso, **InspectionType** y **ViolationDescription** se usan como características o entradas para predecir el valor de **RiskCategory**.

## <a name="choose-a-scenario"></a>Elección de un escenario

![Asistente para el generador de modelos en Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Para entrenar el modelo, seleccione en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos. En este caso, el escenario es de *Clasificación de problemas*.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *RestaurantViolations* y seleccione **Agregar** > **Machine Learning**.
1. Para este ejemplo, el escenario es una clasificación multiclase. En el paso *Escenario* del Generador de modelos, seleccione el escenario **Clasificación de problemas**.

## <a name="load-the-data"></a>Carga de los datos

El Generador de modelos acepta datos de una base de datos de SQL Server o un archivo local en formato `csv` o `tsv`.

1. En el paso de datos de la herramienta Generador de modelos, seleccione **SQL Server** en la lista desplegable de origen de datos.
1. Seleccione el botón situado junto al cuadro de texto **Conectarse a la base de datos SQL Server**.
    1. En el cuadro de diálogo **Elegir datos**, seleccione **Archivo de base de datos de Microsoft SQL Server**.
    1. Desactive la casilla **Usar siempre esta selección** y seleccione **Continuar**.
    1. En el cuadro de diálogo **Propiedades de conexión**, seleccione **Examinar** y después el archivo *RestaurantScores.mdf* descargado.
    1. Seleccione **Aceptar**.
1. Elija **Violations** (Infracciones) en el menú desplegable **Table Name** (Nombre de la tabla).
1. Elija **RiskCategory** en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).
1. Deje las selecciones de columna predeterminadas, **InspectionType** y **ViolationDescription**,activadas en la lista desplegable **Input Columns (Features)** (Columnas de entrada (características)).
1. Seleccione el vínculo **Entrenar** para ir al paso siguiente en el Generador de modelos.

## <a name="train-the-model"></a>Entrenar el modelo

La tarea de aprendizaje automático que se usa para entrenar el modelo de clasificación de problemas de este tutorial es la clasificación multiclase. Durante el proceso de entrenamiento del modelo, el Generador de modelos entrena modelos independientes con diferentes opciones y algoritmos de clasificación multiclase para encontrar el modelo con mejor rendimiento para el conjunto de datos.

El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos. El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.

1. Aunque el Generador de modelos establezca el valor de **Tiempo de entrenamiento (segundos)** en 10 segundos, debe aumentarlo a 30 segundos. El entrenamiento durante un período de tiempo más prolongado permite que el Generador de modelos explore un mayor número de algoritmos y combinación de parámetros en la búsqueda del mejor modelo.
1. Seleccione **Iniciar entrenamiento**.

    Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.

    - En **Estado** se muestra el grado de finalización del proceso de entrenamiento.
    - En **Mejor precisión** se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento. Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.
    - En **Mejor algoritmo** se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.
    - En **Último algoritmo** se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.

1. Una vez que se ha completado el entrenamiento, seleccione el vínculo de **evaluación** para ir al paso siguiente.

## <a name="evaluate-the-model"></a>Evaluar el modelo

El resultado del paso de entrenamiento es el modelo que ha tenido el mejor rendimiento. En el paso de evaluación del Generador de modelos, la sección de salida contiene el algoritmo usado por el modelo con el mejor rendimiento en la entrada **Mejor modelo** junto con las métricas en **Modelo de mayor precisión**. Además, se muestra una tabla de resumen que contiene hasta cinco modelos que se han explorado y sus métricas.

Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos. En caso contrario, seleccione el vínculo de **código** para ir al paso final del Generador de modelos.

## <a name="add-the-code-to-make-predictions"></a>Incorporación del código para hacer predicciones

Como resultado del proceso de entrenamiento se crean dos proyectos.

- RestaurantViolationsML.ConsoleApp: una aplicación de consola .NET Core de C# que contiene el entrenamiento del modelo y código de consumo de ejemplo.
- RestaurantViolationsML.Model: una biblioteca de clases de .NET Standard que contiene los modelos de datos que definen el esquema de los datos de modelo de entrada y salida, la versión guardada del modelo con mejor rendimiento durante el entrenamiento y una clase auxiliar llamada `ConsumeModel` para realizar predicciones.

1. En el paso de código del Generador de modelos, seleccione **Agregar proyectos** para agregar a la solución los proyectos generados de forma automática.
1. Abra el archivo *Program.cs* en el proyecto *RestaurantViolations*.
1. Agregue la instrucción using siguiente para hacer referencia al proyecto *RestaurantViolationsML.Model*:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L2)]

1. Para hacer una predicción según los datos nuevos con el modelo, cree una instancia nueva de la clase `ModelInput` dentro del método `Main` de la aplicación. Observe que la categoría de riesgo no forma parte de la entrada. Esto se debe a que el modelo genera la predicción para ella.

    [!code-csharp [TestData](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L11-L15)]

1. Use el método `Predict` de la clase `ConsumeModel`. El método `Predict` carga el modelo entrenado, crea un objeto [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para el modelo y lo usa para realizar predicciones sobre los datos nuevos.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L17-L24)]

1. Ejecute la aplicación.

    La salida generada por el programa debe ser similar al siguiente fragmento de código:

    ```bash
    Inspection Type: Complaint
    Violation Description: Inadequate sewage or wastewater disposal
    Risk Category: Moderate Risk
    ```

Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

¡Enhorabuena! Ha creado correctamente un modelo de aprendizaje automático para categorizar el riesgo de infracciones sanitarias mediante el Generador de modelos. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) de GitHub.

## <a name="additional-resources"></a>Recursos adicionales

Para más información sobre los temas mencionados en este tutorial, visite estos recursos:

- [Escenarios del Generador de modelos](../automate-training-with-model-builder.md#scenario)
- [Clasificación multiclase](../resources/glossary.md#multiclass-classification)
- [Métricas de modelos de clasificación multiclase](../resources/metrics.md#evaluation-metrics-for-multi-class-classification)
