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
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="c48b6-104">Conceptos básicos del entrenamiento de modelos en ML.NET</span><span class="sxs-lookup"><span data-stu-id="c48b6-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="c48b6-105">En este artículo se explican los conceptos básicos que tratan los escenarios de *entrenamiento de modelos* en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c48b6-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="c48b6-106">No todos los conceptos son pertinentes para el escenario más sencillo de *predicción con un modelo existente*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

<span data-ttu-id="c48b6-107">Este artículo y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="c48b6-107">This article and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="c48b6-108">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="c48b6-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="c48b6-109">Conceptos de entrenamiento de modelos</span><span class="sxs-lookup"><span data-stu-id="c48b6-109">Model training concepts</span></span>

<span data-ttu-id="c48b6-110">Este documento trata los siguientes conceptos relacionados con el entrenamiento de modelos en ML.NET:</span><span class="sxs-lookup"><span data-stu-id="c48b6-110">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="c48b6-111">[*Datos*](#data) representados como una interfaz `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-111">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="c48b6-112">En ML.NET, los datos son similares a una vista SQL: es un conjunto de datos evaluados de forma diferida, inmutables, sobre los que puede colocarse el cursor, heterogéneos y esquematizados.</span><span class="sxs-lookup"><span data-stu-id="c48b6-112">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="c48b6-113">Un documento excelente sobre la interfaz de datos es [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principios de diseño de IDataView).</span><span class="sxs-lookup"><span data-stu-id="c48b6-113">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="c48b6-114">[*Transformer*](#transformer) representado como interfaz `ITransformer`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-114">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="c48b6-115">Transformer es un componente que toma datos, trabaja con ellos y devuelve nuevos datos transformados.</span><span class="sxs-lookup"><span data-stu-id="c48b6-115">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="c48b6-116">Por ejemplo, puede pensar en un modelo de Machine Learning como un componente Transformer que toma características y devuelve predicciones.</span><span class="sxs-lookup"><span data-stu-id="c48b6-116">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="c48b6-117">Otro ejemplo: el tokenizador de texto toma una sola columna de texto y genera una columna de vector con palabras individuales extraídas de los textos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-117">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="c48b6-118">[*Lector de datos*](#data-reader) representado como una interfaz `IDataReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-118">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="c48b6-119">El lector de datos es el componente ML.NET para crear datos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-119">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="c48b6-120">Toma una instancia de `T` y devuelve datos fuera de esta.</span><span class="sxs-lookup"><span data-stu-id="c48b6-120">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="c48b6-121">Por ejemplo, un *TextLoader* es un `IDataReader<IMultiStreamSource>`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-121">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="c48b6-122">Toma el origen y genera datos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-122">It takes the source and produces data.</span></span> 
- <span data-ttu-id="c48b6-123">[*Estimador*](#estimator) representado como una interfaz `IEstimator<T>`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-123">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="c48b6-124">Se trata de un objeto que aprende de los datos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-124">This is an object that learns from data.</span></span> <span data-ttu-id="c48b6-125">El resultado del aprendizaje es un componente *Transformer*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-125">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="c48b6-126">Puede pensar en un *algoritmo* de Machine Learning como un estimador que aprende de los datos y produce un *modelo* de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="c48b6-126">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="c48b6-127">[*Función de predicción*](#prediction-function) representada como una clase `PredictionEngine<TSrc, TDst>`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-127">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="c48b6-128">La función de predicción se puede ver como una máquina que aplica un componente Transformer a una fila, como en tiempo de predicción.</span><span class="sxs-lookup"><span data-stu-id="c48b6-128">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="c48b6-129">Datos</span><span class="sxs-lookup"><span data-stu-id="c48b6-129">Data</span></span>

<span data-ttu-id="c48b6-130">En ML.NET, los datos son similares a una vista SQL: es un conjunto de datos evaluados de forma diferida, sobre los que puede colocarse el cursor, heterogéneos y esquematizados.</span><span class="sxs-lookup"><span data-stu-id="c48b6-130">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="c48b6-131">Tiene *Esquema* (una instancia de una interfaz `ISchema`) que contiene la información sobre las columnas de la vista de datos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-131">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="c48b6-132">Cada columna tiene un *Nombre*, un *Tipo* y un conjunto arbitrario de *metadatos* asociados a ella.</span><span class="sxs-lookup"><span data-stu-id="c48b6-132">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="c48b6-133">Los *metadatos* de la columna contienen información como los nombres de ranura de una columna de vector y similares.</span><span class="sxs-lookup"><span data-stu-id="c48b6-133">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="c48b6-134">Los propios metadatos se representan como otros *datos* de una fila que son únicos para cada columna.</span><span class="sxs-lookup"><span data-stu-id="c48b6-134">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="c48b6-135">La vista de datos es un origen de *cursores*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-135">The data view is a source of *cursors*.</span></span> <span data-ttu-id="c48b6-136">Cursores de SQL de reflexión: Un cursor es un objeto que procesa una iteración en los datos, una fila a la vez y presenta los datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c48b6-136">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="c48b6-137">Naturalmente, los datos pueden tener tantos cursores activos sobre ellos como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="c48b6-137">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="c48b6-138">Como los propios datos son inmutables, los cursores son realmente independientes.</span><span class="sxs-lookup"><span data-stu-id="c48b6-138">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="c48b6-139">Los cursores suelen tener acceso únicamente a un subconjunto de columnas: Para lograr eficiencia, ML.NET calcula solo los valores de columnas que necesita el cursor.</span><span class="sxs-lookup"><span data-stu-id="c48b6-139">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="c48b6-140">Transformer</span><span class="sxs-lookup"><span data-stu-id="c48b6-140">Transformer</span></span>

<span data-ttu-id="c48b6-141">Transformer es un componente que toma datos, trabaja con ellos y devuelve nuevos datos transformados.</span><span class="sxs-lookup"><span data-stu-id="c48b6-141">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="c48b6-142">La mayoría de los componentes Transformer de ML.NET tienden a funcionar en una *columna de entrada* a la vez y producen la *columna de salida*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-142">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="c48b6-143">Por ejemplo, un elemento `new HashTransformer("bar", "foo")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los pone en la columna "bar".</span><span class="sxs-lookup"><span data-stu-id="c48b6-143">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="c48b6-144">También es habitual que los nombres de columnas de entrada y salida sean los mismos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-144">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="c48b6-145">En este caso, la columna antigua se reemplaza por la nueva.</span><span class="sxs-lookup"><span data-stu-id="c48b6-145">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="c48b6-146">Por ejemplo, un elemento `new HashTransformer("foo")` toma los valores de la columna "foo", usa algoritmos hash en ellos y los vuelve a poner en "foo".</span><span class="sxs-lookup"><span data-stu-id="c48b6-146">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="c48b6-147">Cualquier transformador genera una vista de datos nueva cuando se llama a `Transform`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-147">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="c48b6-148">Recuerde, las vistas de datos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="c48b6-148">Remember, data views are immutable.</span></span>

<span data-ttu-id="c48b6-149">Otra consideración importante es que, debido a que los datos se evalúan de forma diferida, los *componentes Transformer también son diferidos*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-149">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="c48b6-150">En esencia, tras su llamada,</span><span class="sxs-lookup"><span data-stu-id="c48b6-150">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="c48b6-151">no se produce ningún cálculo real.</span><span class="sxs-lookup"><span data-stu-id="c48b6-151">no actual computation happens.</span></span> <span data-ttu-id="c48b6-152">Solo después de obtener un cursor de `newData` y empezar a usar el valor, `newData` invoca la lógica de transformación `transformer` (e incluso entonces, solo cuando el elemento `transformer` en cuestión es necesario para generar las columnas solicitadas).</span><span class="sxs-lookup"><span data-stu-id="c48b6-152">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="c48b6-153">Cadenas de Transformer</span><span class="sxs-lookup"><span data-stu-id="c48b6-153">Transformer chains</span></span>

<span data-ttu-id="c48b6-154">Una propiedad útil de un componente Transformer es que *puede compilar una aplicación secuencial de componentes Transformer como otro componente Transformer*:</span><span class="sxs-lookup"><span data-stu-id="c48b6-154">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="c48b6-155">Esta propiedad se suele usar en ML.NET: normalmente, el modelo ML.NET entrenado es una cadena de componentes Transformer, es decir, a todos los efectos, un componente *Transformer*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-155">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="c48b6-156">Lector de datos</span><span class="sxs-lookup"><span data-stu-id="c48b6-156">Data reader</span></span>

<span data-ttu-id="c48b6-157">El lector de datos es un componente de ML.NET para "crear" datos: toma una instancia de `T` y devuelve datos fuera de esta.</span><span class="sxs-lookup"><span data-stu-id="c48b6-157">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="c48b6-158">Una propiedad interesante a tener en cuenta es que puede crear un lector de datos asociando un componente Transformer a un lector de datos existente.</span><span class="sxs-lookup"><span data-stu-id="c48b6-158">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="c48b6-159">De esta forma puede tener un lector con comportamiento de transformación a la carta:</span><span class="sxs-lookup"><span data-stu-id="c48b6-159">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="c48b6-160">Otra similitud con los componentes Transformer es que, puesto que los datos se evalúan de forma diferida, *los lectores son diferidos*: no se produce ninguna "lectura" real (o mínima) al llamar a `reader.Read()`: solo al solicitarse un cursor en los datos resultantes, el lector empieza a funcionar.</span><span class="sxs-lookup"><span data-stu-id="c48b6-160">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="c48b6-161">Estimador</span><span class="sxs-lookup"><span data-stu-id="c48b6-161">Estimator</span></span>

<span data-ttu-id="c48b6-162">El *estimador* es un objeto que aprende de los datos.</span><span class="sxs-lookup"><span data-stu-id="c48b6-162">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="c48b6-163">El resultado del aprendizaje es un componente *Transformer*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-163">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="c48b6-164">En ML.NET, use esta propiedad para crear canalizaciones de aprendizaje que encadenen diferentes estimadores:</span><span class="sxs-lookup"><span data-stu-id="c48b6-164">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

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

<span data-ttu-id="c48b6-165">Una propiedad importante de los estimadores es que los *estimadores son diligentes, no diferidos*: todas las llamadas a `Fit` están haciendo que se produzca el aprendizaje, lo que es posiblemente una operación que demanda mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="c48b6-165">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="c48b6-166">Función de predicción</span><span class="sxs-lookup"><span data-stu-id="c48b6-166">Prediction function</span></span>

<span data-ttu-id="c48b6-167">La función de predicción se puede ver como un componente que aplica un componente Transformer a una fila.</span><span class="sxs-lookup"><span data-stu-id="c48b6-167">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="c48b6-168">Una vez que obtenga el modelo (un componente *Transformer* entrenado a través de `Fit()` o cargado desde algún lugar), puede usarlo para realizar predicciones con las llamadas normales a `model.Transform(data)`.</span><span class="sxs-lookup"><span data-stu-id="c48b6-168">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="c48b6-169">Sin embargo, cuando usa este modelo en un escenario de la vida real, no suele contar con muchos ejemplos sobre los que predecir.</span><span class="sxs-lookup"><span data-stu-id="c48b6-169">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="c48b6-170">En su lugar, tiene un ejemplo a la vez y debe realizar predicciones puntuales sobre ellos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c48b6-170">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="c48b6-171">Por supuesto, puede reducir esto a la predicción por lotes:</span><span class="sxs-lookup"><span data-stu-id="c48b6-171">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="c48b6-172">Cree una vista de datos con una fila exactamente.</span><span class="sxs-lookup"><span data-stu-id="c48b6-172">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="c48b6-173">Llame a `model.Transform(data)` para obtener la vista de datos prevista.</span><span class="sxs-lookup"><span data-stu-id="c48b6-173">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="c48b6-174">Obtenga un cursor a través de los datos resultantes.</span><span class="sxs-lookup"><span data-stu-id="c48b6-174">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="c48b6-175">Avance un paso con el cursor para obtener acceso a la primera (y única) fila.</span><span class="sxs-lookup"><span data-stu-id="c48b6-175">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="c48b6-176">Extraiga los valores previstos de ella.</span><span class="sxs-lookup"><span data-stu-id="c48b6-176">Extract the predicted values out of it.</span></span>

<span data-ttu-id="c48b6-177">El algoritmo anterior se puede implementar mediante la [comprensión de esquema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con dos objetos `InputExample` y `OutputPrediction` definidos por el usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c48b6-177">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="c48b6-178">Pero esto es complicado e implica costos de rendimiento. </span><span class="sxs-lookup"><span data-stu-id="c48b6-178">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="c48b6-179">En su lugar, un objeto de función de predicción realiza el mismo trabajo, pero de forma más rápida y adecuada, a través de un método de extensión `CreatePredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="c48b6-179">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="c48b6-180">La función de predicción *no es reentrante / es segura para subprocesos*.</span><span class="sxs-lookup"><span data-stu-id="c48b6-180">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="c48b6-181">Si desea realizar predicciones simultáneamente con varios subprocesos, debe tener una función de predicción por subproceso.</span><span class="sxs-lookup"><span data-stu-id="c48b6-181">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
