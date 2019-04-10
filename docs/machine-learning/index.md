---
title: Guía de contenido de ML.NET
description: Obtenga información sobre cómo compilar soluciones de IA personalizadas e integrarlas en las aplicaciones .NET mediante ML.NET.
ms.date: 04/05/2019
ms.custom: seodec18
ms.openlocfilehash: de681daea5a29a121d350271ced4ccc2c0b1b533
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231336"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="b36eb-103">Guía de contenido de ML.NET</span><span class="sxs-lookup"><span data-stu-id="b36eb-103">ML.NET Content Guide</span></span>

<span data-ttu-id="b36eb-104">En esta guía se explican los conceptos básicos y se proporcionan tutoriales y una referencia de API para trabajar con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b36eb-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="b36eb-105">Esta documentación hace referencia a ML.NET, que se encuentra actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b36eb-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="b36eb-106">El material puede estar sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="b36eb-106">Material may be subject to change.</span></span> <span data-ttu-id="b36eb-107">Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b36eb-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="b36eb-108">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="b36eb-108">Get started</span></span>

<span data-ttu-id="b36eb-109">Para instalar y empezar a compilar en ML.NET, siga el [tutorial de introducción](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span><span class="sxs-lookup"><span data-stu-id="b36eb-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="b36eb-110">Para aprender sobre ML.NET, consulte [¿Qué es ML.NET?](what-is-mldotnet.md)</span><span class="sxs-lookup"><span data-stu-id="b36eb-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="b36eb-111">Para comprender los conceptos básicos, consulte [Conceptos básicos del entrenamiento de modelos en ML.NET](basic-concepts-model-training-in-mldotnet.md).</span><span class="sxs-lookup"><span data-stu-id="b36eb-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="b36eb-112">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="b36eb-112">Tutorials</span></span>

<span data-ttu-id="b36eb-113">En [Análisis de opinión mediante un modelo de clasificación binario](./tutorials/sentiment-analysis.md) se muestra cómo compilar una aplicación que determina si la opinión es positiva o negativa.</span><span class="sxs-lookup"><span data-stu-id="b36eb-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="b36eb-114">En la [clasificación de problemas de GitHub mediante un modelo de clasificación multiclase](./tutorials/github-issue-classification.md) se le muestra cómo compilar una aplicación que determina la etiqueta de área para un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="b36eb-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="b36eb-115">En [Tutorial: Predicción de las tarifas de taxi de Nueva York mediante un aprendiz de regresión con ML.NET](./tutorials/taxi-fare.md) se muestra cómo compilar una aplicación predictiva que utiliza muchos factores de los datos históricos para determinar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b36eb-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="b36eb-116">En [Clasificar flores de iris mediante características](./tutorials/iris-clustering.md) se muestra cómo usar un modelo de agrupación en clústeres para analizar el conjunto de datos de iris.</span><span class="sxs-lookup"><span data-stu-id="b36eb-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span>

<span data-ttu-id="b36eb-117">[Creación de un recomendador de películas con ML.NET](./tutorials/movie-recommmendation.md) muestra cómo crear una aplicación de recomendación para recomendar películas a los usuarios en función de su historial.</span><span class="sxs-lookup"><span data-stu-id="b36eb-117">[Create a Movie Recommender with ML.NET](./tutorials/movie-recommmendation.md) shows you how to build a recommendation app to recommend movies to users based on their history.</span></span>

<span data-ttu-id="b36eb-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md) (Creación de un clasificador de imágenes personalizado de ML.NET con TensorFlow): muestra cómo volver a entrenar un modelo de TensorFlow para crear un clasificador de imágenes personalizado mediante ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b36eb-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md): demonstrates how to retrain an existing Tensorflow model to create a custom image classifier using ML.NET.</span></span>

## <a name="how-to-guide"></a><span data-ttu-id="b36eb-119">Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="b36eb-119">How to guide</span></span>

<span data-ttu-id="b36eb-120">En [Creación de una aplicación de listas de enfrentamientos en juegos con Infer.NET y programación probabilística](./how-to-guides/matchup-app-infer-net.md) se muestra cómo compilar una versión simplificada de una aplicación de emparejamiento, como vería en un juego de Xbox.</span><span class="sxs-lookup"><span data-stu-id="b36eb-120">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="b36eb-121">Recursos</span><span class="sxs-lookup"><span data-stu-id="b36eb-121">Resources</span></span>

<span data-ttu-id="b36eb-122">En el [Glosario de aprendizaje automático](./resources/glossary.md) se define la terminología clave.</span><span class="sxs-lookup"><span data-stu-id="b36eb-122">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="b36eb-123">En [Tareas de aprendizaje automático](./resources/tasks.md) se describen tareas, como la clasificación y detección de anomalías.</span><span class="sxs-lookup"><span data-stu-id="b36eb-123">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="b36eb-124">En [Transformaciones de datos](./resources/transforms.md) se describen las funcionalidades de preparación de datos en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="b36eb-124">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>

## <a name="api-reference"></a><span data-ttu-id="b36eb-125">referencia de API</span><span class="sxs-lookup"><span data-stu-id="b36eb-125">API reference</span></span>

<span data-ttu-id="b36eb-126">En [Referencia de API ML.NET](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) se describen las diversas API disponibles.</span><span class="sxs-lookup"><span data-stu-id="b36eb-126">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
