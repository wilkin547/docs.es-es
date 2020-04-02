---
title: ¿Qué es el Generador de modelos y cómo funciona?
description: Cómo usar el Generador de modelos de ML.NET para entrenar un modelo de Machine Learning de forma automática
ms.date: 03/25/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 9cf66455109908ebd9fc10e62cf4f067609b57d9
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344783"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="be810-103">¿Qué es el Generador de modelos y cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="be810-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="be810-104">El Generador de modelos de ML.NET es una extensión gráfica intuitiva de Visual Studio para compilar, entrenar e implementar modelos de Machine Learning personalizados.</span><span class="sxs-lookup"><span data-stu-id="be810-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="be810-105">El Generador de modelos usa aprendizaje automático automatizado (AutoML) para explorar distintos algoritmos y configuraciones de aprendizaje automático a fin de ayudar a encontrar el más adecuado a cada escenario.</span><span class="sxs-lookup"><span data-stu-id="be810-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="be810-106">Para usar el Generador de modelos no se necesita experiencia previa con el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="be810-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="be810-107">Lo único que se necesita son algunos datos y un problema para resolver.</span><span class="sxs-lookup"><span data-stu-id="be810-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="be810-108">El Generador de modelos genera el código para agregar el modelo a la aplicación de .NET.</span><span class="sxs-lookup"><span data-stu-id="be810-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animación de la interfaz de usuario de la extensión Generador de modelos de Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="be810-110">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="be810-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="be810-111">Escenario</span><span class="sxs-lookup"><span data-stu-id="be810-111">Scenario</span></span>

<span data-ttu-id="be810-112">Se pueden incorporar muchos escenarios diferentes al Generador de modelos a fin de generar un modelo de Machine Learning para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be810-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="be810-113">Un escenario es una descripción del tipo de predicción que se quiere realizar usando los datos.</span><span class="sxs-lookup"><span data-stu-id="be810-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="be810-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be810-114">For example:</span></span>

- <span data-ttu-id="be810-115">predecir el volumen futuro de ventas de productos en función de los datos de ventas históricos</span><span class="sxs-lookup"><span data-stu-id="be810-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="be810-116">clasificar opiniones como positivas o negativas en función de las revisiones de los clientes</span><span class="sxs-lookup"><span data-stu-id="be810-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="be810-117">detectar si una transacción bancaria es fraudulenta</span><span class="sxs-lookup"><span data-stu-id="be810-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="be810-118">dirigir problemas de comentarios de clientes al equipo correcto de la empresa</span><span class="sxs-lookup"><span data-stu-id="be810-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="be810-119">¿Qué escenario de aprendizaje automático es el más adecuado en cada caso?</span><span class="sxs-lookup"><span data-stu-id="be810-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="be810-120">En el Generador de modelos, debe seleccionar un escenario.</span><span class="sxs-lookup"><span data-stu-id="be810-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="be810-121">El tipo de escenario depende del tipo de predicción que esté intentando realizar.</span><span class="sxs-lookup"><span data-stu-id="be810-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="be810-122">Clasificación de textos</span><span class="sxs-lookup"><span data-stu-id="be810-122">Text classification</span></span>

<span data-ttu-id="be810-123">La clasificación se utiliza para clasificar los datos en categorías.</span><span class="sxs-lookup"><span data-stu-id="be810-123">Classification is used to categorize data into categories.</span></span>

![Diagrama en el que se muestran ejemplos de clasificación binaria, como detección de fraudes, mitigación de riesgos y filtrado de aplicaciones](media/binary-classification-examples.png)

