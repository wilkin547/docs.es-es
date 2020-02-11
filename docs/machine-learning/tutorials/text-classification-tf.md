---
title: 'Tutorial: Análisis de opinión mediante un modelo TensorFlow'
description: En este tutorial se muestra cómo usar un modelo de TensorFlow previamente entrenado para clasificar la opinión en comentarios de sitios Web. El clasificador binario de opiniones es una aplicación de consola de C# desarrollada con Visual Studio.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7a6043f56a2ecaca633ba5545170f27a85a22efc
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092400"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="71469-104">Tutorial: Análisis de la opinión de reseñas de películas con un modelo de TensorFlow entrenado previamente en ML.NET</span><span class="sxs-lookup"><span data-stu-id="71469-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="71469-105">En este tutorial se muestra cómo usar un modelo de TensorFlow previamente entrenado para clasificar la opinión en comentarios de sitios Web.</span><span class="sxs-lookup"><span data-stu-id="71469-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="71469-106">El clasificador binario de opiniones es una aplicación de consola de C# desarrollada con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="71469-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="71469-107">El modelo de TensorFlow que se usa en este tutorial se entrenó con reseñas de películas procedentes de la base de datos de IMDB.</span><span class="sxs-lookup"><span data-stu-id="71469-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="71469-108">Cuando haya terminado de desarrollar la aplicación, podrá proporcionar el texto de la reseña de la película y la aplicación le indicará si la reseña tiene una opinión positiva o negativa.</span><span class="sxs-lookup"><span data-stu-id="71469-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="71469-109">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="71469-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="71469-110">Carga de un modelo de TensorFlow entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="71469-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="71469-111">Transformación del texto de comentario del sitio web en características adecuadas para el modelo</span><span class="sxs-lookup"><span data-stu-id="71469-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="71469-112">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="71469-112">Use the model to make a prediction</span></span>

<span data-ttu-id="71469-113">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="71469-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71469-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="71469-114">Prerequisites</span></span>

* <span data-ttu-id="71469-115">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="71469-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="71469-116">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="71469-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="71469-117">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="71469-117">Create the application</span></span>

