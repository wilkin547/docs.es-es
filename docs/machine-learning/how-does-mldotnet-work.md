---
title: ¿Qué es ML.NET y cómo funciona?
description: ML.NET ofrece la posibilidad de agregar aprendizaje automático en aplicaciones de .NET, ya sea en escenarios en línea o sin conexión. Con esta funcionalidad, es posible realizar predicciones automáticas usando los datos disponibles para la aplicación sin tener que estar conectado a una red para usar ML.NET. En este artículo se explican los conceptos básicos de aprendizaje automático en ML.NET.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 98251c39a4bdaba8203c26c6a781a86efc46efa4
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740084"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="b055a-105">¿Qué es ML.NET y cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="b055a-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="b055a-106">ML.NET ofrece la posibilidad de agregar aprendizaje automático en aplicaciones de .NET, ya sea en escenarios en línea o sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b055a-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="b055a-107">Con esta funcionalidad, puede realizar predicciones automáticas con los datos disponibles para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b055a-107">With this capability, you can make automatic predictions using the data available to your application.</span></span>

<span data-ttu-id="b055a-108">La base de ML.NET es un **modelo** de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="b055a-108">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="b055a-109">El modelo especifica los pasos necesarios para transformar los datos de entrada en una predicción.</span><span class="sxs-lookup"><span data-stu-id="b055a-109">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="b055a-110">Con ML.NET, puede entrenar un modelo personalizado mediante la especificación de un algoritmo, o bien puede importar modelos TensorFlow y ONNX previamente entrenados.</span><span class="sxs-lookup"><span data-stu-id="b055a-110">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="b055a-111">Una vez que tiene un modelo, puede agregarlo a la aplicación para realizar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="b055a-111">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="b055a-112">ML.NET se ejecuta en Windows, Linux y macOS con .NET Core o en Windows mediante .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b055a-112">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="b055a-113">La versión de 64 bits es compatible con todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="b055a-113">64 bit is supported on all platforms.</span></span> <span data-ttu-id="b055a-114">La versión de 32 bits es compatible con Windows, salvo para la funcionalidad relacionada con TensorFlow, LightGBM y ONNX.</span><span class="sxs-lookup"><span data-stu-id="b055a-114">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX-related functionality.</span></span>

<span data-ttu-id="b055a-115">Algunos ejemplos del tipo de predicciones que puede hacer con ML.NET:</span><span class="sxs-lookup"><span data-stu-id="b055a-115">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="b055a-116">Clasificación y categorización</span><span class="sxs-lookup"><span data-stu-id="b055a-116">Classification/Categorization</span></span>|<span data-ttu-id="b055a-117">Clasifique automáticamente los comentarios del cliente en positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="b055a-117">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="b055a-118">Valores continuos de regresión y predicción</span><span class="sxs-lookup"><span data-stu-id="b055a-118">Regression/Predict continuous values</span></span>|<span data-ttu-id="b055a-119">Prediga el precio de la vivienda según el tamaño y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b055a-119">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="b055a-120">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="b055a-120">Anomaly Detection</span></span>|<span data-ttu-id="b055a-121">Detecte transacciones bancarias fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="b055a-121">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="b055a-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b055a-122">Recommendations</span></span>|<span data-ttu-id="b055a-123">Sugiera productos que los compradores en línea pueden comprar, en función de sus compras anteriores.</span><span class="sxs-lookup"><span data-stu-id="b055a-123">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="b055a-124">Series temporales y datos secuenciales</span><span class="sxs-lookup"><span data-stu-id="b055a-124">Time series/sequential data</span></span>|<span data-ttu-id="b055a-125">Haga una previsión del tiempo y de las ventas de productos</span><span class="sxs-lookup"><span data-stu-id="b055a-125">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="b055a-126">Clasificación de la imagen</span><span class="sxs-lookup"><span data-stu-id="b055a-126">Image classification</span></span>|<span data-ttu-id="b055a-127">Clasifique las patologías de imágenes médicas</span><span class="sxs-lookup"><span data-stu-id="b055a-127">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="b055a-128">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="b055a-128">Hello ML.NET World</span></span>

