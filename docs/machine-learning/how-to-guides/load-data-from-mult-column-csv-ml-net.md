---
title: 'Carga de datos con muchas columnas desde un archivo CSV para el procesamiento de aprendizaje automático: ML.NET'
description: Obtenga información sobre cómo cargar datos con muchas columnas a partir de un archivos CSV para usarlos en la creación, el entrenamiento y la puntuación de modelos de Machine Learning con ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: e33fdf1d71b02545e3ea284cc317f5d244c3fc13
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675958"
---
# <a name="load-data-with-many-columns-from-a-csv-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="a53b9-103">Carga de datos con muchas columnas desde un archivo CSV para el procesamiento de aprendizaje automático: ML.NET</span><span class="sxs-lookup"><span data-stu-id="a53b9-103">Load data with many columns from a CSV file for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="a53b9-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="a53b9-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a53b9-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a53b9-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a53b9-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a53b9-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="a53b9-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="a53b9-108">`TextLoader` se usa para cargar datos de archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="a53b9-108">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="a53b9-109">Necesita especificar las columnas de datos, sus tipos y su ubicación en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a53b9-109">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="a53b9-110">Cuando el archivo de entrada contenga muchas columnas del mismo tipo y siempre se usen juntas, léalas como una *columna de vectores*.</span><span class="sxs-lookup"><span data-stu-id="a53b9-110">When the input file contains many columns of the same type and always used together, read them as a *vector column*.</span></span> <span data-ttu-id="a53b9-111">Esta estrategia da como resultado un esquema de datos limpio y evita costos de rendimiento innecesarios, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a53b9-111">This strategy results in a clean data schema and avoids unnecessary performance costs, as shown in the following example:</span></span>

<span data-ttu-id="a53b9-112">[Archivo de ejemplo](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span><span class="sxs-lookup"><span data-stu-id="a53b9-112">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span></span>

```console
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
0.28;1.05;-0.24;0.30;-0.99;0.19;0.32;-0.95;-1.19;-0.63;0.75;443.51
```

<span data-ttu-id="a53b9-113">Leer este archivo mediante `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="a53b9-113">Reading this file using `TextLoader`:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
    // We read the first 10 values as a single float vector.
        new TextLoader.Column("FeatureVector",DataKind.R4,0,9),
        // Separately, read the target variable.
        new TextLoader.Column("Target",DataKind.R4,10)
    },
    // Default separator is tab, but we need a semicolon.
    separatorChar: ';',
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```    