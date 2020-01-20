---
title: Tareas de aprendizaje automático
description: Explore las diferentes tareas de aprendizaje automático y las tareas asociadas que se admiten en ML.NET.
ms.date: 12/23/2019
ms.openlocfilehash: badb096ab3e7fbd575d8594b4fbd0e2ebaf63820
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739626"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="aca5d-103">Tareas de aprendizaje automático en ML.NET</span><span class="sxs-lookup"><span data-stu-id="aca5d-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="aca5d-104">Una tarea de aprendizaje automático es el tipo de predicción o inferencia que se está realizando, en función del problema o la pregunta que se está formulando, y los datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="aca5d-104">A machine learning task is the type of prediction or inference being made, based on the problem or question that is being asked, and the available data.</span></span> <span data-ttu-id="aca5d-105">Por ejemplo, la tarea de clasificación asigna datos a categorías y la tarea de agrupación en clústeres agrupa datos según su similitud.</span><span class="sxs-lookup"><span data-stu-id="aca5d-105">For example, the classification task assigns data to categories, and the clustering task groups data according to similarity.</span></span>

<span data-ttu-id="aca5d-106">Las tareas de aprendizaje automático se basan en patrones de los datos en lugar de programarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="aca5d-106">Machine learning tasks rely on patterns in the data rather than being explicitly programmed.</span></span>

<span data-ttu-id="aca5d-107">En este artículo se describen las diferentes tareas de aprendizaje automático que puede elegir en ML.NET y algunos casos de uso comunes.</span><span class="sxs-lookup"><span data-stu-id="aca5d-107">This article describes the different machine learning tasks that you can choose from in ML.NET and some common use cases.</span></span>

<span data-ttu-id="aca5d-108">Cuando haya decidido qué tarea funciona en su escenario, debe elegir el mejor algoritmo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="aca5d-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="aca5d-109">Los algoritmos disponibles se muestran en la sección correspondiente a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="aca5d-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="aca5d-110">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="aca5d-110">Binary classification</span></span>

