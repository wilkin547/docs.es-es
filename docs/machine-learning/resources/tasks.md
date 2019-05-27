---
title: Tareas de aprendizaje automático
description: Explore las diferentes tareas de aprendizaje automático y las tareas asociadas que se admiten en ML.NET.
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: ed6361fdcbca11c100ee5cae4ca76e152ddfba11
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063546"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="6849d-103">Tareas de aprendizaje automático en ML.NET</span><span class="sxs-lookup"><span data-stu-id="6849d-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="6849d-104">Cuando se crea un modelo de aprendizaje automático, primero debe definir lo que espera lograr con sus datos.</span><span class="sxs-lookup"><span data-stu-id="6849d-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="6849d-105">Esto le permite elegir la tarea de aprendizaje de automático adecuada para su situación.</span><span class="sxs-lookup"><span data-stu-id="6849d-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="6849d-106">La siguiente lista describe las diferentes tareas de aprendizaje automático que puede elegir y algunos casos de uso comunes.</span><span class="sxs-lookup"><span data-stu-id="6849d-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="6849d-107">Cuando haya decidido qué tarea funciona en su escenario, debe elegir el mejor algoritmo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="6849d-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="6849d-108">Los algoritmos disponibles se muestran en la sección correspondiente a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="6849d-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="6849d-109">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="6849d-109">Binary classification</span></span>

