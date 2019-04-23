---
title: 'Tareas de aprendizaje automático: ML.NET'
description: Explore las diferentes tareas de aprendizaje automático y las tareas asociadas que se admiten en ML.NET.
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613166"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="bc8d1-103">Tareas de aprendizaje automático en ML.NET</span><span class="sxs-lookup"><span data-stu-id="bc8d1-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="bc8d1-104">Cuando se crea un modelo de aprendizaje automático, primero debe definir lo que espera lograr con sus datos.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="bc8d1-105">Esto le permite elegir la tarea de aprendizaje de automático adecuada para su situación.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="bc8d1-106">La siguiente lista describe las diferentes tareas de aprendizaje automático que puede elegir y algunos casos de uso comunes.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="bc8d1-107">Cuando haya decidido qué tarea funciona en su escenario, debe elegir el mejor algoritmo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="bc8d1-108">Los algoritmos disponibles se muestran en la sección correspondiente a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="bc8d1-109">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="bc8d1-109">Binary classification</span></span>

<span data-ttu-id="bc8d1-110">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="bc8d1-111">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="bc8d1-112">El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="bc8d1-113">Entre los ejemplos de escenarios de clasificación binaria están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="bc8d1-114">[Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".</span><span class="sxs-lookup"><span data-stu-id="bc8d1-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="bc8d1-115">Diagnosticar si un paciente tiene una determinada enfermedad o no.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="bc8d1-116">Tomar una decisión para marcar un correo electrónico como no deseado o no.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="bc8d1-117">Determinar si una foto contiene un perro o una fruta.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="bc8d1-118">Para obtener más información, consulte el artículo de Wikipedia [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) (Clasificación binaria).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="bc8d1-119">Algoritmos de aprendizaje de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="bc8d1-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="bc8d1-120">Puede entrenar un modelo de clasificación binaria mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="bc8d1-121">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="bc8d1-121">Multiclass classification</span></span>

<span data-ttu-id="bc8d1-122">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="bc8d1-123">La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="bc8d1-124">Cada etiqueta se inicia normalmente como texto.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-124">Each label normally starts as text.</span></span> <span data-ttu-id="bc8d1-125">Luego se ejecuta mediante TermTransform, que lo convierte al tipo de clave (numérico).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="bc8d1-126">El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="bc8d1-127">Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="bc8d1-128">Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="bc8d1-129">Comprender las críticas de películas como "positivas", "neutrales" o "negativas".</span><span class="sxs-lookup"><span data-stu-id="bc8d1-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="bc8d1-130">Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="bc8d1-131">Para obtener más información, consulte el artículo de Wikipedia [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) (Clasificación multiclase).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="bc8d1-132">Uno frente a todos actualiza los [mecanismos de aprendizaje de clasificación binaria](#binary-classification) para que actúen en conjuntos de datos multiclase.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="bc8d1-133">Obtenga más información sobre [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="bc8d1-134">Algoritmos de aprendizaje de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="bc8d1-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="bc8d1-135">Puede entrenar un modelo de clasificación multiclase mediante los siguientes algoritmos de aprendizaje:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="bc8d1-136">Regresión</span><span class="sxs-lookup"><span data-stu-id="bc8d1-136">Regression</span></span>

<span data-ttu-id="bc8d1-137">Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="bc8d1-138">La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="bc8d1-139">Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="bc8d1-140">La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="bc8d1-141">El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="bc8d1-142">Estos son algunos ejemplos de escenarios de regresión:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="bc8d1-143">Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="bc8d1-144">Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="bc8d1-145">Predecir las ventas de un producto en función del presupuesto para publicidad.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="bc8d1-146">Algoritmos de aprendizaje de regresión</span><span class="sxs-lookup"><span data-stu-id="bc8d1-146">Regression training algorithms</span></span>

<span data-ttu-id="bc8d1-147">Puede entrenar un modelo de regresión mediante los siguientes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="bc8d1-148">Agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="bc8d1-148">Clustering</span></span>

<span data-ttu-id="bc8d1-149">Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="bc8d1-150">La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="bc8d1-151">Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="bc8d1-152">Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="bc8d1-153">ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="bc8d1-154">Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="bc8d1-155">Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="bc8d1-156">Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="bc8d1-157">Categorizar un inventario tomando como base las métricas de fabricación.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="bc8d1-158">Algoritmos de aprendizaje de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="bc8d1-158">Clustering training algorithms</span></span>

<span data-ttu-id="bc8d1-159">Puede entrenar un modelo de agrupación en clústeres mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="bc8d1-160">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="bc8d1-160">Anomaly detection</span></span>

<span data-ttu-id="bc8d1-161">Esta tarea crea un modelo de detección de anomalías mediante el uso de análisis de componentes principales (PCA).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="bc8d1-162">La detección de anomalías basada en PCA le permite generar un modelo en escenarios donde resulta sencillo obtener datos de entrenamiento de una clase, como transacciones válidas, pero difícil obtener muestras suficientes de las anomalías de destino.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="bc8d1-163">Una técnica establecida en aprendizaje automático, el PCA se suele usar en el análisis de datos exploratorios porque revela la estructura interna de los datos y explica la variación en los datos.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="bc8d1-164">El PCA funciona analizando datos que contienen varias variables.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="bc8d1-165">Busca correlaciones entre las variables y determina la combinación de valores que mejor recoge las diferencias en los resultados.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="bc8d1-166">Estos valores de características combinados se usan para crear un espacio de características más compactas llamadas componentes principales.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="bc8d1-167">La detección de anomalías engloba muchas tareas importantes de aprendizaje automático:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="bc8d1-168">La identificación de transacciones potencialmente fraudulentas.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="bc8d1-169">El aprendizaje de patrones que indican que se ha producido una intrusión de red.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="bc8d1-170">La búsqueda de clústeres anómalos de pacientes.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="bc8d1-171">La comprobación de los valores especificados en un sistema.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-171">Checking values entered into a system.</span></span>

<span data-ttu-id="bc8d1-172">Dado que las anomalías son eventos excepcionales por definición, puede ser difícil recopilar una muestra representativa de datos que usar en el modelado.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="bc8d1-173">Los algoritmos que se incluyen en esta categoría se han diseñado especialmente para abordar los principales desafíos de compilar y entrenar modelos mediante el uso de conjuntos de datos desequilibrados.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="bc8d1-174">Algoritmos de aprendizaje de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="bc8d1-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="bc8d1-175">Puede entrenar un modelo de detección de anomalías mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="bc8d1-176">Clasificación</span><span class="sxs-lookup"><span data-stu-id="bc8d1-176">Ranking</span></span>

<span data-ttu-id="bc8d1-177">Una tarea de clasificación construye un clasificador a partir de un conjunto de ejemplos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="bc8d1-178">Este conjunto de ejemplos consta de grupos de instancias que se pueden puntuar con un criterio determinado.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="bc8d1-179">Las etiquetas de clasificación son {0, 1, 2, 3, 4} para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="bc8d1-180">El clasificador está entrenado para clasificar nuevos grupos de instancias con puntuaciones desconocidas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="bc8d1-181">Los mecanismos de aprendizaje de clasificación de ML.NET se basan en la [clasificación aprendida automáticamente](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="bc8d1-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="bc8d1-182">Algoritmos de aprendizaje de clasificación</span><span class="sxs-lookup"><span data-stu-id="bc8d1-182">Ranking training algorithms</span></span>

<span data-ttu-id="bc8d1-183">Puede entrenar un modelo de clasificación mediante los algoritmos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="bc8d1-184">Recomendación</span><span class="sxs-lookup"><span data-stu-id="bc8d1-184">Recommendation</span></span>

<span data-ttu-id="bc8d1-185">Una tarea de recomendación permite generar una lista de productos o servicios recomendados.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="bc8d1-186">ML.NET utiliza la [factorización matricial (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), un algoritmo de [filtrado de colaboración](https://en.wikipedia.org/wiki/Collaborative_filtering) de las recomendaciones cuando hay datos históricos de clasificación de productos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="bc8d1-187">Por ejemplo, tiene datos históricos de clasificación de películas para los usuarios y desea recomendar otras películas que puedan ver a continuación.</span><span class="sxs-lookup"><span data-stu-id="bc8d1-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="bc8d1-188">Algoritmos de aprendizaje de recomendación</span><span class="sxs-lookup"><span data-stu-id="bc8d1-188">Recommendation training algorithms</span></span>

<span data-ttu-id="bc8d1-189">Puede entrenar un modelo de recomendación mediante el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="bc8d1-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