<span data-ttu-id="aca5d-111">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="aca5d-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="aca5d-112">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="aca5d-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="aca5d-113">El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aca5d-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="aca5d-114">Entre los ejemplos de escenarios de clasificación binaria están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="aca5d-115">[Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".</span><span class="sxs-lookup"><span data-stu-id="aca5d-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="aca5d-116">Diagnosticar si un paciente tiene una determinada enfermedad o no.</span><span class="sxs-lookup"><span data-stu-id="aca5d-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="aca5d-117">Tomar una decisión para marcar un correo electrónico como no deseado o no.</span><span class="sxs-lookup"><span data-stu-id="aca5d-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="aca5d-118">Determinar si una fotografía contiene un elemento determinado o no, como un perro o una fruta.</span><span class="sxs-lookup"><span data-stu-id="aca5d-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="aca5d-119">Para obtener más información, consulte el artículo de Wikipedia [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) (Clasificación binaria).</span><span class="sxs-lookup"><span data-stu-id="aca5d-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="aca5d-120">Instructores de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="aca5d-120">Binary classification trainers</span></span>

<span data-ttu-id="aca5d-121">Puede entrenar un modelo de clasificación binaria mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-121">You can train a binary classification model using the following algorithms:</span></span>

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

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="aca5d-122">Entradas y salidas de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="aca5d-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="aca5d-123">Para obtener los mejores resultados con la clasificación binaria, los datos de entrenamiento deben estar equilibrados (es decir, igual número de datos de entrenamiento positivos y negativos).</span><span class="sxs-lookup"><span data-stu-id="aca5d-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="aca5d-124">Los valores que faltan se deben controlar antes del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="aca5d-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="aca5d-125">Los datos de la columna de etiquetas de entrada deben ser <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="aca5d-126">Los datos de la columna de características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="aca5d-127">Estos instructores generan las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="aca5d-128">Nombre de columna de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-128">Output Column Name</span></span> | <span data-ttu-id="aca5d-129">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="aca5d-129">Column Type</span></span> | <span data-ttu-id="aca5d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="aca5d-131">Puntuación sin procesar calculada por el modelo</span><span class="sxs-lookup"><span data-stu-id="aca5d-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="aca5d-132">Etiqueta de predicción, según el signo de la puntuación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="aca5d-133">Una puntuación negativa se asigna a `false` y una positiva a `true`.</span><span class="sxs-lookup"><span data-stu-id="aca5d-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="aca5d-134">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="aca5d-134">Multiclass classification</span></span>

<span data-ttu-id="aca5d-135">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="aca5d-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="aca5d-136">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aca5d-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="aca5d-137">Cada etiqueta se inicia normalmente como texto.</span><span class="sxs-lookup"><span data-stu-id="aca5d-137">Each label normally starts as text.</span></span> <span data-ttu-id="aca5d-138">Luego se ejecuta mediante TermTransform, que lo convierte al tipo de clave (numérico).</span><span class="sxs-lookup"><span data-stu-id="aca5d-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="aca5d-139">El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aca5d-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="aca5d-140">Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="aca5d-141">Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.</span><span class="sxs-lookup"><span data-stu-id="aca5d-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="aca5d-142">Comprender las críticas de películas como "positivas", "neutrales" o "negativas".</span><span class="sxs-lookup"><span data-stu-id="aca5d-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="aca5d-143">Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.</span><span class="sxs-lookup"><span data-stu-id="aca5d-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="aca5d-144">Para obtener más información, consulte el artículo de Wikipedia [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) (Clasificación multiclase).</span><span class="sxs-lookup"><span data-stu-id="aca5d-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="aca5d-145">Uno frente a todos actualiza los [mecanismos de aprendizaje de clasificación binaria](#binary-classification) para que actúen en conjuntos de datos multiclase.</span><span class="sxs-lookup"><span data-stu-id="aca5d-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="aca5d-146">Obtenga más información sobre [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="aca5d-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="aca5d-147">Instructores de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="aca5d-147">Multiclass classification trainers</span></span>

<span data-ttu-id="aca5d-148">Puede entrenar un modelo de clasificación multiclase mediante los siguientes algoritmos de aprendizaje:</span><span class="sxs-lookup"><span data-stu-id="aca5d-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="aca5d-149">Entradas y salidas de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="aca5d-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="aca5d-150">Los datos de la columna de etiquetas de entrada deben ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="aca5d-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="aca5d-151">La columna de características debe ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="aca5d-152">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca5d-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="aca5d-153">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-153">Output Name</span></span> | <span data-ttu-id="aca5d-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca5d-154">Type</span></span> | <span data-ttu-id="aca5d-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="aca5d-156">Vector de <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="aca5d-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="aca5d-157">Puntuaciones de todas las clases.</span><span class="sxs-lookup"><span data-stu-id="aca5d-157">The scores of all classes.</span></span> <span data-ttu-id="aca5d-158">Un valor más alto indica mayor probabilidad de que caigan en la clase asociada.</span><span class="sxs-lookup"><span data-stu-id="aca5d-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="aca5d-159">Si el elemento i-th tiene el valor más grande, el índice de la etiqueta de predicción sería i.</span><span class="sxs-lookup"><span data-stu-id="aca5d-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="aca5d-160">Tenga en cuenta que i es el índice de base cero.</span><span class="sxs-lookup"><span data-stu-id="aca5d-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="aca5d-161">Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="aca5d-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="aca5d-162">Índice de la etiqueta de predicción.</span><span class="sxs-lookup"><span data-stu-id="aca5d-162">The predicted label's index.</span></span> <span data-ttu-id="aca5d-163">Si su valor es i, la etiqueta real sería la categoría de i-th en el tipo de etiqueta de entrada con valores de clave.</span><span class="sxs-lookup"><span data-stu-id="aca5d-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="aca5d-164">Regresión</span><span class="sxs-lookup"><span data-stu-id="aca5d-164">Regression</span></span>

<span data-ttu-id="aca5d-165">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas.</span><span class="sxs-lookup"><span data-stu-id="aca5d-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="aca5d-166">La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="aca5d-167">Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características.</span><span class="sxs-lookup"><span data-stu-id="aca5d-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="aca5d-168">La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos.</span><span class="sxs-lookup"><span data-stu-id="aca5d-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="aca5d-169">El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada.</span><span class="sxs-lookup"><span data-stu-id="aca5d-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="aca5d-170">Estos son algunos ejemplos de escenarios de regresión:</span><span class="sxs-lookup"><span data-stu-id="aca5d-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="aca5d-171">Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.</span><span class="sxs-lookup"><span data-stu-id="aca5d-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="aca5d-172">Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.</span><span class="sxs-lookup"><span data-stu-id="aca5d-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="aca5d-173">Predecir las ventas de un producto en función del presupuesto para publicidad.</span><span class="sxs-lookup"><span data-stu-id="aca5d-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="aca5d-174">Instructores de regresión</span><span class="sxs-lookup"><span data-stu-id="aca5d-174">Regression trainers</span></span>

<span data-ttu-id="aca5d-175">Puede entrenar un modelo de regresión mediante los siguientes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="aca5d-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="aca5d-176">Entradas y salidas de regresión</span><span class="sxs-lookup"><span data-stu-id="aca5d-176">Regression inputs and outputs</span></span>

<span data-ttu-id="aca5d-177">Los datos de la columna de etiquetas de entrada deben ser <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="aca5d-178">Los instructores para esta tarea producen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca5d-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="aca5d-179">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-179">Output Name</span></span> | <span data-ttu-id="aca5d-180">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca5d-180">Type</span></span> | <span data-ttu-id="aca5d-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="aca5d-182">Puntuación sin procesar que el modelo predijo</span><span class="sxs-lookup"><span data-stu-id="aca5d-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="aca5d-183">Agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="aca5d-183">Clustering</span></span>

<span data-ttu-id="aca5d-184">Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares.</span><span class="sxs-lookup"><span data-stu-id="aca5d-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="aca5d-185">La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="aca5d-186">Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida.</span><span class="sxs-lookup"><span data-stu-id="aca5d-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="aca5d-187">Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad.</span><span class="sxs-lookup"><span data-stu-id="aca5d-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="aca5d-188">ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means.</span><span class="sxs-lookup"><span data-stu-id="aca5d-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="aca5d-189">Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="aca5d-190">Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.</span><span class="sxs-lookup"><span data-stu-id="aca5d-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="aca5d-191">Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.</span><span class="sxs-lookup"><span data-stu-id="aca5d-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="aca5d-192">Categorizar un inventario tomando como base las métricas de fabricación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="aca5d-193">Instructor de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="aca5d-193">Clustering trainer</span></span>

<span data-ttu-id="aca5d-194">Puede entrenar un modelo de agrupación en clústeres mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="aca5d-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="aca5d-195">Entradas y salidas de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="aca5d-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="aca5d-196">Los datos de las características de entrada deben ser <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="aca5d-197">No se necesita ninguna etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aca5d-197">No labels are needed.</span></span>

<span data-ttu-id="aca5d-198">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca5d-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="aca5d-199">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-199">Output Name</span></span> | <span data-ttu-id="aca5d-200">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca5d-200">Type</span></span> | <span data-ttu-id="aca5d-201">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="aca5d-202">Vector de <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="aca5d-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="aca5d-203">Las distancias de los datos especificados apuntan a todos los centroides de los clústeres</span><span class="sxs-lookup"><span data-stu-id="aca5d-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="aca5d-204">Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="aca5d-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="aca5d-205">El índice del clúster más cercano predicho por el modelo.</span><span class="sxs-lookup"><span data-stu-id="aca5d-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="aca5d-206">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="aca5d-206">Anomaly detection</span></span>

<span data-ttu-id="aca5d-207">Esta tarea crea un modelo de detección de anomalías mediante el uso de análisis de componentes principales (PCA).</span><span class="sxs-lookup"><span data-stu-id="aca5d-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="aca5d-208">La detección de anomalías basada en PCA le permite generar un modelo en escenarios donde resulta sencillo obtener datos de entrenamiento de una clase, como transacciones válidas, pero difícil obtener muestras suficientes de las anomalías de destino.</span><span class="sxs-lookup"><span data-stu-id="aca5d-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="aca5d-209">Una técnica establecida en aprendizaje automático, el PCA se suele usar en el análisis de datos exploratorios porque revela la estructura interna de los datos y explica la variación en los datos.</span><span class="sxs-lookup"><span data-stu-id="aca5d-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="aca5d-210">El PCA funciona analizando datos que contienen varias variables.</span><span class="sxs-lookup"><span data-stu-id="aca5d-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="aca5d-211">Busca correlaciones entre las variables y determina la combinación de valores que mejor recoge las diferencias en los resultados.</span><span class="sxs-lookup"><span data-stu-id="aca5d-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="aca5d-212">Estos valores de características combinados se usan para crear un espacio de características más compactas llamadas componentes principales.</span><span class="sxs-lookup"><span data-stu-id="aca5d-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="aca5d-213">La detección de anomalías engloba muchas tareas importantes de aprendizaje automático:</span><span class="sxs-lookup"><span data-stu-id="aca5d-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="aca5d-214">La identificación de transacciones potencialmente fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="aca5d-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="aca5d-215">El aprendizaje de patrones que indican que se ha producido una intrusión de red.</span><span class="sxs-lookup"><span data-stu-id="aca5d-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="aca5d-216">La búsqueda de clústeres anómalos de pacientes.</span><span class="sxs-lookup"><span data-stu-id="aca5d-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="aca5d-217">La comprobación de los valores especificados en un sistema.</span><span class="sxs-lookup"><span data-stu-id="aca5d-217">Checking values entered into a system.</span></span>

<span data-ttu-id="aca5d-218">Dado que las anomalías son eventos excepcionales por definición, puede ser difícil recopilar una muestra representativa de datos que usar en el modelado.</span><span class="sxs-lookup"><span data-stu-id="aca5d-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="aca5d-219">Los algoritmos que se incluyen en esta categoría se han diseñado especialmente para abordar los principales desafíos de compilar y entrenar modelos mediante el uso de conjuntos de datos desequilibrados.</span><span class="sxs-lookup"><span data-stu-id="aca5d-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="aca5d-220">Instructor de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="aca5d-220">Anomaly detection trainer</span></span>

<span data-ttu-id="aca5d-221">Puede entrenar un modelo de detección de anomalías mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="aca5d-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="aca5d-222">Salidas y entradas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="aca5d-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="aca5d-223">Las características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="aca5d-224">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca5d-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="aca5d-225">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-225">Output Name</span></span> | <span data-ttu-id="aca5d-226">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca5d-226">Type</span></span> | <span data-ttu-id="aca5d-227">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="aca5d-228">Puntuación no negativa sin enlazar que ha calculado el modelo de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="aca5d-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="aca5d-229">Un valor true o false que representa si la entrada es una anomalía (PredictedLabel=true) o no (PredictedLabel=false)</span><span class="sxs-lookup"><span data-stu-id="aca5d-229">A true/false value representing whether the input is an anomaly (PredictedLabel=true) or not (PredictedLabel=false)</span></span> |

## <a name="ranking"></a><span data-ttu-id="aca5d-230">Clasificación</span><span class="sxs-lookup"><span data-stu-id="aca5d-230">Ranking</span></span>

<span data-ttu-id="aca5d-231">Una tarea de clasificación construye un clasificador a partir de un conjunto de ejemplos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="aca5d-231">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="aca5d-232">Este conjunto de ejemplos consta de grupos de instancias que se pueden puntuar con un criterio determinado.</span><span class="sxs-lookup"><span data-stu-id="aca5d-232">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="aca5d-233">Las etiquetas de clasificación son {0, 1, 2, 3, 4} para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="aca5d-233">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="aca5d-234">El clasificador está entrenado para clasificar nuevos grupos de instancias con puntuaciones desconocidas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="aca5d-234">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="aca5d-235">Los mecanismos de aprendizaje de clasificación de ML.NET se basan en la [clasificación aprendida automáticamente](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="aca5d-235">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="aca5d-236">Algoritmos de aprendizaje de clasificación</span><span class="sxs-lookup"><span data-stu-id="aca5d-236">Ranking training algorithms</span></span>

<span data-ttu-id="aca5d-237">Puede entrenar un modelo de clasificación mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca5d-237">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="aca5d-238">Salidas y entradas de clasificación</span><span class="sxs-lookup"><span data-stu-id="aca5d-238">Ranking input and outputs</span></span>

<span data-ttu-id="aca5d-239">El tipo de datos de la etiqueta de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="aca5d-239">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="aca5d-240">El valor de la etiqueta determina la relevancia, donde los valores más altos indican mayor relevancia.</span><span class="sxs-lookup"><span data-stu-id="aca5d-240">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="aca5d-241">Si la etiqueta es de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType), entonces el índice de la clave es el valor de relevancia, donde el índice más pequeño es el menos relevante.</span><span class="sxs-lookup"><span data-stu-id="aca5d-241">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="aca5d-242">Si la etiqueta es un <xref:System.Single>, los valores mayores indican mayor relevancia.</span><span class="sxs-lookup"><span data-stu-id="aca5d-242">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="aca5d-243">Los datos de la característica deben ser un vector de tamaño fijo de <xref:System.Single> y la columna de grupo de filas de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="aca5d-243">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="aca5d-244">Este instructor produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca5d-244">This trainer outputs the following:</span></span>

| <span data-ttu-id="aca5d-245">Nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="aca5d-245">Output Name</span></span> | <span data-ttu-id="aca5d-246">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca5d-246">Type</span></span> | <span data-ttu-id="aca5d-247">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca5d-247">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="aca5d-248">Puntuación sin enlazar que ha calculado el modelo para determinar la predicción</span><span class="sxs-lookup"><span data-stu-id="aca5d-248">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="aca5d-249">Recomendación</span><span class="sxs-lookup"><span data-stu-id="aca5d-249">Recommendation</span></span>

<span data-ttu-id="aca5d-250">Una tarea de recomendación permite generar una lista de productos o servicios recomendados.</span><span class="sxs-lookup"><span data-stu-id="aca5d-250">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="aca5d-251">ML.NET utiliza la [factorización matricial (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), un algoritmo de [filtrado de colaboración](https://en.wikipedia.org/wiki/Collaborative_filtering) de las recomendaciones cuando hay datos históricos de clasificación de productos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="aca5d-251">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="aca5d-252">Por ejemplo, tiene datos históricos de clasificación de películas para los usuarios y desea recomendar otras películas que puedan ver a continuación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-252">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="aca5d-253">Algoritmos de aprendizaje de recomendación</span><span class="sxs-lookup"><span data-stu-id="aca5d-253">Recommendation training algorithms</span></span>

<span data-ttu-id="aca5d-254">Puede entrenar un modelo de recomendación mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="aca5d-254">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
