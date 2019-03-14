---
title: Conceptos básicos del entrenamiento de modelos en ML.NET
description: En este artículo se explican los conceptos básicos que tratan los escenarios de *entrenamiento de modelos* en ML.NET. No todos los conceptos son pertinentes para el escenario más sencillo de *predicción con el modelo existente*.
ms.date: 03/05/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 78554cfd1dfdb3dba82a325d47245aeb313bb6fe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675568"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a>Conceptos básicos del entrenamiento de modelos en ML.NET

En este artículo se explican los conceptos básicos que tratan los escenarios de *entrenamiento de modelos* en ML.NET. No todos los conceptos son pertinentes para el escenario más sencillo de *predicción con un modelo existente*.

Este artículo y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="model-training-concepts"></a>Conceptos de entrenamiento de modelos

Este documento trata los siguientes conceptos relacionados con el entrenamiento de modelos en ML.NET:

- [*Datos*](#data) representados como una interfaz `IDataView`.
  - En ML.NET, los datos son similares a una vista SQL: es un conjunto de datos evaluados de forma diferida, inmutables, sobre los que puede colocarse el cursor, heterogéneos y esquematizados. 
  - Un documento excelente sobre la interfaz de datos es [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principios de diseño de IDataView).
- [*Transformer*](#transformer) representado como interfaz `ITransformer`.
  - Transformer es un componente que toma datos, trabaja con ellos y devuelve nuevos datos transformados.
  - Por ejemplo, puede pensar en un modelo de Machine Learning como un componente Transformer que toma características y devuelve predicciones.
  - Otro ejemplo: el tokenizador de texto toma una sola columna de texto y genera una columna de vector con palabras individuales extraídas de los textos.
- [*Lector de datos*](#data-reader) representado como una interfaz `IDataReader<T>`.
  - El lector de datos es el componente ML.NET para crear datos. Toma una instancia de `T` y devuelve datos fuera de esta. 
  - Por ejemplo, un *TextLoader* es un `IDataReader<IMultiStreamSource>`. Toma el origen y genera datos. 
- [*Estimador*](#estimator) representado como una interfaz `IEstimator<T>`.
  - Se trata de un objeto que aprende de los datos. El resultado del aprendizaje es un componente *Transformer*.
  - Puede pensar en un *algoritmo* de Machine Learning como un estimador que aprende de los datos y produce un *modelo* de Machine Learning.
- [*Función de predicción*](#prediction-function) representada como una clase `PredictionEngine<TSrc, TDst>`.
  - La función de predicción se puede ver como una máquina que aplica un componente Transformer a una fila, como en tiempo de predicción.

## <a name="data"></a>Datos

En ML.NET, los datos son similares a una vista SQL: es un conjunto de datos evaluados de forma diferida, sobre los que puede colocarse el cursor, heterogéneos y esquematizados.

- Tiene *Esquema* (una instancia de una interfaz `ISchema`) que contiene la información sobre las columnas de la vista de datos.
  - Cada columna tiene un *Nombre*, un *Tipo* y un conjunto arbitrario de *metadatos* asociados a ella.
  - Los *metadatos* de la columna contienen información como los nombres de ranura de una columna de vector y similares. Los propios metadatos se representan como otros *datos* de una fila que son únicos para cada columna.
  - La vista de datos es un origen de *cursores*. Cursores de SQL de reflexión: Un cursor es un objeto que procesa una iteración en los datos, una fila a la vez y presenta los datos disponibles.
  - Naturalmente, los datos pueden tener tantos cursores activos sobre ellos como sean necesarios. Como los propios datos son inmutables, los cursores son realmente independientes.
  - Los cursores suelen tener acceso únicamente a un subconjunto de columnas: Para lograr eficiencia, ML.NET calcula solo los valores de columnas que necesita el cursor.

## <a name="transformer"></a>Transformer

Transformer es un componente que toma datos, trabaja con ellos y devuelve nuevos datos transformados.

La mayoría de los componentes Transformer de ML.NET tienden a funcionar en una *columna de entrada* a la vez y producen la *columna de salida*. Por ejemplo, un elemento `new HashTransformer("bar", "foo")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los pone en la columna "bar". 

También es habitual que los nombres de columnas de entrada y salida sean los mismos. En este caso, la columna antigua se reemplaza por la nueva. Por ejemplo, un elemento `new HashTransformer("foo")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los vuelve a poner en "foo". 

Cualquier transformador genera una vista de datos nueva cuando se llama a `Transform`. Recuerde, las vistas de datos son inmutables.

Otra consideración importante es que, debido a que los datos se evalúan de forma diferida, los *componentes Transformer también son diferidos*. En esencia, tras su llamada,

```csharp
var newData = transformer.Transform(oldData)
```

no se produce ningún cálculo real. Solo después de obtener un cursor de `newData` y empezar a usar el valor, `newData` invoca la lógica de transformación `transformer` (e incluso entonces, solo cuando el elemento `transformer` en cuestión es necesario para generar las columnas solicitadas).

### <a name="transformer-chains"></a>Cadenas de Transformer

Una propiedad útil de un componente Transformer es que *puede compilar una aplicación secuencial de componentes Transformer como otro componente Transformer*:

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

Esta propiedad se suele usar en ML.NET: normalmente, el modelo ML.NET entrenado es una cadena de componentes Transformer, es decir, a todos los efectos, un componente *Transformer*.

## <a name="data-reader"></a>Lector de datos

El lector de datos es un componente de ML.NET para "crear" datos: toma una instancia de `T` y devuelve datos fuera de esta.

Una propiedad interesante a tener en cuenta es que puede crear un lector de datos asociando un componente Transformer a un lector de datos existente. De esta forma puede tener un lector con comportamiento de transformación a la carta:

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

Otra similitud con los componentes Transformer es que, puesto que los datos se evalúan de forma diferida, *los lectores son diferidos*: no se produce ninguna "lectura" real (o mínima) al llamar a `reader.Read()`: solo al solicitarse un cursor en los datos resultantes, el lector empieza a funcionar.

## <a name="estimator"></a>Estimador

El *estimador* es un objeto que aprende de los datos. El resultado del aprendizaje es un componente *Transformer*.

En ML.NET, use esta propiedad para crear canalizaciones de aprendizaje que encadenen diferentes estimadores:

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

Una propiedad importante de los estimadores es que los *estimadores son diligentes, no diferidos*: todas las llamadas a `Fit` están haciendo que se produzca el aprendizaje, lo que es posiblemente una operación que demanda mucho tiempo.

## <a name="prediction-function"></a>Función de predicción

La función de predicción se puede ver como un componente que aplica un componente Transformer a una fila.

Una vez que obtenga el modelo (un componente *Transformer* entrenado a través de `Fit()` o cargado desde algún lugar), puede usarlo para realizar predicciones con las llamadas normales a `model.Transform(data)`. Sin embargo, cuando usa este modelo en un escenario de la vida real, no suele contar con muchos ejemplos sobre los que predecir. En su lugar, tiene un ejemplo a la vez y debe realizar predicciones puntuales sobre ellos inmediatamente.

Por supuesto, puede reducir esto a la predicción por lotes:

- Cree una vista de datos con una fila exactamente.
- Llame a `model.Transform(data)` para obtener la vista de datos prevista.
- Obtenga un cursor a través de los datos resultantes.
- Avance un paso con el cursor para obtener acceso a la primera (y única) fila.
- Extraiga los valores previstos de ella.

El algoritmo anterior se puede implementar mediante la [comprensión de esquema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con dos objetos `InputExample` y `OutputPrediction` definidos por el usuario de la siguiente manera:

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

Pero esto es complicado e implica costos de rendimiento.  En su lugar, un objeto de función de predicción realiza el mismo trabajo, pero de forma más rápida y adecuada, a través de un método de extensión `CreatePredictionEngine`:

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

La función de predicción *no es reentrante / es segura para subprocesos*. Si desea realizar predicciones simultáneamente con varios subprocesos, debe tener una función de predicción por subproceso.
