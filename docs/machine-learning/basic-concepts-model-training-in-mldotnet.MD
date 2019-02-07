---
title: Conceptos básicos del entrenamiento de modelos en ML.NET
description: En este artículo se explican los conceptos básicos que tratan los escenarios de *entrenamiento de modelos* en ML.NET. No todos los conceptos son pertinentes para el escenario más sencillo de *predicción con el modelo existente*.
ms.date: 11/06/2018
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: cff833b45583bc752bb42616820a95ca6c5c6b12
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "55252444"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a>Conceptos básicos del entrenamiento de modelos en ML.NET

En este artículo se explican los conceptos básicos que tratan los escenarios de *entrenamiento de modelos* en ML.NET. No todos los conceptos son pertinentes para el escenario más sencillo de *predicción con el modelo existente*.

## <a name="model-training-concepts"></a>Conceptos de entrenamiento de modelos

Este documento trata los siguientes conceptos relacionados con el entrenamiento de modelos en ML.NET:

- [*Datos*](#data) representados como una interfaz `IDataView`.
  - En ML.NET, los datos son similares a una vista SQL: es un conjunto de datos evaluados de forma diferida, inmutables, sobre los que puede colocarse el cursor, heterogéneos y esquematizados. 
  - Un documento excelente sobre la interfaz de datos es [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principios de diseño de IDataView).
- [*Transformer*](#transformer) representado como interfaz `ITransformer`.
  - Transformer es un componente que toma datos, trabaja con ellos y devuelve nuevos datos transformados.
  - Por ejemplo, puede pensar en un modelo de Machine Learning como un componente Transformer que toma características y devuelve predicciones.
  - Otro ejemplo, el tokenizador de texto toma una sola columna de texto y genera una columna de vector con palabras individuales extraídas de los textos.
- [*Lector de datos*](#data-reader) representado como una interfaz `IDataReader<T>`.
  - El lector de datos es el componente ML.NET para crear datos. Toma una instancia de `T` y devuelve datos fuera de esta. 
  - Por ejemplo, un *TextLoader* es un `IDataReader<FileSource>`. Toma el origen del archivo y produce datos. 
- [*Estimador*](#estimator) representado como una interfaz `IEstimator<T>`.
  - Se trata de un objeto que aprende de los datos. El resultado del aprendizaje es un componente *Transformer*.
  - Puede pensar en un *algoritmo* de Machine Learning como un estimador que aprende de los datos y produce un *modelo* de Machine Learning.
- [*Función de predicción*](#prediction-function) representada como una clase `PredictionFunction<TSrc, TDst>`.
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

La mayoría de los componentes Transformer de ML.NET tienden a funcionar en una *columna de entrada* a la vez y producen la *columna de salida*. Por ejemplo, un `new HashTransformer("foo", "bar")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los pone en la columna "bar". 

También es habitual que los nombres de columnas de entrada y salida sean los mismos. En este caso, la columna antigua se reemplaza por la nueva. Por ejemplo, un `new HashTransformer("foo")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los vuelve a poner en "foo". 

Cualquier componente Transformer, por supuesto, produce una nueva vista de datos al llamarse a `Transform`. Recuerde, las vistas de datos son inmutables.

Otra consideración importante es que, debido a que los datos se evalúan de forma diferida, los *componentes Transformer también son diferidos*. En esencia, tras su llamada,

```csharp
var newData = transformer.Transform(oldData)
```

no se produce ningún cálculo real. Solo una vez que obtiene un cursor de `newData` y empieza a utilizar el valor, `newData` invocan la lógica de transformación `transformer` (y aun cuando solamente el `transformer` en cuestión sea necesario para producir las columnas solicitadas).

### <a name="transformer-chains"></a>Cadenas de Transformer

Una propiedad útil de un componente Transformer es que *puede formular una aplicación secuencial de componentes Transformer como otro componente Transformer*:

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

Esta propiedad se suele usar en ML.NET: normalmente, el modelo ML.NET entrenado es una cadena de componentes Transformer, es decir, a todos los efectos, un componente *Transformer*. 

## <a name="data-reader"></a>Lector de datos

El lector de datos es el componente ML.NET para "crear" datos: toma una instancia de `T` y devuelve datos fuera de esta.

Una propiedad interesante a tener en cuenta es que puede crear un lector de datos asociando un componente Transformer a un lector de datos existente. De esta forma puede tener un lector con comportamiento de transformación a la carta:

```c#
var newReader = reader.Append(transformer1).Append(transformer2)
```

Otra similitud con los componentes Transformer es que, puesto que los datos se evalúan de forma diferida, *los lectores son diferidos*: no se produce ninguna "lectura" real (o mínima) al llamar a `dataReader.Read()`: solo al solicitarse un cursor en los datos resultantes, el lector empieza a funcionar.

## <a name="estimator"></a>Estimador

El *estimador* es un objeto que aprende de los datos. El resultado del aprendizaje es un componente *Transformer*.

En ML.NET, use esta propiedad para crear canalizaciones de aprendizaje que encadenen diferentes estimadores:

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = new CopyColumnsEstimator(mlContext, "FareAmount", "Label")
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "VendorId"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "RateCode"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "PaymentType"))
.Append(new ColumnConcatenatingEstimator(mlContext, "Features", "VendorId", "RateCode", "PassengerCount", "TripTime", "TripDistance", "PaymentType"))
.Append(mlContext.Regression.Trainers.FastTree("Label", "Features"));

var model = pipeline.Fit(dataView);
```

Una propiedad importante de los estimadores es que los *estimadores son diligentes, no diferidos*: todas las llamadas a `Fit` están haciendo que se produzca el aprendizaje, lo que es posiblemente una operación que demanda mucho tiempo.

## <a name="prediction-function"></a>Función de predicción

La función de predicción se puede ver como una máquina que aplica un componente Transformer a una fila.

Una vez que obtenga el modelo (un componente *Transformer* entrenado a través de `Fit()` o cargado desde algún lugar), puede usarlo para realizar predicciones con las llamadas normales a `model.Transform(data)`. Sin embargo, cuando usa este modelo en un escenario de la vida real, no suele contar con muchos ejemplos sobre los que predecir. En su lugar, tiene un ejemplo a la vez y debe realizar predicciones puntuales sobre ellos inmediatamente.

Por supuesto, puede reducir esto a la predicción por lotes:

- Cree una vista de datos con una fila exactamente.
- Llame a `model.Transform(data)` para obtener la vista de datos prevista.
- Obtenga un cursor a través de los datos resultantes.
- Avance un paso con el cursor para obtener acceso a la primera (y única) fila.
- Extraiga los valores previstos de ella.

El algoritmo anterior se puede implementar mediante la [comprensión de esquema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con dos objetos `InputExample` y `OutputPrediction` definidos por el usuario de la siguiente manera:

```c#
var inputData = env.CreateDataView(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = outputData.AsDynamic.AsEnumerable<OutputPrediction>(env, reuseRowObject: false).Single();
```

Pero esto es complicado e implica costos de rendimiento.  En su lugar, un objeto de función de predicción realiza el mismo trabajo, pero de forma más rápida y adecuada, a través de un método de extensión `MakePredictionFunction`:

```c#
var predictionFunc = model.MakePredictionFunction<InputExample, OutputPrediction>(env);
var output = predictionFunc.Predict(example);
```

La función de predicción *no es reentrante / es segura para subprocesos*. Si desea realizar predicciones simultáneamente con varios subprocesos, debe tener una función de predicción por subproceso.