<span data-ttu-id="b055a-129">El código en el siguiente fragmento muestra la aplicación de ML.NET más sencilla.</span><span class="sxs-lookup"><span data-stu-id="b055a-129">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="b055a-130">En este ejemplo se crea un modelo de regresión lineal para predecir los precios de la vivienda con información sobre el tamaño y el precio de la vivienda.</span><span class="sxs-lookup"><span data-stu-id="b055a-130">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> 

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;

    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }

        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }

        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();

            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));

            // 3. Train model
            var model = pipeline.Fit(trainingData);

            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    }
```

## <a name="code-workflow"></a><span data-ttu-id="b055a-131">Flujo de trabajo del código</span><span class="sxs-lookup"><span data-stu-id="b055a-131">Code workflow</span></span>

<span data-ttu-id="b055a-132">El siguiente diagrama representa la estructura del código de aplicación, así como el proceso iterativo de desarrollo de modelos:</span><span class="sxs-lookup"><span data-stu-id="b055a-132">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="b055a-133">Recopilar y cargar datos de entrenamiento en un objeto **IDataView**</span><span class="sxs-lookup"><span data-stu-id="b055a-133">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="b055a-134">Especificar una canalización de operaciones para extraer características y aplicar un algoritmo de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="b055a-134">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="b055a-135">Entrenar un modelo mediante una llamada a **Fit()** en la canalización</span><span class="sxs-lookup"><span data-stu-id="b055a-135">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="b055a-136">Evaluar el modelo e iterar para mejorar</span><span class="sxs-lookup"><span data-stu-id="b055a-136">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="b055a-137">Guardar el modelo en formato binario, para su uso en una aplicación</span><span class="sxs-lookup"><span data-stu-id="b055a-137">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="b055a-138">Cargar el modelo en un objeto **ITransformer**</span><span class="sxs-lookup"><span data-stu-id="b055a-138">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="b055a-139">Realizar predicciones mediante una llamada a **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="b055a-139">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![Flujo de desarrollo de aplicaciones de ML.NET, incluidos los componentes para la generación de datos, el desarrollo de canalizaciones, el entrenamiento del modelo, la evaluación del modelo y el uso del modelo](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="b055a-141">Vamos a profundizar un poco más en estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="b055a-141">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="b055a-142">Modelo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b055a-142">Machine learning model</span></span>

<span data-ttu-id="b055a-143">Un modelo de ML.NET es un objeto que contiene las transformaciones que se realizarán en los datos de entrada para llegar a los resultados previstos.</span><span class="sxs-lookup"><span data-stu-id="b055a-143">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="b055a-144">Básico</span><span class="sxs-lookup"><span data-stu-id="b055a-144">Basic</span></span>

<span data-ttu-id="b055a-145">El modelo más básico es una regresión lineal bidimensional, donde una cantidad continua es proporcional a otra, como se muestra en el ejemplo anterior del precio de la vivienda.</span><span class="sxs-lookup"><span data-stu-id="b055a-145">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![El modelo de regresión lineal con parámetros de peso y sesgo](./media/linear-regression-model.svg)

<span data-ttu-id="b055a-147">El modelo es simplemente: $Precio = b + Tamaño \* w$.</span><span class="sxs-lookup"><span data-stu-id="b055a-147">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="b055a-148">Los parámetros $b$ y $w$ se calculan ajustando una línea en un conjunto de pares (tamaño, precio).</span><span class="sxs-lookup"><span data-stu-id="b055a-148">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="b055a-149">Los datos que se usan para buscar los parámetros del modelo se denominan **datos de aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="b055a-149">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="b055a-150">Las entradas de un modelo de Machine Learning se denominan **características**.</span><span class="sxs-lookup"><span data-stu-id="b055a-150">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="b055a-151">En este ejemplo, $Tamaño$ es la única característica.</span><span class="sxs-lookup"><span data-stu-id="b055a-151">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="b055a-152">Los valores de datos reales en el terreno que se usan para entrenar un modelo de Machine Learning se denominan **etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="b055a-152">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="b055a-153">En este caso, los valores de $Precio$ en el conjunto de datos de entrenamiento son las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="b055a-153">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="b055a-154">Más complejo</span><span class="sxs-lookup"><span data-stu-id="b055a-154">More complex</span></span>

<span data-ttu-id="b055a-155">Un modelo más complejo clasifica las transacciones financieras en categorías utilizando la descripción de texto de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b055a-155">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="b055a-156">La descripción de cada transacción se divide en un conjunto de características quitando palabras y caracteres redundantes, y contando combinaciones de palabras y caracteres.</span><span class="sxs-lookup"><span data-stu-id="b055a-156">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="b055a-157">El conjunto de características se utiliza para entrenar un modelo lineal según el conjunto de categorías en los datos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="b055a-157">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="b055a-158">Cuanto más similar es una nueva descripción a las del conjunto de entrenamiento, más probabilidades tiene de que se le asigne la misma categoría.</span><span class="sxs-lookup"><span data-stu-id="b055a-158">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![Modelo de clasificación de textos](./media/text-classification-model.svg)

<span data-ttu-id="b055a-160">Tanto el modelo de precios de vivienda como el modelo de clasificación de textos son modelos **lineales**.</span><span class="sxs-lookup"><span data-stu-id="b055a-160">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="b055a-161">Según la naturaleza de los datos y el problema que se va a resolver, también puede usar modelos de **árbol de decisión** y **modelos aditivos generalizados**, entre otros.</span><span class="sxs-lookup"><span data-stu-id="b055a-161">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="b055a-162">Para obtener más información sobre los modelos, vea [Tareas](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="b055a-162">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="b055a-163">Preparación de datos</span><span class="sxs-lookup"><span data-stu-id="b055a-163">Data preparation</span></span>

<span data-ttu-id="b055a-164">En la mayoría de los casos, los datos que tiene a su disposición no son aptos para usarse directamente en el entrenamiento de un modelo de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b055a-164">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="b055a-165">Los datos sin procesar deben prepararse o procesarse previamente antes de que se puedan usar para buscar los parámetros del modelo.</span><span class="sxs-lookup"><span data-stu-id="b055a-165">The raw data needs to be prepared, or pre-processed, before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="b055a-166">Es posible que los datos deban convertirse de valores de cadena a una representación numérica.</span><span class="sxs-lookup"><span data-stu-id="b055a-166">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="b055a-167">Puede que tenga información redundante en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b055a-167">You might have redundant information in your input data.</span></span> <span data-ttu-id="b055a-168">Tal vez necesite reducir o expandir las dimensiones de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b055a-168">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="b055a-169">Puede que los datos deban normalizarse o escalarse.</span><span class="sxs-lookup"><span data-stu-id="b055a-169">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="b055a-170">Los [tutoriales de ML.NET](./tutorials/index.md) le proporcionan información sobre las diferentes canalizaciones de procesamiento de datos para texto, imágenes, datos numéricos y de series temporales que se usan en tareas específicas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="b055a-170">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="b055a-171">[Cómo preparar los datos](./how-to-guides/prepare-data-ml-net.md) le explica cómo aplicar la preparación de datos de manera más general.</span><span class="sxs-lookup"><span data-stu-id="b055a-171">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to apply data preparation more generally.</span></span>

<span data-ttu-id="b055a-172">Encontrará un apéndice de todas las [transformaciones disponibles](./resources/transforms.md) en la sección de recursos.</span><span class="sxs-lookup"><span data-stu-id="b055a-172">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="b055a-173">Evaluación de modelo</span><span class="sxs-lookup"><span data-stu-id="b055a-173">Model evaluation</span></span>

<span data-ttu-id="b055a-174">Una vez que ha entrenado el modelo, ¿cómo sabe hasta qué punto realizará predicciones futuras?</span><span class="sxs-lookup"><span data-stu-id="b055a-174">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="b055a-175">Con ML.NET, puede evaluar su modelo con algunos datos de prueba nuevos.</span><span class="sxs-lookup"><span data-stu-id="b055a-175">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="b055a-176">Cada tipo de tarea de aprendizaje automático tiene métricas que se usan para evaluar la precisión y exactitud del modelo en el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b055a-176">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="b055a-177">En nuestro ejemplo de precios de vivienda, hemos usado la tarea **Regresión**.</span><span class="sxs-lookup"><span data-stu-id="b055a-177">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="b055a-178">Para evaluar el modelo, agregue el código siguiente en el ejemplo original.</span><span class="sxs-lookup"><span data-stu-id="b055a-178">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);

        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="b055a-179">Las métricas de evaluación indican que el error es bastante bajo y que la correlación entre la salida de predicción y la salida de prueba es alta.</span><span class="sxs-lookup"><span data-stu-id="b055a-179">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="b055a-180">¡Qué sencillo!</span><span class="sxs-lookup"><span data-stu-id="b055a-180">That was easy!</span></span> <span data-ttu-id="b055a-181">En los ejemplos reales, se necesitan más ajustes para lograr las métricas del modelo adecuado.</span><span class="sxs-lookup"><span data-stu-id="b055a-181">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="b055a-182">Arquitectura de ML.NET</span><span class="sxs-lookup"><span data-stu-id="b055a-182">ML.NET architecture</span></span>

<span data-ttu-id="b055a-183">En esta sección, veremos los patrones arquitectónicos de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b055a-183">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="b055a-184">Si es un desarrollador experimentado de .NET, algunos de estos patrones le resultarán familiares y otros serán menos conocidos.</span><span class="sxs-lookup"><span data-stu-id="b055a-184">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="b055a-185">¡Sujétese bien mientras nos sumergimos!</span><span class="sxs-lookup"><span data-stu-id="b055a-185">Hold tight, while we dive in!</span></span>

<span data-ttu-id="b055a-186">Una aplicación de ML.NET se inicia con un objeto <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="b055a-186">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="b055a-187">Este objeto singleton contiene **catálogos**.</span><span class="sxs-lookup"><span data-stu-id="b055a-187">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="b055a-188">Un catálogo es una fábrica para cargar y guardar datos, transformaciones, instructores y componentes de la operación de modelos.</span><span class="sxs-lookup"><span data-stu-id="b055a-188">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="b055a-189">Cada objeto de catálogo tiene métodos para crear los diferentes tipos de componentes:</span><span class="sxs-lookup"><span data-stu-id="b055a-189">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="b055a-190">Carga y guardado de datos</span><span class="sxs-lookup"><span data-stu-id="b055a-190">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="b055a-191">Preparación de datos</span><span class="sxs-lookup"><span data-stu-id="b055a-191">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="b055a-192">Algoritmos de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="b055a-192">Training algorithms</span></span>|<span data-ttu-id="b055a-193">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="b055a-193">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="b055a-194">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="b055a-194">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="b055a-195">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="b055a-195">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="b055a-196">Agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="b055a-196">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="b055a-197">Previsión</span><span class="sxs-lookup"><span data-stu-id="b055a-197">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="b055a-198">Clasificación</span><span class="sxs-lookup"><span data-stu-id="b055a-198">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="b055a-199">Regresión</span><span class="sxs-lookup"><span data-stu-id="b055a-199">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="b055a-200">Recomendación</span><span class="sxs-lookup"><span data-stu-id="b055a-200">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="b055a-201">Adición del paquete NuGet `Microsoft.ML.Recommender`</span><span class="sxs-lookup"><span data-stu-id="b055a-201">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="b055a-202">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="b055a-202">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="b055a-203">Adición del paquete NuGet `Microsoft.ML.TimeSeries`</span><span class="sxs-lookup"><span data-stu-id="b055a-203">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="b055a-204">Uso del modelo</span><span class="sxs-lookup"><span data-stu-id="b055a-204">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="b055a-205">Puede navegar a los métodos de creación en cada una de las categorías anteriores.</span><span class="sxs-lookup"><span data-stu-id="b055a-205">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="b055a-206">Con Visual Studio, los catálogos se muestran a través de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b055a-206">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense para instructores de regresión](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="b055a-208">Crear la canalización</span><span class="sxs-lookup"><span data-stu-id="b055a-208">Build the pipeline</span></span>

<span data-ttu-id="b055a-209">Dentro de cada catálogo hay un conjunto de métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="b055a-209">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="b055a-210">Echemos un vistazo a la forma en que se usan los métodos de extensión para crear una canalización de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="b055a-210">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="b055a-211">En el fragmento de código, `Concatenate` y `Sdca` son métodos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="b055a-211">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="b055a-212">Cada uno crea un objeto [IEstimator](xref:Microsoft.ML.IEstimator%601) que se anexa a la canalización.</span><span class="sxs-lookup"><span data-stu-id="b055a-212">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="b055a-213">En este momento, solo se crean los objetos.</span><span class="sxs-lookup"><span data-stu-id="b055a-213">At this point, the objects are created only.</span></span> <span data-ttu-id="b055a-214">No se ha producido ninguna ejecución.</span><span class="sxs-lookup"><span data-stu-id="b055a-214">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="b055a-215">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="b055a-215">Train the model</span></span>

<span data-ttu-id="b055a-216">Una vez que se han creado los objetos en la canalización, se pueden usar datos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b055a-216">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="b055a-217">Una llamada a `Fit()` usa los datos de entrenamiento de entrada para calcular los parámetros del modelo.</span><span class="sxs-lookup"><span data-stu-id="b055a-217">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="b055a-218">Esto se conoce como entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b055a-218">This is known as training the model.</span></span> <span data-ttu-id="b055a-219">Recuerde que el modelo de regresión lineal anterior tenía dos parámetros de modelo: **sesgo** y **peso**.</span><span class="sxs-lookup"><span data-stu-id="b055a-219">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="b055a-220">Después de la llamada de `Fit()`, se conocen los valores de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="b055a-220">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="b055a-221">La mayoría de los modelos tendrá muchos más parámetros que esto.</span><span class="sxs-lookup"><span data-stu-id="b055a-221">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="b055a-222">Puede obtener más información acerca del entrenamiento del modelo en [Cómo entrenar el modelo](./how-to-guides/train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="b055a-222">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md).</span></span>

<span data-ttu-id="b055a-223">El objeto del modelo resultante implementa la interfaz <xref:Microsoft.ML.ITransformer>.</span><span class="sxs-lookup"><span data-stu-id="b055a-223">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="b055a-224">Es decir, el modelo transforma datos de entrada en predicciones.</span><span class="sxs-lookup"><span data-stu-id="b055a-224">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="b055a-225">Uso del modelo</span><span class="sxs-lookup"><span data-stu-id="b055a-225">Use the model</span></span>

<span data-ttu-id="b055a-226">Puede transformar datos de entrada en predicciones de forma masiva o una entrada a la vez.</span><span class="sxs-lookup"><span data-stu-id="b055a-226">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="b055a-227">En el ejemplo de precios de vivienda, lo hicimos de ambas maneras: de forma masiva con el fin de evaluar el modelo y de uno en uno para realizar una predicción nueva.</span><span class="sxs-lookup"><span data-stu-id="b055a-227">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="b055a-228">Echemos un vistazo a la realización de predicciones únicas.</span><span class="sxs-lookup"><span data-stu-id="b055a-228">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="b055a-229">El método `CreatePredictionEngine()` toma una clase de entrada y una clase de salida.</span><span class="sxs-lookup"><span data-stu-id="b055a-229">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="b055a-230">Los atributos de código o los nombres de campo determinan los nombres de las columnas de datos utilizadas durante el entrenamiento del modelo y la predicción.</span><span class="sxs-lookup"><span data-stu-id="b055a-230">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="b055a-231">Puede leer más sobre [cómo realizar una sola predicción](./how-to-guides/single-predict-model-ml-net.md) en la sección de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b055a-231">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="b055a-232">Esquema y modelos de datos</span><span class="sxs-lookup"><span data-stu-id="b055a-232">Data models and schema</span></span>

<span data-ttu-id="b055a-233">En el núcleo de una canalización de aprendizaje automático de ML.NET están los objetos [DataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="b055a-233">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="b055a-234">Cada transformación en la canalización tiene un esquema de entrada (nombres, tipos y tamaños de datos que la transformación espera ver en su entrada), así como un esquema de salida (nombres, tipos y tamaños de datos que la transformación produce después de la misma).</span><span class="sxs-lookup"><span data-stu-id="b055a-234">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="b055a-235">En el siguiente documento se ofrece una explicación detallada de la [interfaz de IDataView y su sistema de tipos](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span><span class="sxs-lookup"><span data-stu-id="b055a-235">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="b055a-236">Si el esquema de salida de una transformación en la canalización no coincide con el esquema de entrada de la siguiente transformación, ML.NET producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="b055a-236">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="b055a-237">Un objeto de vista de datos tiene columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="b055a-237">A data view object has columns and rows.</span></span> <span data-ttu-id="b055a-238">Cada columna tiene un nombre, un tipo y una longitud.</span><span class="sxs-lookup"><span data-stu-id="b055a-238">Each column has a name and a type and a length.</span></span> <span data-ttu-id="b055a-239">Por ejemplo, las columnas de entrada en el ejemplo de precios de vivienda son **Tamaño** y **Precio**.</span><span class="sxs-lookup"><span data-stu-id="b055a-239">For example, the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="b055a-240">Ambas son tipos y cantidades escalares, en lugar de vectores.</span><span class="sxs-lookup"><span data-stu-id="b055a-240">They are both type and they are scalar quantities rather than vector ones.</span></span>

   ![Ejemplo de vista de datos de ML.NET con datos de predicción de precios de la vivienda](./media/ml-net-dataview.png)

<span data-ttu-id="b055a-242">Todos los algoritmos ML.NET buscan una columna de entrada que sea un vector.</span><span class="sxs-lookup"><span data-stu-id="b055a-242">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="b055a-243">De forma predeterminada, esta columna de vector se denomina **Características**.</span><span class="sxs-lookup"><span data-stu-id="b055a-243">By default this vector column is called **Features**.</span></span> <span data-ttu-id="b055a-244">Este es el motivo por el que concatenamos la columna **Tamaño** en una nueva columna denominada **Características** en nuestro ejemplo de precios de vivienda.</span><span class="sxs-lookup"><span data-stu-id="b055a-244">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="b055a-245">Todos los algoritmos también crean nuevas columnas una vez que han realizado una predicción.</span><span class="sxs-lookup"><span data-stu-id="b055a-245">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="b055a-246">Los nombres fijos de estas nuevas columnas dependen del tipo de algoritmo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="b055a-246">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="b055a-247">Para la tarea de regresión, una de las nuevas columnas se denomina **Puntuación**.</span><span class="sxs-lookup"><span data-stu-id="b055a-247">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="b055a-248">Este es el motivo por el que atribuimos nuestros datos de precios con este nombre.</span><span class="sxs-lookup"><span data-stu-id="b055a-248">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="b055a-249">Si desea obtener más información acerca de las columnas de salida de diferentes tareas de aprendizaje automático, vea la guía [Tareas de Machine Learning](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="b055a-249">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="b055a-250">Una propiedad importante de los objetos DataView es que se evalúan **de forma diferida**.</span><span class="sxs-lookup"><span data-stu-id="b055a-250">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="b055a-251">Las vistas de datos solo se cargan y utilizan en las operaciones durante el entrenamiento del modelo, la evaluación y la predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="b055a-251">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="b055a-252">Mientras escribe y prueba la aplicación de ML.NET, puede utilizar el depurador de Visual Studio para echar un vistazo a cualquier objeto de vista de datos llamando al método [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*).</span><span class="sxs-lookup"><span data-stu-id="b055a-252">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="b055a-253">Puede ver la variable `debug` en el depurador y examinar su contenido.</span><span class="sxs-lookup"><span data-stu-id="b055a-253">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="b055a-254">No utilice el método Preview en el código de producción, ya que reduce significativamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b055a-254">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="b055a-255">Implementación de modelos</span><span class="sxs-lookup"><span data-stu-id="b055a-255">Model Deployment</span></span>

<span data-ttu-id="b055a-256">En las aplicaciones de la vida real, el código de entrenamiento y evaluación del modelo será independiente de la predicción.</span><span class="sxs-lookup"><span data-stu-id="b055a-256">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="b055a-257">De hecho, estas dos actividades las realizan a menudo equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b055a-257">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="b055a-258">El equipo de desarrollo del modelo puede guardar el modelo para su uso en la aplicación de predicción.</span><span class="sxs-lookup"><span data-stu-id="b055a-258">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="b055a-259">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b055a-259">Next steps</span></span>

* <span data-ttu-id="b055a-260">Aprenda a crear aplicaciones mediante diferentes tareas de aprendizaje automático con conjuntos de datos más realistas en los [tutoriales](./tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="b055a-260">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="b055a-261">Obtenga información más detallada sobre temas específicos en las [guías de instrucciones](./how-to-guides/index.md).</span><span class="sxs-lookup"><span data-stu-id="b055a-261">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="b055a-262">Si está muy interesado, puede sumergirse directamente en la [documentación de referencia de la API](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b055a-262">If you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span></span>