<span data-ttu-id="6849d-110">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="6849d-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="6849d-111">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="6849d-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="6849d-112">El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6849d-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="6849d-113">Entre los ejemplos de escenarios de clasificación binaria están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6849d-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="6849d-114">[Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".</span><span class="sxs-lookup"><span data-stu-id="6849d-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="6849d-115">Diagnosticar si un paciente tiene una determinada enfermedad o no.</span><span class="sxs-lookup"><span data-stu-id="6849d-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="6849d-116">Tomar una decisión para marcar un correo electrónico como no deseado o no.</span><span class="sxs-lookup"><span data-stu-id="6849d-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="6849d-117">Determinar si una foto contiene un perro o una fruta.</span><span class="sxs-lookup"><span data-stu-id="6849d-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="6849d-118">Para obtener más información, consulte el artículo de Wikipedia [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) (Clasificación binaria).</span><span class="sxs-lookup"><span data-stu-id="6849d-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="6849d-119">Instructores de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="6849d-119">Binary classification trainers</span></span>

<span data-ttu-id="6849d-120">Puede entrenar un modelo de clasificación binaria mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6849d-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer> 
* <xref:Microsoft.ML.Trainers.PriorTrainer> 
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="6849d-121">Entradas y salidas de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="6849d-121">Binary classification inputs and outputs</span></span>

<span data-ttu-id="6849d-122">Para obtener los mejores resultados con la clasificación binaria, los datos de entrenamiento deben estar equilibrados (es decir, igual número de datos de entrenamiento positivos y negativos).</span><span class="sxs-lookup"><span data-stu-id="6849d-122">For best results with binary classification, the training data should be balanced (i.e. equal numbers of positive and negative training data).</span></span> <span data-ttu-id="6849d-123">Los datos que faltan y los valores se deben controlar antes del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="6849d-123">Missing and values should be handled before training.</span></span>

<span data-ttu-id="6849d-124">Los datos de la columna de etiquetas de entrada deben ser <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="6849d-124">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="6849d-125">Los datos de la columna de características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-125">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="6849d-126">Estos instructores generan las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="6849d-126">These trainers outputs the following columns:</span></span>

| <span data-ttu-id="6849d-127">Nombre de columna de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-127">Output Column Name</span></span> | <span data-ttu-id="6849d-128">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="6849d-128">Column Type</span></span> | <span data-ttu-id="6849d-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-129">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="6849d-130">Puntuación sin procesar calculada por el modelo</span><span class="sxs-lookup"><span data-stu-id="6849d-130">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="6849d-131">Etiqueta de predicción, según el signo de la puntuación.</span><span class="sxs-lookup"><span data-stu-id="6849d-131">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="6849d-132">Una puntuación negativa se asigna a `false` y una positiva a `true`.</span><span class="sxs-lookup"><span data-stu-id="6849d-132">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="6849d-133">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="6849d-133">Multiclass classification</span></span>

<span data-ttu-id="6849d-134">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="6849d-134">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="6849d-135">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6849d-135">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="6849d-136">Cada etiqueta se inicia normalmente como texto.</span><span class="sxs-lookup"><span data-stu-id="6849d-136">Each label normally starts as text.</span></span> <span data-ttu-id="6849d-137">Luego se ejecuta mediante TermTransform, que lo convierte al tipo de clave (numérico).</span><span class="sxs-lookup"><span data-stu-id="6849d-137">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="6849d-138">El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6849d-138">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="6849d-139">Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6849d-139">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="6849d-140">Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.</span><span class="sxs-lookup"><span data-stu-id="6849d-140">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="6849d-141">Comprender las críticas de películas como "positivas", "neutrales" o "negativas".</span><span class="sxs-lookup"><span data-stu-id="6849d-141">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="6849d-142">Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.</span><span class="sxs-lookup"><span data-stu-id="6849d-142">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="6849d-143">Para obtener más información, consulte el artículo de Wikipedia [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) (Clasificación multiclase).</span><span class="sxs-lookup"><span data-stu-id="6849d-143">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="6849d-144">Uno frente a todos actualiza los [mecanismos de aprendizaje de clasificación binaria](#binary-classification) para que actúen en conjuntos de datos multiclase.</span><span class="sxs-lookup"><span data-stu-id="6849d-144">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="6849d-145">Obtenga más información sobre [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="6849d-145">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="6849d-146">Instructores de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="6849d-146">Multiclass classification trainers</span></span>

<span data-ttu-id="6849d-147">Puede entrenar un modelo de clasificación multiclase mediante los siguientes algoritmos de aprendizaje:</span><span class="sxs-lookup"><span data-stu-id="6849d-147">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer> 

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="6849d-148">Entradas y salidas de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="6849d-148">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="6849d-149">Los datos de la columna de etiquetas de entrada deben ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="6849d-149">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="6849d-150">La columna de características debe ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-150">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="6849d-151">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6849d-151">This trainer outputs the following:</span></span>

| <span data-ttu-id="6849d-152">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-152">Output Name</span></span> | <span data-ttu-id="6849d-153">Tipo</span><span class="sxs-lookup"><span data-stu-id="6849d-153">Type</span></span> | <span data-ttu-id="6849d-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-154">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="6849d-155">Vector de <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="6849d-155">Vector of <xref:System.Single></span></span> | <span data-ttu-id="6849d-156">Puntuaciones de todas las clases.</span><span class="sxs-lookup"><span data-stu-id="6849d-156">The scores of all classes.</span></span> <span data-ttu-id="6849d-157">Un valor más alto indica mayor probabilidad de que caigan en la clase asociada.</span><span class="sxs-lookup"><span data-stu-id="6849d-157">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="6849d-158">Si el elemento i-th tiene el valor más grande, el índice de la etiqueta de predicción sería i.</span><span class="sxs-lookup"><span data-stu-id="6849d-158">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="6849d-159">Tenga en cuenta que i es el índice de base cero.</span><span class="sxs-lookup"><span data-stu-id="6849d-159">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="6849d-160">Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="6849d-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="6849d-161">Índice de la etiqueta de predicción.</span><span class="sxs-lookup"><span data-stu-id="6849d-161">The predicted label's index.</span></span> <span data-ttu-id="6849d-162">Si su valor es i, la etiqueta real sería la categoría de i-th en el tipo de etiqueta de entrada con valores de clave.</span><span class="sxs-lookup"><span data-stu-id="6849d-162">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="6849d-163">Regresión</span><span class="sxs-lookup"><span data-stu-id="6849d-163">Regression</span></span>

<span data-ttu-id="6849d-164">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6849d-164">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="6849d-165">La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación.</span><span class="sxs-lookup"><span data-stu-id="6849d-165">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="6849d-166">Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características.</span><span class="sxs-lookup"><span data-stu-id="6849d-166">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="6849d-167">La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos.</span><span class="sxs-lookup"><span data-stu-id="6849d-167">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="6849d-168">El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada.</span><span class="sxs-lookup"><span data-stu-id="6849d-168">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="6849d-169">Estos son algunos ejemplos de escenarios de regresión:</span><span class="sxs-lookup"><span data-stu-id="6849d-169">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="6849d-170">Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.</span><span class="sxs-lookup"><span data-stu-id="6849d-170">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="6849d-171">Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.</span><span class="sxs-lookup"><span data-stu-id="6849d-171">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="6849d-172">Predecir las ventas de un producto en función del presupuesto para publicidad.</span><span class="sxs-lookup"><span data-stu-id="6849d-172">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="6849d-173">Instructores de regresión</span><span class="sxs-lookup"><span data-stu-id="6849d-173">Regression trainers</span></span>

<span data-ttu-id="6849d-174">Puede entrenar un modelo de regresión mediante los siguientes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="6849d-174">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="6849d-175">Entradas y salidas de regresión</span><span class="sxs-lookup"><span data-stu-id="6849d-175">Regression inputs and outputs</span></span>

<span data-ttu-id="6849d-176">Los datos de la columna de etiquetas de entrada deben ser <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-176">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="6849d-177">Los instructores para esta tarea producen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6849d-177">The trainers for this task output the following:</span></span>

| <span data-ttu-id="6849d-178">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-178">Output Name</span></span> | <span data-ttu-id="6849d-179">Tipo</span><span class="sxs-lookup"><span data-stu-id="6849d-179">Type</span></span> | <span data-ttu-id="6849d-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-180">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="6849d-181">Puntuación sin procesar que el modelo predijo</span><span class="sxs-lookup"><span data-stu-id="6849d-181">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="6849d-182">Agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="6849d-182">Clustering</span></span>

<span data-ttu-id="6849d-183">Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares.</span><span class="sxs-lookup"><span data-stu-id="6849d-183">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="6849d-184">La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación.</span><span class="sxs-lookup"><span data-stu-id="6849d-184">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="6849d-185">Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida.</span><span class="sxs-lookup"><span data-stu-id="6849d-185">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="6849d-186">Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad.</span><span class="sxs-lookup"><span data-stu-id="6849d-186">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="6849d-187">ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means.</span><span class="sxs-lookup"><span data-stu-id="6849d-187">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="6849d-188">Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6849d-188">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="6849d-189">Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.</span><span class="sxs-lookup"><span data-stu-id="6849d-189">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="6849d-190">Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.</span><span class="sxs-lookup"><span data-stu-id="6849d-190">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="6849d-191">Categorizar un inventario tomando como base las métricas de fabricación.</span><span class="sxs-lookup"><span data-stu-id="6849d-191">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="6849d-192">Instructor de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="6849d-192">Clustering trainer</span></span>

<span data-ttu-id="6849d-193">Puede entrenar un modelo de agrupación en clústeres mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="6849d-193">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer> 

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="6849d-194">Entradas y salidas de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="6849d-194">Clustering inputs and outputs</span></span>

<span data-ttu-id="6849d-195">Los datos de las características de entrada deben ser <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-195">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="6849d-196">No se necesita ninguna etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6849d-196">No labels are needed.</span></span>

<span data-ttu-id="6849d-197">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6849d-197">This trainer outputs the following:</span></span>

| <span data-ttu-id="6849d-198">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-198">Output Name</span></span> | <span data-ttu-id="6849d-199">Tipo</span><span class="sxs-lookup"><span data-stu-id="6849d-199">Type</span></span> | <span data-ttu-id="6849d-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-200">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="6849d-201">Vector de <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="6849d-201">vector of <xref:System.Single></span></span> | <span data-ttu-id="6849d-202">Las distancias de los datos especificados apuntan a todos los centroides de los clústeres</span><span class="sxs-lookup"><span data-stu-id="6849d-202">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="6849d-203">Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="6849d-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="6849d-204">El índice del clúster más cercano predicho por el modelo.</span><span class="sxs-lookup"><span data-stu-id="6849d-204">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="6849d-205">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="6849d-205">Anomaly detection</span></span>

<span data-ttu-id="6849d-206">Esta tarea crea un modelo de detección de anomalías mediante el uso de análisis de componentes principales (PCA).</span><span class="sxs-lookup"><span data-stu-id="6849d-206">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="6849d-207">La detección de anomalías basada en PCA le permite generar un modelo en escenarios donde resulta sencillo obtener datos de entrenamiento de una clase, como transacciones válidas, pero difícil obtener muestras suficientes de las anomalías de destino.</span><span class="sxs-lookup"><span data-stu-id="6849d-207">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="6849d-208">Una técnica establecida en aprendizaje automático, el PCA se suele usar en el análisis de datos exploratorios porque revela la estructura interna de los datos y explica la variación en los datos.</span><span class="sxs-lookup"><span data-stu-id="6849d-208">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="6849d-209">El PCA funciona analizando datos que contienen varias variables.</span><span class="sxs-lookup"><span data-stu-id="6849d-209">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="6849d-210">Busca correlaciones entre las variables y determina la combinación de valores que mejor recoge las diferencias en los resultados.</span><span class="sxs-lookup"><span data-stu-id="6849d-210">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="6849d-211">Estos valores de características combinados se usan para crear un espacio de características más compactas llamadas componentes principales.</span><span class="sxs-lookup"><span data-stu-id="6849d-211">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="6849d-212">La detección de anomalías engloba muchas tareas importantes de aprendizaje automático:</span><span class="sxs-lookup"><span data-stu-id="6849d-212">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="6849d-213">La identificación de transacciones potencialmente fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="6849d-213">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="6849d-214">El aprendizaje de patrones que indican que se ha producido una intrusión de red.</span><span class="sxs-lookup"><span data-stu-id="6849d-214">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="6849d-215">La búsqueda de clústeres anómalos de pacientes.</span><span class="sxs-lookup"><span data-stu-id="6849d-215">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="6849d-216">La comprobación de los valores especificados en un sistema.</span><span class="sxs-lookup"><span data-stu-id="6849d-216">Checking values entered into a system.</span></span>

<span data-ttu-id="6849d-217">Dado que las anomalías son eventos excepcionales por definición, puede ser difícil recopilar una muestra representativa de datos que usar en el modelado.</span><span class="sxs-lookup"><span data-stu-id="6849d-217">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="6849d-218">Los algoritmos que se incluyen en esta categoría se han diseñado especialmente para abordar los principales desafíos de compilar y entrenar modelos mediante el uso de conjuntos de datos desequilibrados.</span><span class="sxs-lookup"><span data-stu-id="6849d-218">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="6849d-219">Instructor de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="6849d-219">Anomaly detection trainer</span></span>

<span data-ttu-id="6849d-220">Puede entrenar un modelo de detección de anomalías mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="6849d-220">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="6849d-221">Salidas y entradas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="6849d-221">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="6849d-222">Las características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-222">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="6849d-223">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6849d-223">This trainer outputs the following:</span></span>

| <span data-ttu-id="6849d-224">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-224">Output Name</span></span> | <span data-ttu-id="6849d-225">Tipo</span><span class="sxs-lookup"><span data-stu-id="6849d-225">Type</span></span> | <span data-ttu-id="6849d-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-226">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="6849d-227">Puntuación no negativa sin enlazar que ha calculado el modelo de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="6849d-227">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="6849d-228">Clasificación</span><span class="sxs-lookup"><span data-stu-id="6849d-228">Ranking</span></span>

<span data-ttu-id="6849d-229">Una tarea de clasificación construye un clasificador a partir de un conjunto de ejemplos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="6849d-229">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="6849d-230">Este conjunto de ejemplos consta de grupos de instancias que se pueden puntuar con un criterio determinado.</span><span class="sxs-lookup"><span data-stu-id="6849d-230">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="6849d-231">Las etiquetas de clasificación son {0, 1, 2, 3, 4} para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="6849d-231">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="6849d-232">El clasificador está entrenado para clasificar nuevos grupos de instancias con puntuaciones desconocidas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="6849d-232">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="6849d-233">Los mecanismos de aprendizaje de clasificación de ML.NET se basan en la [clasificación aprendida automáticamente](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="6849d-233">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="6849d-234">Algoritmos de aprendizaje de clasificación</span><span class="sxs-lookup"><span data-stu-id="6849d-234">Ranking training algorithms</span></span>

<span data-ttu-id="6849d-235">Puede entrenar un modelo de clasificación mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6849d-235">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer> 

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="6849d-236">Salidas y entradas de clasificación</span><span class="sxs-lookup"><span data-stu-id="6849d-236">Ranking input and outputs</span></span>

<span data-ttu-id="6849d-237">El tipo de datos de la etiqueta de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6849d-237">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="6849d-238">El valor de la etiqueta determina la relevancia, donde los valores más altos indican mayor relevancia.</span><span class="sxs-lookup"><span data-stu-id="6849d-238">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="6849d-239">Si la etiqueta es de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType), entonces el índice de la clave es el valor de relevancia, donde el índice más pequeño es el menos relevante.</span><span class="sxs-lookup"><span data-stu-id="6849d-239">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="6849d-240">Si la etiqueta es un <xref:System.Single>, los valores mayores indican mayor relevancia.</span><span class="sxs-lookup"><span data-stu-id="6849d-240">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="6849d-241">Los datos de la característica deben ser un vector de tamaño fijo de <xref:System.Single> y la columna de grupo de filas de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="6849d-241">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="6849d-242">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6849d-242">This trainer outputs the following:</span></span>

| <span data-ttu-id="6849d-243">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="6849d-243">Output Name</span></span> | <span data-ttu-id="6849d-244">Tipo</span><span class="sxs-lookup"><span data-stu-id="6849d-244">Type</span></span> | <span data-ttu-id="6849d-245">Descripción</span><span class="sxs-lookup"><span data-stu-id="6849d-245">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="6849d-246">Puntuación sin enlazar que ha calculado el modelo para determinar la predicción</span><span class="sxs-lookup"><span data-stu-id="6849d-246">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="6849d-247">Recomendación</span><span class="sxs-lookup"><span data-stu-id="6849d-247">Recommendation</span></span>

<span data-ttu-id="6849d-248">Una tarea de recomendación permite generar una lista de productos o servicios recomendados.</span><span class="sxs-lookup"><span data-stu-id="6849d-248">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="6849d-249">ML.NET utiliza la [factorización matricial (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), un algoritmo de [filtrado de colaboración](https://en.wikipedia.org/wiki/Collaborative_filtering) de las recomendaciones cuando hay datos históricos de clasificación de productos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="6849d-249">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="6849d-250">Por ejemplo, tiene datos históricos de clasificación de películas para los usuarios y desea recomendar otras películas que puedan ver a continuación.</span><span class="sxs-lookup"><span data-stu-id="6849d-250">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="6849d-251">Algoritmos de aprendizaje de recomendación</span><span class="sxs-lookup"><span data-stu-id="6849d-251">Recommendation training algorithms</span></span>

<span data-ttu-id="6849d-252">Puede entrenar un modelo de recomendación mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="6849d-252">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
