---
title: Tareas de aprendizaje automático
description: Explore las diferentes tareas de aprendizaje automático admitidas en ML.NET.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 22249ac2d275a4168dbd8b03b90d9698fe90f2d1
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34860700"
---
# <a name="machine-learning-tasks"></a>Tareas de aprendizaje automático

Cuando se crea un modelo de aprendizaje automático, primero debe definir lo que espera lograr con sus datos. Después, puede elegir la tarea de aprendizaje automático adecuada para su situación. La siguiente lista describe las diferentes tareas de aprendizaje automático que puede elegir y algunos casos de uso comunes. 

> [!NOTE]
> ML.NET se encuentra actualmente en versión preliminar. No todas las tareas de aprendizaje automático se admiten actualmente. Para enviar una solicitud para una tarea determinada, abra un tema en el [repositorio dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

> [!NOTE]
> Actualmente, ML.NET no admite tareas de aprendizaje automático con imágenes. Se agregará esta compatibilidad en futuras versiones. 

## <a name="binary-classification"></a>Clasificación binaria

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1. El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación binaria están los siguientes:

* [Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".
* Diagnosticar si un paciente tiene una determinada enfermedad o no.
* Tomar una decisión para marcar un correo electrónico como no deseado o no.

## <a name="multi-class-classification"></a>Clasificación multiclase

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta. Cada etiqueta es un número entero entre 0 y k-1, donde k es el número de clases. El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:

* Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.
* Comprender las críticas de películas como "positivas", "neutrales" o "negativas".
* Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.

## <a name="regression"></a>Regresión

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas. La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación. Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características. La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos. El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada. Estos son algunos ejemplos de escenarios de regresión:

* Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.
* Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.
* Predecir las ventas de un producto en función del presupuesto para publicidad.

> [!NOTE]
> Actualmente, ML.NET aún está generando la compatibilidad para tareas de regresión que implican series temporales.

## <a name="clustering"></a>Agrupación en clústeres

Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares. La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación. Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida. Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad. ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means. Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:

* Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.
* Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.
* Categorizar un inventario tomando como base las métricas de fabricación.

## <a name="anomaly-detection-coming-soon"></a>Detección de anomalías (*próximamente*)

## <a name="ranking-coming-soon"></a>Clasificación por orden de prioridad (*próximamente*)

## <a name="recommendation-coming-soon"></a>Recomendación (*próximamente*)

