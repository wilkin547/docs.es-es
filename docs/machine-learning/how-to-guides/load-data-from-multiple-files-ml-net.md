---
title: 'Carga de datos de varios archivos para el procesamiento de aprendizaje automático: ML.NET'
description: Obtenga información acerca de cómo cargar datos de varios archivos para usarlos en la creación, entrenamiento y puntuación de modelos de Machine Learning con ML.NET.
ms.date: 01/29/2019
ms.custom: mvc,how-to
ms.openlocfilehash: fe6758e46d923dc07908e1334056ea8394c1085e
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479989"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a><span data-ttu-id="bf0d3-103">Carga de datos de varios archivos para el procesamiento de aprendizaje automático: ML.NET</span><span class="sxs-lookup"><span data-stu-id="bf0d3-103">Load data from multiple files for machine learning processing - ML.NET</span></span>

<span data-ttu-id="bf0d3-104">Use `TextLoader` y especifique una matriz de archivos para el método `Read`.</span><span class="sxs-lookup"><span data-stu-id="bf0d3-104">Use the `TextLoader`, and specify an array of files to the `Read` method.</span></span> <span data-ttu-id="bf0d3-105">Los archivos deben tener el mismo esquema (mismo número y tipo de columnas):</span><span class="sxs-lookup"><span data-stu-id="bf0d3-105">The files must have the same schema (same number and type of columns):</span></span>

* [<span data-ttu-id="bf0d3-106">Archivo de ejemplo1</span><span class="sxs-lookup"><span data-stu-id="bf0d3-106">Example file1</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [<span data-ttu-id="bf0d3-107">Archivo de ejemplo2</span><span class="sxs-lookup"><span data-stu-id="bf0d3-107">Example file2</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the files (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(exampleFile1, exampleFile2);
```