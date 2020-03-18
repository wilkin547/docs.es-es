---
title: Aprendizaje automático automatizado con ML.NET
description: Introducción a la selección y el entrenamiento de modelos automáticos
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc, mlnet-tooling
ms.openlocfilehash: acd6cae71d2d5d79209a77d34175e7f1b3c1ee35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849359"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="c370a-103">Aprendizaje automático automatizado con ML.NET</span><span class="sxs-lookup"><span data-stu-id="c370a-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="c370a-104">El aprendizaje automático automatizado es una característica de ML.NET que realiza automáticamente el entrenamiento y la selección de modelos.</span><span class="sxs-lookup"><span data-stu-id="c370a-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="c370a-105">Especifique la tarea de aprendizaje automático y proporcione un conjunto de datos, y ML automatizado elegirá el modelo con las mejores métricas.</span><span class="sxs-lookup"><span data-stu-id="c370a-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="c370a-106">Se genera:</span><span class="sxs-lookup"><span data-stu-id="c370a-106">It outputs:</span></span>

- <span data-ttu-id="c370a-107">un archivo de modelo que se puede cargar en la aplicación de predicción</span><span class="sxs-lookup"><span data-stu-id="c370a-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="c370a-108">código de aplicación para realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="c370a-108">application code to make predictions</span></span>
- <span data-ttu-id="c370a-109">el código fuente que se usa para la selección de características y el entrenamiento del modelo (para comprender el modelo)</span><span class="sxs-lookup"><span data-stu-id="c370a-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="c370a-110">Esta característica se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="c370a-110">This feature is currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="c370a-111">El ML automatizado se limita actualmente a las [tareas](resources/tasks.md) de aprendizaje automático de clasificación binaria, clasificación multiclase y regresión.</span><span class="sxs-lookup"><span data-stu-id="c370a-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="c370a-112">Las demás tareas de aprendizaje automático se admitirán en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="c370a-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="c370a-113">Existen tres maneras de usar ML automatizado:</span><span class="sxs-lookup"><span data-stu-id="c370a-113">There are three ways to use automated ML:</span></span>

1. <span data-ttu-id="c370a-114">Con una interfaz gráfica de usuario, mediante el [compilador de modelos de ML.NET](automate-training-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="c370a-114">With a graphical user interface, with the [ML.NET Model Builder](automate-training-with-model-builder.md)</span></span>
1. <span data-ttu-id="c370a-115">En la línea de comandos, con la [CLI de ML.NET](automate-training-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="c370a-115">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="c370a-116">A través de una aplicación, con la [API automatizada de ML](how-to-guides/how-to-use-the-automl-api.md)</span><span class="sxs-lookup"><span data-stu-id="c370a-116">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>