![Ejemplos de clasificación multiclase que incluyen la clasificación de documentos y productos, el enrutamiento de incidencias de soporte técnico y la priorización de problemas de clientes](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="be810-126">Predicción de valores</span><span class="sxs-lookup"><span data-stu-id="be810-126">Value prediction</span></span>

<span data-ttu-id="be810-127">La regresión se usa para predecir números.</span><span class="sxs-lookup"><span data-stu-id="be810-127">Regression is used to predict numbers.</span></span>

![Diagrama en el que se muestran ejemplos de regresión, como la predicción de precios, la previsión de ventas y el mantenimiento predictivo](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="be810-129">Clasificación de la imagen</span><span class="sxs-lookup"><span data-stu-id="be810-129">Image classification</span></span>

<span data-ttu-id="be810-130">La clasificación de la imagen se puede utilizar para identificar imágenes de distintas categorías.</span><span class="sxs-lookup"><span data-stu-id="be810-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="be810-131">Por ejemplo, diferentes tipos de terreno, animales o defectos de fabricación.</span><span class="sxs-lookup"><span data-stu-id="be810-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="be810-132">Puede usar el escenario de clasificación de la imagen si tiene un conjunto de imágenes y desea clasificar las imágenes en distintas categorías.</span><span class="sxs-lookup"><span data-stu-id="be810-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="be810-133">Recomendación</span><span class="sxs-lookup"><span data-stu-id="be810-133">Recommendation</span></span>

<span data-ttu-id="be810-134">El escenario de recomendaciones predice una lista de elementos sugeridos para un usuario determinado, en función de la similitud y la diferencia entre los usuarios de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="be810-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="be810-135">Puede usar el escenario de recomendación cuando tenga un conjunto de usuarios y un conjunto de "productos", como artículos para comprar, películas, libros o programas de TV, junto con un conjunto de "clasificaciones" de los usuarios de esos productos.</span><span class="sxs-lookup"><span data-stu-id="be810-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="be810-136">Entorno</span><span class="sxs-lookup"><span data-stu-id="be810-136">Environment</span></span>

<span data-ttu-id="be810-137">Puede entrenar el modelo de aprendizaje automático localmente en la máquina o en la nube en Azure.</span><span class="sxs-lookup"><span data-stu-id="be810-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="be810-138">Al entrenar localmente, se trabaja dentro de las restricciones de los recursos del equipo (CPU, memoria y disco).</span><span class="sxs-lookup"><span data-stu-id="be810-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="be810-139">Al entrenar en la nube, puede escalar verticalmente los recursos para satisfacer las demandas de su escenario, especialmente para grandes conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="be810-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="be810-140">El entrenamiento local se admite en todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="be810-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="be810-141">El entrenamiento de Azure se admite para la clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="be810-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="be810-142">Datos</span><span class="sxs-lookup"><span data-stu-id="be810-142">Data</span></span>

<span data-ttu-id="be810-143">Una vez que ha elegido el escenario, el generador de modelos pide que se proporcione un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="be810-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="be810-144">Los datos se usan para entrenar, evaluar y elegir el mejor modelo para el escenario.</span><span class="sxs-lookup"><span data-stu-id="be810-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagrama en el que se muestran los pasos del generador de modelos](media/model-builder-steps.png)

<span data-ttu-id="be810-146">El generador de modelos admite conjuntos de datos en formatos. tsv,. csv,. txt, así como en el formato de base datos SQL.</span><span class="sxs-lookup"><span data-stu-id="be810-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="be810-147">Si tiene un archivo. txt, las columnas se deben separar con `,`, `;` o `/t`, y el archivo debe tener una fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="be810-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="be810-148">Si el conjunto de archivos se compone de imágenes, los tipos de archivo admitidos son `.jpg` y `.png`.</span><span class="sxs-lookup"><span data-stu-id="be810-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="be810-149">Para obtener más información, vea [Carga de datos de entrenamiento en el Generador de modelos](how-to-guides/load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="be810-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="be810-150">Selección del resultado que se va a predecir (etiqueta)</span><span class="sxs-lookup"><span data-stu-id="be810-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="be810-151">Un conjunto de datos es una tabla de filas de ejemplos de entrenamiento y columnas de atributos.</span><span class="sxs-lookup"><span data-stu-id="be810-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="be810-152">Cada fila tiene:</span><span class="sxs-lookup"><span data-stu-id="be810-152">Each row has:</span></span>

- <span data-ttu-id="be810-153">una **etiqueta** (el atributo que se quiere predecir)</span><span class="sxs-lookup"><span data-stu-id="be810-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="be810-154">**características** (atributos que se usan como entradas para predecir la etiqueta).</span><span class="sxs-lookup"><span data-stu-id="be810-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="be810-155">En el escenario de predicción del precio de las viviendas, las características podrían ser:</span><span class="sxs-lookup"><span data-stu-id="be810-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="be810-156">los metros cuadrados de la vivienda</span><span class="sxs-lookup"><span data-stu-id="be810-156">the square footage of the house</span></span>
- <span data-ttu-id="be810-157">el número de dormitorios y baños</span><span class="sxs-lookup"><span data-stu-id="be810-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="be810-158">el código postal</span><span class="sxs-lookup"><span data-stu-id="be810-158">the zip code</span></span>

<span data-ttu-id="be810-159">La etiqueta es el precio histórico de la vivienda para esa fila de valores de metros cuadrados, baños y dormitorios y el código postal.</span><span class="sxs-lookup"><span data-stu-id="be810-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabla donde se muestran las filas y columnas de datos de precios de viviendas con características que constan de etiquetas de tamaño, habitaciones, código postal y precio](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="be810-161">Conjuntos de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="be810-161">Example datasets</span></span>

<span data-ttu-id="be810-162">Si aún no tiene datos propios, pruebe uno de estos conjuntos de datos:</span><span class="sxs-lookup"><span data-stu-id="be810-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="be810-163">Escenario</span><span class="sxs-lookup"><span data-stu-id="be810-163">Scenario</span></span>|<span data-ttu-id="be810-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be810-164">Example</span></span>|<span data-ttu-id="be810-165">Datos</span><span class="sxs-lookup"><span data-stu-id="be810-165">Data</span></span>|<span data-ttu-id="be810-166">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="be810-166">Label</span></span>|<span data-ttu-id="be810-167">Características</span><span class="sxs-lookup"><span data-stu-id="be810-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="be810-168">Clasificación</span><span class="sxs-lookup"><span data-stu-id="be810-168">Classification</span></span>|<span data-ttu-id="be810-169">Predicción de anomalías de ventas</span><span class="sxs-lookup"><span data-stu-id="be810-169">Predict sales anomalies</span></span>|[<span data-ttu-id="be810-170">datos de ventas de productos</span><span class="sxs-lookup"><span data-stu-id="be810-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="be810-171">Ventas de productos</span><span class="sxs-lookup"><span data-stu-id="be810-171">Product Sales</span></span>|<span data-ttu-id="be810-172">Mes</span><span class="sxs-lookup"><span data-stu-id="be810-172">Month</span></span>|
||<span data-ttu-id="be810-173">Predicción de sentimiento de comentarios de sitios web</span><span class="sxs-lookup"><span data-stu-id="be810-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="be810-174">datos de comentarios de sitio web</span><span class="sxs-lookup"><span data-stu-id="be810-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="be810-175">Etiqueta (0 si la opinión es negativa, 1 si es positiva)</span><span class="sxs-lookup"><span data-stu-id="be810-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="be810-176">Comentario, año</span><span class="sxs-lookup"><span data-stu-id="be810-176">Comment, Year</span></span>|
||<span data-ttu-id="be810-177">Predicción de transacciones de tarjetas de crédito fraudulentas</span><span class="sxs-lookup"><span data-stu-id="be810-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="be810-178">datos de tarjetas de crédito</span><span class="sxs-lookup"><span data-stu-id="be810-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="be810-179">Clase (1 si es fraudulenta, en caso contrario, 0)</span><span class="sxs-lookup"><span data-stu-id="be810-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="be810-180">Cantidad, V1-V28 (características anónimas)</span><span class="sxs-lookup"><span data-stu-id="be810-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="be810-181">Predecir el tipo de problema en un repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="be810-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="be810-182">datos de problemas de GitHub</span><span class="sxs-lookup"><span data-stu-id="be810-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="be810-183">Área</span><span class="sxs-lookup"><span data-stu-id="be810-183">Area</span></span>|<span data-ttu-id="be810-184">Título, descripción</span><span class="sxs-lookup"><span data-stu-id="be810-184">Title, Description</span></span>|
|<span data-ttu-id="be810-185">Predicción de valores</span><span class="sxs-lookup"><span data-stu-id="be810-185">Value prediction</span></span>|<span data-ttu-id="be810-186">Predicción del precio de los taxis</span><span class="sxs-lookup"><span data-stu-id="be810-186">Predict taxi fare price</span></span>|[<span data-ttu-id="be810-187">datos de carreras de taxi</span><span class="sxs-lookup"><span data-stu-id="be810-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="be810-188">Carrera</span><span class="sxs-lookup"><span data-stu-id="be810-188">Fare</span></span>|<span data-ttu-id="be810-189">Tiempo de viaje, distancia</span><span class="sxs-lookup"><span data-stu-id="be810-189">Trip time, distance</span></span>|
|<span data-ttu-id="be810-190">Clasificación de la imagen</span><span class="sxs-lookup"><span data-stu-id="be810-190">Image classification</span></span>|<span data-ttu-id="be810-191">Predicción de la categoría de un problema</span><span class="sxs-lookup"><span data-stu-id="be810-191">Predict the category of an issue</span></span>|[<span data-ttu-id="be810-192">imágenes de flores</span><span class="sxs-lookup"><span data-stu-id="be810-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="be810-193">El tipo de flor: margarita, diente de león, rosas, girasoles o tulipanes</span><span class="sxs-lookup"><span data-stu-id="be810-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="be810-194">Los propios datos de la imagen</span><span class="sxs-lookup"><span data-stu-id="be810-194">The image data itself</span></span>|
|<span data-ttu-id="be810-195">Recomendación</span><span class="sxs-lookup"><span data-stu-id="be810-195">Recommendation</span></span>|<span data-ttu-id="be810-196">Predicción de películas que le gusten a alguien</span><span class="sxs-lookup"><span data-stu-id="be810-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="be810-197">clasificaciones de películas</span><span class="sxs-lookup"><span data-stu-id="be810-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="be810-198">Usuarios, películas</span><span class="sxs-lookup"><span data-stu-id="be810-198">Users, Movies</span></span>|<span data-ttu-id="be810-199">Clasificaciones</span><span class="sxs-lookup"><span data-stu-id="be810-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="be810-200">Entrenamiento</span><span class="sxs-lookup"><span data-stu-id="be810-200">Train</span></span>

<span data-ttu-id="be810-201">Una vez que se seleccionan el escenario, los datos y la etiqueta, el Generador de modelos entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-201">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="be810-202">¿Qué es el entrenamiento?</span><span class="sxs-lookup"><span data-stu-id="be810-202">What is training?</span></span>

<span data-ttu-id="be810-203">El entrenamiento es un proceso automático mediante el cual el Generador de modelos enseña al modelo a responder a preguntas del escenario.</span><span class="sxs-lookup"><span data-stu-id="be810-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="be810-204">Una vez entrenado, el modelo puede realizar predicciones con datos de entrada que no ha visto antes.</span><span class="sxs-lookup"><span data-stu-id="be810-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="be810-205">Por ejemplo, si está prediciendo los precios de la vivienda y se pone en el mercado un nuevo inmueble, puede predecir su precio de venta.</span><span class="sxs-lookup"><span data-stu-id="be810-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="be810-206">Dado que el Generador de modelos usa aprendizaje automático automatizado (AutoML), no requiere ninguna entrada ni ajuste por parte del usuario durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="be810-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="be810-207">¿Durante cuánto tiempo debe entrenarse?</span><span class="sxs-lookup"><span data-stu-id="be810-207">How long should I train for?</span></span>

<span data-ttu-id="be810-208">El generador de modelos usa AutoML para explorar varios modelos y encontrar el mejor modelo de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="be810-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="be810-209">Los períodos de entrenamiento más largos permiten a AutoML explorar más modelos con una mayor variedad de opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="be810-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="be810-210">En la tabla siguiente se resume el tiempo promedio necesario para obtener un buen rendimiento en un conjunto de conjuntos de valores de ejemplo, en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="be810-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="be810-211">Tamaño del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="be810-211">Dataset size</span></span>|<span data-ttu-id="be810-212">Promedio de tiempo para entrenar</span><span class="sxs-lookup"><span data-stu-id="be810-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="be810-213">0-10 MB</span><span class="sxs-lookup"><span data-stu-id="be810-213">0 - 10 MB</span></span>|<span data-ttu-id="be810-214">10 s</span><span class="sxs-lookup"><span data-stu-id="be810-214">10 sec</span></span>|
|<span data-ttu-id="be810-215">10-100 MB</span><span class="sxs-lookup"><span data-stu-id="be810-215">10 - 100 MB</span></span>|<span data-ttu-id="be810-216">10 min</span><span class="sxs-lookup"><span data-stu-id="be810-216">10 min</span></span>|
|<span data-ttu-id="be810-217">100-500 MB</span><span class="sxs-lookup"><span data-stu-id="be810-217">100 - 500 MB</span></span>|<span data-ttu-id="be810-218">30 min</span><span class="sxs-lookup"><span data-stu-id="be810-218">30 min</span></span>|
|<span data-ttu-id="be810-219">500-1 GB</span><span class="sxs-lookup"><span data-stu-id="be810-219">500 - 1 GB</span></span>|<span data-ttu-id="be810-220">60 min</span><span class="sxs-lookup"><span data-stu-id="be810-220">60 min</span></span>|
|<span data-ttu-id="be810-221">1 GB o más</span><span class="sxs-lookup"><span data-stu-id="be810-221">1 GB+</span></span>|<span data-ttu-id="be810-222">3 horas o más</span><span class="sxs-lookup"><span data-stu-id="be810-222">3+ hours</span></span>|

<span data-ttu-id="be810-223">Estos números son solo una guía.</span><span class="sxs-lookup"><span data-stu-id="be810-223">These numbers are a guide only.</span></span> <span data-ttu-id="be810-224">La duración exacta del entrenamiento depende de varios factores:</span><span class="sxs-lookup"><span data-stu-id="be810-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="be810-225">El número de características (columnas) que se usan como entrada para el modelo</span><span class="sxs-lookup"><span data-stu-id="be810-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="be810-226">El tipo de columnas</span><span class="sxs-lookup"><span data-stu-id="be810-226">the type of columns</span></span>
- <span data-ttu-id="be810-227">La tarea de ML</span><span class="sxs-lookup"><span data-stu-id="be810-227">the ML task</span></span>
- <span data-ttu-id="be810-228">El rendimiento de la CPU, el disco y la memoria de la máquina usada para el entrenamiento</span><span class="sxs-lookup"><span data-stu-id="be810-228">the CPU, disk, and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="be810-229">Evaluate</span><span class="sxs-lookup"><span data-stu-id="be810-229">Evaluate</span></span>

<span data-ttu-id="be810-230">La evaluación es el proceso por el que se mide el grado de calidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-230">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="be810-231">El Generador de modelo usa el modelo entrenado para realizar predicciones con nuevos datos de prueba y luego mide la calidad de las predicciones.</span><span class="sxs-lookup"><span data-stu-id="be810-231">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="be810-232">El Generador de modelos divide los datos de entrenamiento en un conjunto de entrenamiento y un conjunto de prueba.</span><span class="sxs-lookup"><span data-stu-id="be810-232">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="be810-233">Los datos de entrenamiento (80 %) se usan para entrenar el modelo y los datos de prueba (20 %) se incluyen para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-233">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="be810-234">¿Cómo puedo interpretar el rendimiento de mi modelo?</span><span class="sxs-lookup"><span data-stu-id="be810-234">How do I understand my model performance?</span></span>

<span data-ttu-id="be810-235">Un escenario se asigna a una tarea de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="be810-235">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="be810-236">Cada tarea de ML tiene su propio conjunto de métricas de evaluación.</span><span class="sxs-lookup"><span data-stu-id="be810-236">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="be810-237">Predicción de valores</span><span class="sxs-lookup"><span data-stu-id="be810-237">Value prediction</span></span>

<span data-ttu-id="be810-238">La métrica predeterminada para los problemas de predicción de valores es RSquared, y el valor de RSquared oscila entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="be810-238">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="be810-239">1 es el mejor valor posible o, en otras palabras, cuanto más se acerque el valor de RSquared a 1, mejor será el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-239">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="be810-240">Otras métricas notificadas, como pérdida absoluta, pérdida al cuadrado y pérdida RMS son métricas adicionales, que pueden usarse para comprender el rendimiento del modelo y compararlo con otros modelos de predicción de valores.</span><span class="sxs-lookup"><span data-stu-id="be810-240">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="be810-241">Clasificación (2 categorías)</span><span class="sxs-lookup"><span data-stu-id="be810-241">Classification (2 categories)</span></span>

<span data-ttu-id="be810-242">La métrica predeterminada para los problemas de clasificación es la precisión.</span><span class="sxs-lookup"><span data-stu-id="be810-242">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="be810-243">La precisión define la proporción de predicciones correctas que realiza el modelo en el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="be810-243">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="be810-244">Cuanto más cerca esté del 100 % o 1.0, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-244">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="be810-245">Otras métricas notificadas, como AUC (área bajo la curva), que mide la tasa de positivos verdaderos frente a la tasa de falsos positivos, deben ser superiores a 0,50 para que los modelos sean aceptables.</span><span class="sxs-lookup"><span data-stu-id="be810-245">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="be810-246">Se pueden usar métricas adicionales como la puntuación F1 para controlar el equilibrio entre la precisión y la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="be810-246">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="be810-247">Clasificación (3 categorías)</span><span class="sxs-lookup"><span data-stu-id="be810-247">Classification (3+ categories)</span></span>

<span data-ttu-id="be810-248">La métrica predeterminada para la clasificación multiclase es la microprecisión.</span><span class="sxs-lookup"><span data-stu-id="be810-248">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="be810-249">Cuanto más se acerque la microprecisión al 100 % o 1,0, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-249">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="be810-250">Otra métrica importante para la clasificación multiclase es la macroprecisión, que, de forma similar a la de la microprecisión, cuanto más se acerque a 1,0 mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-250">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="be810-251">Una buena manera de imaginarse estos dos tipos de precisión es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="be810-251">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="be810-252">Microprecisión: ¿con qué frecuencia se clasifica una incidencia entrante en el equipo adecuado?</span><span class="sxs-lookup"><span data-stu-id="be810-252">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="be810-253">Macroprecisión: para un equipo promedio, ¿con qué frecuencia es correcta una incidencia entrante para su equipo?</span><span class="sxs-lookup"><span data-stu-id="be810-253">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="be810-254">Más información sobre las métricas de evaluación</span><span class="sxs-lookup"><span data-stu-id="be810-254">More information on evaluation metrics</span></span>

<span data-ttu-id="be810-255">Para obtener más información, vea [Métricas de evaluación de modelos](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="be810-255">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="be810-256">Mejora</span><span class="sxs-lookup"><span data-stu-id="be810-256">Improve</span></span>

<span data-ttu-id="be810-257">Si la puntuación de rendimiento del modelo no es tan buena como se quiere que sea, se puede:</span><span class="sxs-lookup"><span data-stu-id="be810-257">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="be810-258">Entrenar durante más tiempo.</span><span class="sxs-lookup"><span data-stu-id="be810-258">Train for a longer period of time.</span></span> <span data-ttu-id="be810-259">Con más tiempo, el motor de aprendizaje automático automatizado experimenta con más algoritmos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="be810-259">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="be810-260">Agregar más datos.</span><span class="sxs-lookup"><span data-stu-id="be810-260">Add more data.</span></span> <span data-ttu-id="be810-261">A veces la cantidad de datos no es suficiente para entrenar un modelo de Machine Learning de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="be810-261">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="be810-262">Equilibrar los datos.</span><span class="sxs-lookup"><span data-stu-id="be810-262">Balance your data.</span></span> <span data-ttu-id="be810-263">En las tareas de clasificación, asegúrese de que el conjunto de entrenamiento esté equilibrado entre las categorías.</span><span class="sxs-lookup"><span data-stu-id="be810-263">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="be810-264">Por ejemplo, si tiene cuatro clases de 100 ejemplos de entrenamiento y las dos primeras (etiqueta1 y etiqueta2) se usan para 90 registros, pero las otras dos (etiqueta3 y etiqueta4) solo se usan en los 10 registros restantes, la falta de datos equilibrados puede hacer que el modelo se esfuerce por predecir correctamente etiqueta3 o etiqueta4.</span><span class="sxs-lookup"><span data-stu-id="be810-264">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="be810-265">Código</span><span class="sxs-lookup"><span data-stu-id="be810-265">Code</span></span>

<span data-ttu-id="be810-266">Después de la fase de evaluación, el Generador de modelos genera un archivo de modelo y el código que se puede usar para agregar el modelo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be810-266">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="be810-267">Los modelos de ML.NET se guardan como un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="be810-267">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="be810-268">El código para cargar y usar el modelo se agrega como un nuevo proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="be810-268">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="be810-269">El Generador de modelos también agrega una aplicación de consola de ejemplo que se puede ejecutar para ver el modelo en acción.</span><span class="sxs-lookup"><span data-stu-id="be810-269">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="be810-270">Además, el Generador de modelos produce el código que ha generado el modelo, para que pueda entender los pasos llevados a cabo para generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="be810-270">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="be810-271">También puede usar el código de entrenamiento del modelo para volver a entrenar el modelo con nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="be810-271">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="be810-272">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="be810-272">What's next?</span></span>

<span data-ttu-id="be810-273">[Instalar](how-to-guides/install-model-builder.md) la extensión de Visual Studio del generador de modelos</span><span class="sxs-lookup"><span data-stu-id="be810-273">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="be810-274">Pruebe la [predicción de precios o cualquier escenario de regresión](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="be810-274">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