1. <span data-ttu-id="71469-118">Cree una **aplicación de consola de .NET Core** denominada "TextClassificationTF".</span><span class="sxs-lookup"><span data-stu-id="71469-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="71469-119">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="71469-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="71469-120">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="71469-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="71469-121">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="71469-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="71469-122">Elija "nuget.org" como origen del paquete y luego seleccione la pestaña **Examinar**. Busque **Microsoft.ML**, seleccione el paquete que desee y luego, el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="71469-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="71469-123">Acepte los términos de licencia del paquete que elija para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="71469-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="71469-124">Repita estos pasos para **Microsoft.ML.TensorFlow** y **SciSharp.TensorFlow.Redist**.</span><span class="sxs-lookup"><span data-stu-id="71469-124">Repeat these steps for **Microsoft.ML.TensorFlow** and **SciSharp.TensorFlow.Redist**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="71469-125">Adición del modelo TensorFlow al proyecto</span><span class="sxs-lookup"><span data-stu-id="71469-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="71469-126">El modelo de este tutorial procede del repositorio de GitHub, [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model).</span><span class="sxs-lookup"><span data-stu-id="71469-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="71469-127">El modelo tiene el formato TensorFlow SavedModel.</span><span class="sxs-lookup"><span data-stu-id="71469-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="71469-128">Descargue el [archivo zip sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="71469-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="71469-129">El archivo zip contiene:</span><span class="sxs-lookup"><span data-stu-id="71469-129">The zip file contains:</span></span>

    * <span data-ttu-id="71469-130">`saved_model.pb`: el propio modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="71469-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="71469-131">El modelo toma una matriz de enteros de longitud fija (tamaño 600) de características que representan el texto de una cadena de reseña de IMDB y genera dos probabilidades que suman 1: la probabilidad de que la reseña de entrada tenga una opinión positiva y la probabilidad de que la reseña de entrada tenga una opinión negativa.</span><span class="sxs-lookup"><span data-stu-id="71469-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="71469-132">`imdb_word_index.csv`: una asignación de palabras individuales a un valor entero.</span><span class="sxs-lookup"><span data-stu-id="71469-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="71469-133">La asignación se usa para generar las características de entrada para el modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="71469-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="71469-134">Copie el contenido del directorio `sentiment_model` más interno en el directorio `sentiment_model` del proyecto *TextClassificationTF*.</span><span class="sxs-lookup"><span data-stu-id="71469-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="71469-135">En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="71469-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![contenido del directorio sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="71469-137">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio `sentiment_model` y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="71469-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="71469-138">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="71469-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="71469-139">Adición de instrucciones Using y variables globales</span><span class="sxs-lookup"><span data-stu-id="71469-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="71469-140">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="71469-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="71469-141">Cree dos variables globales justo encima del método `Main`para que contengan la ruta de acceso del archivo de modelo guardado y la longitud del vector de características.</span><span class="sxs-lookup"><span data-stu-id="71469-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="71469-142">`_modelPath` es la ruta de acceso del archivo del modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="71469-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="71469-143">`FeatureLength` es la longitud de la matriz de características de tipo entero que el modelo espera.</span><span class="sxs-lookup"><span data-stu-id="71469-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="71469-144">Modelado de los datos</span><span class="sxs-lookup"><span data-stu-id="71469-144">Model the data</span></span>

<span data-ttu-id="71469-145">Las reseñas de películas son texto de forma libre.</span><span class="sxs-lookup"><span data-stu-id="71469-145">Movie reviews are free form text.</span></span> <span data-ttu-id="71469-146">La aplicación convierte el texto en el formato de entrada que el modelo espera en varias fases discretas.</span><span class="sxs-lookup"><span data-stu-id="71469-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="71469-147">La primera consiste en dividir el texto en palabras independientes y usar el archivo de asignación proporcionado para asignar cada palabra a una codificación de enteros.</span><span class="sxs-lookup"><span data-stu-id="71469-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="71469-148">El resultado de esta transformación es una matriz de enteros de longitud variable cuya longitud corresponde al número de palabras de la oración.</span><span class="sxs-lookup"><span data-stu-id="71469-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="71469-149">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="71469-149">Property</span></span>| <span data-ttu-id="71469-150">Valor</span><span class="sxs-lookup"><span data-stu-id="71469-150">Value</span></span>|<span data-ttu-id="71469-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="71469-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="71469-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="71469-152">ReviewText</span></span>|<span data-ttu-id="71469-153">Esta película es realmente buena</span><span class="sxs-lookup"><span data-stu-id="71469-153">this film is really good</span></span>|<span data-ttu-id="71469-154">cadena</span><span class="sxs-lookup"><span data-stu-id="71469-154">string</span></span>|
|<span data-ttu-id="71469-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="71469-155">VariableLengthFeatures</span></span>|<span data-ttu-id="71469-156">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71469-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="71469-157">int[]</span><span class="sxs-lookup"><span data-stu-id="71469-157">int[]</span></span>|

<span data-ttu-id="71469-158">El tamaño de la matriz de características de longitud variable se cambia a una longitud fija de 600.</span><span class="sxs-lookup"><span data-stu-id="71469-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="71469-159">Esta es la longitud que espera el modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="71469-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="71469-160">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="71469-160">Property</span></span>| <span data-ttu-id="71469-161">Valor</span><span class="sxs-lookup"><span data-stu-id="71469-161">Value</span></span>|<span data-ttu-id="71469-162">Tipo</span><span class="sxs-lookup"><span data-stu-id="71469-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="71469-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="71469-163">ReviewText</span></span>|<span data-ttu-id="71469-164">Esta película es realmente buena</span><span class="sxs-lookup"><span data-stu-id="71469-164">this film is really good</span></span>|<span data-ttu-id="71469-165">cadena</span><span class="sxs-lookup"><span data-stu-id="71469-165">string</span></span>|
|<span data-ttu-id="71469-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="71469-166">VariableLengthFeatures</span></span>|<span data-ttu-id="71469-167">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71469-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="71469-168">int[]</span><span class="sxs-lookup"><span data-stu-id="71469-168">int[]</span></span>|
|<span data-ttu-id="71469-169">Características</span><span class="sxs-lookup"><span data-stu-id="71469-169">Features</span></span>|<span data-ttu-id="71469-170">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71469-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="71469-171">int[600]</span><span class="sxs-lookup"><span data-stu-id="71469-171">int[600]</span></span>|

1. <span data-ttu-id="71469-172">Cree una clase para los datos de entrada, después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="71469-173">La clase de datos de entrada, `MovieReview`, tiene un objeto `string` para comentarios de usuario (`ReviewText`).</span><span class="sxs-lookup"><span data-stu-id="71469-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="71469-174">Cree una clase para las características de longitud variable, después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="71469-175">La propiedad `VariableLengthFeatures` tiene un atributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) para designarla como vector.</span><span class="sxs-lookup"><span data-stu-id="71469-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="71469-176">Todos los elementos de vector deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="71469-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="71469-177">En conjuntos de datos con un gran número de columnas, la carga de varias columnas como un único vector reduce el número de pasadas de datos cuando se aplican transformaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="71469-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="71469-178">Esta clase se usa en la acción `ResizeFeatures`.</span><span class="sxs-lookup"><span data-stu-id="71469-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="71469-179">Los nombres de sus propiedades (en este caso, solo una) se usan para indicar las columnas de DataView que se pueden usar como _entrada_ de la acción de asignación personalizada.</span><span class="sxs-lookup"><span data-stu-id="71469-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="71469-180">Cree una clase para las características de longitud fija, después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="71469-181">Esta clase se usa en la acción `ResizeFeatures`.</span><span class="sxs-lookup"><span data-stu-id="71469-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="71469-182">Los nombres de sus propiedades (en este caso, solo una) se usan para indicar las columnas de DataView que se pueden usar como _salida_ de la acción de asignación personalizada.</span><span class="sxs-lookup"><span data-stu-id="71469-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="71469-183">Tenga en cuenta que el nombre de la propiedad `Features` viene determinado por el modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="71469-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="71469-184">Este nombre de propiedad no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="71469-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="71469-185">Cree una clase para la predicción después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="71469-186">`MovieReviewSentimentPrediction` es la clase de predicción que se utiliza tras el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="71469-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="71469-187">`MovieReviewSentimentPrediction` tiene una sola matriz `float` (`Prediction`) y un atributo `VectorType`.</span><span class="sxs-lookup"><span data-stu-id="71469-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="71469-188">Creación de la clase MLContext, el diccionario de búsqueda y la acción para cambiar el tamaño de las características</span><span class="sxs-lookup"><span data-stu-id="71469-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="71469-189">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="71469-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="71469-190">La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="71469-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="71469-191">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="71469-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="71469-192">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable mlContext:</span><span class="sxs-lookup"><span data-stu-id="71469-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="71469-193">Cree un diccionario para codificar palabras como enteros mediante el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) para cargar los datos de asignación de un archivo, como se aprecia en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="71469-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="71469-194">Palabra</span><span class="sxs-lookup"><span data-stu-id="71469-194">Word</span></span>     |<span data-ttu-id="71469-195">Índice</span><span class="sxs-lookup"><span data-stu-id="71469-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="71469-196">niños</span><span class="sxs-lookup"><span data-stu-id="71469-196">kids</span></span>     |  <span data-ttu-id="71469-197">362</span><span class="sxs-lookup"><span data-stu-id="71469-197">362</span></span>    |
    |<span data-ttu-id="71469-198">quiero</span><span class="sxs-lookup"><span data-stu-id="71469-198">want</span></span>     |  <span data-ttu-id="71469-199">181</span><span class="sxs-lookup"><span data-stu-id="71469-199">181</span></span>    |
    |<span data-ttu-id="71469-200">incorrecto</span><span class="sxs-lookup"><span data-stu-id="71469-200">wrong</span></span>    |  <span data-ttu-id="71469-201">355</span><span class="sxs-lookup"><span data-stu-id="71469-201">355</span></span>    |
    |<span data-ttu-id="71469-202">efectos</span><span class="sxs-lookup"><span data-stu-id="71469-202">effects</span></span>  |  <span data-ttu-id="71469-203">302</span><span class="sxs-lookup"><span data-stu-id="71469-203">302</span></span>    |
    |<span data-ttu-id="71469-204">sentimiento</span><span class="sxs-lookup"><span data-stu-id="71469-204">feeling</span></span>  |  <span data-ttu-id="71469-205">547</span><span class="sxs-lookup"><span data-stu-id="71469-205">547</span></span>    |

    <span data-ttu-id="71469-206">Agregue el código siguiente para crear la asignación de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="71469-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="71469-207">Agregue un objeto `Action` para cambiar el tamaño de la matriz de enteros de palabras de longitud variable a una matriz de enteros de tamaño fijo, con las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="71469-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="71469-208">Carga del modelo de TensorFlow entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="71469-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="71469-209">Agregue código para cargar el modelo de TensorFlow:</span><span class="sxs-lookup"><span data-stu-id="71469-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="71469-210">Una vez cargado el modelo, puede extraer su esquema de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="71469-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="71469-211">Los esquemas se muestran solo a efectos de interés y aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="71469-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="71469-212">No necesita este código para que la aplicación final funcione:</span><span class="sxs-lookup"><span data-stu-id="71469-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    <span data-ttu-id="71469-213">El esquema de entrada es la matriz de longitud fija de palabras codificadas en enteros.</span><span class="sxs-lookup"><span data-stu-id="71469-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="71469-214">El esquema de salida es una matriz float de probabilidades que indica si la opinión de una reseña es negativa o positiva.</span><span class="sxs-lookup"><span data-stu-id="71469-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="71469-215">Estos valores suman 1, ya que la probabilidad de que sea positiva es el complemento de la probabilidad de que la opinión sea negativa.</span><span class="sxs-lookup"><span data-stu-id="71469-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="71469-216">Creación de la canalización de ML.NET</span><span class="sxs-lookup"><span data-stu-id="71469-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="71469-217">Cree la canalización y divida el texto de entrada en palabras con la transformación [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) para dividir el texto en palabras como la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="71469-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="71469-218">La transformación [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) usa espacios para analizar el texto o la cadena por palabras.</span><span class="sxs-lookup"><span data-stu-id="71469-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="71469-219">Crea otra columna y divide cada cadena de entrada en un vector de subcadenas según el separador definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="71469-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="71469-220">Asigne las palabras a su codificación de enteros con la tabla de búsqueda que declaró anteriormente:</span><span class="sxs-lookup"><span data-stu-id="71469-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. <span data-ttu-id="71469-221">Cambie el tamaño de las codificaciones de enteros de longitud variable al de longitud fija que requiere el modelo:</span><span class="sxs-lookup"><span data-stu-id="71469-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. <span data-ttu-id="71469-222">Clasifique la entrada con el modelo de TensorFlow cargado:</span><span class="sxs-lookup"><span data-stu-id="71469-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="71469-223">La salida del modelo de TensorFlow se denomina `Prediction/Softmax`.</span><span class="sxs-lookup"><span data-stu-id="71469-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="71469-224">Tenga en cuenta que el nombre `Prediction/Softmax` viene determinado por el modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="71469-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="71469-225">Este nombre no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="71469-225">You cannot change this name.</span></span>

1. <span data-ttu-id="71469-226">Cree otra columna para la predicción de salida:</span><span class="sxs-lookup"><span data-stu-id="71469-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="71469-227">Tiene que copiar la columna `Prediction/Softmax` en otra cuyo nombre pueda usarse como propiedad en una clase de C#: `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="71469-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="71469-228">El carácter `/` no está permitido en un nombre de propiedad de C#.</span><span class="sxs-lookup"><span data-stu-id="71469-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="71469-229">Creación del modelo de ML.NET a partir de la canalización</span><span class="sxs-lookup"><span data-stu-id="71469-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="71469-230">Agregue el código para crear el modelo a partir de la canalización:</span><span class="sxs-lookup"><span data-stu-id="71469-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="71469-231">Un modelo de ML.NET se crea a partir de la cadena de estimadores de la canalización llamando al método `Fit`.</span><span class="sxs-lookup"><span data-stu-id="71469-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="71469-232">En este caso, no se adaptan los datos para crear el modelo, puesto que el modelo de TensorFlow ya se ha entrenado previamente.</span><span class="sxs-lookup"><span data-stu-id="71469-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="71469-233">Proporcionamos un objeto de vista de datos vacío para satisfacer los requisitos del método `Fit`.</span><span class="sxs-lookup"><span data-stu-id="71469-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="71469-234">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="71469-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="71469-235">Agregue el método `PredictSentiment` después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="71469-236">Agregue el código siguiente para crear `PredictionEngine` como la primera línea en el método `PredictSentiment()`:</span><span class="sxs-lookup"><span data-stu-id="71469-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="71469-237">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="71469-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="71469-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="71469-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="71469-239">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="71469-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="71469-240">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71469-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="71469-241">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="71469-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="71469-242">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="71469-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="71469-243">Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict()` mediante la creación de una instancia de `MovieReview`:</span><span class="sxs-lookup"><span data-stu-id="71469-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. <span data-ttu-id="71469-244">Pase los datos del comentario de prueba a `Prediction Engine` agregando las líneas de código siguientes al método `PredictSentiment()`:</span><span class="sxs-lookup"><span data-stu-id="71469-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. <span data-ttu-id="71469-245">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una sola fila de datos:</span><span class="sxs-lookup"><span data-stu-id="71469-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="71469-246">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="71469-246">Property</span></span>| <span data-ttu-id="71469-247">Valor</span><span class="sxs-lookup"><span data-stu-id="71469-247">Value</span></span>|<span data-ttu-id="71469-248">Tipo</span><span class="sxs-lookup"><span data-stu-id="71469-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="71469-249">Predicción</span><span class="sxs-lookup"><span data-stu-id="71469-249">Prediction</span></span>|<span data-ttu-id="71469-250">[0.5459937, 0.454006255]</span><span class="sxs-lookup"><span data-stu-id="71469-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="71469-251">float[]</span><span class="sxs-lookup"><span data-stu-id="71469-251">float[]</span></span>|

1. <span data-ttu-id="71469-252">Muestre la predicción de opiniones con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="71469-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="71469-253">Agregue una llamada a `PredictSentiment` al final del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="71469-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="71469-254">Resultados</span><span class="sxs-lookup"><span data-stu-id="71469-254">Results</span></span>

<span data-ttu-id="71469-255">Compile y ejecute su aplicación.</span><span class="sxs-lookup"><span data-stu-id="71469-255">Build and run your application.</span></span>

<span data-ttu-id="71469-256">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="71469-256">Your results should be similar to the following.</span></span> <span data-ttu-id="71469-257">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="71469-257">During processing, messages are displayed.</span></span> <span data-ttu-id="71469-258">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="71469-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="71469-259">Estos mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="71469-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="71469-260">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="71469-260">Congratulations!</span></span> <span data-ttu-id="71469-261">Ha creado correctamente un modelo de Machine Learning para clasificar y predecir la opinión de los mensajes reutilizando un modelo de `TensorFlow` entrenado previamente en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="71469-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="71469-262">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="71469-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="71469-263">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="71469-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="71469-264">Carga de un modelo de TensorFlow entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="71469-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="71469-265">Transformación del texto de comentario del sitio web en características adecuadas para el modelo</span><span class="sxs-lookup"><span data-stu-id="71469-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="71469-266">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="71469-266">Use the model to make a prediction</span></span>
