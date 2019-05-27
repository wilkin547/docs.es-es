---
title: Carga de datos
description: Carga de archivos de datos y datos de transmisión en ML.NET
ms.date: 05/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6edcc92b610e2e1f5e21c371b9f0aefd0b216d31
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063644"
---
# <a name="load-data-from-file-and-in-memory-sources"></a><span data-ttu-id="c4e15-103">Carga de datos desde orígenes de archivo y en memoria</span><span class="sxs-lookup"><span data-stu-id="c4e15-103">Load data from file and in-memory sources</span></span>

<span data-ttu-id="c4e15-104">Este procedimiento muestra cómo cargar datos para su procesamiento y entrenamiento en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c4e15-104">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="c4e15-105">Los datos se almacenan originalmente en archivos u orígenes de datos de transmisión o en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="c4e15-105">The data is originally stored in files or real-time / streaming data sources.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="c4e15-106">Crear el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="c4e15-106">Create the data model</span></span>

<span data-ttu-id="c4e15-107">ML.NET permite definir los modelos de datos mediante clases.</span><span class="sxs-lookup"><span data-stu-id="c4e15-107">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="c4e15-108">Por ejemplo, dado los siguientes datos de entrada:</span><span class="sxs-lookup"><span data-stu-id="c4e15-108">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="c4e15-109">Cree un modelo de datos que represente el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4e15-109">Create a data model that represents the snippet below:</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="c4e15-110">Anotar el modelo de datos con atributos de columna</span><span class="sxs-lookup"><span data-stu-id="c4e15-110">Annotating the data model with column attributes</span></span>

<span data-ttu-id="c4e15-111">Los atributos proporcionan a ML.NET más información sobre el modelo de datos y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c4e15-111">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="c4e15-112">El atributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) especifica los índices de columna de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c4e15-112">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4e15-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) solo es necesario cuando se cargan datos desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="c4e15-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="c4e15-114">Cargar columnas como:</span><span class="sxs-lookup"><span data-stu-id="c4e15-114">Load columns as:</span></span> 
- <span data-ttu-id="c4e15-115">Columnas individuales como `Size` y `CurrentPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="c4e15-115">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="c4e15-116">Varias columnas a la vez en forma de un vector como `HistoricalPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="c4e15-116">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="c4e15-117">Si tiene una propiedad de vector, aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) a la propiedad en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="c4e15-117">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="c4e15-118">Es importante tener en cuenta que todos los elementos del vector deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="c4e15-118">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="c4e15-119">ML.NET funciona a través de los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="c4e15-119">ML.NET Operates through column names.</span></span> <span data-ttu-id="c4e15-120">Si desea cambiar el nombre de una columna a otro nombre que no sea el de la propiedad, utilice el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="c4e15-120">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="c4e15-121">Al crear objetos en memoria, debe crear todavía objetos mediante el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4e15-121">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="c4e15-122">Sin embargo, para el procesamiento de datos y la compilación de modelos de aprendizaje automático, ML.NET invalida la propiedad y hace referencia a esta con el valor proporcionado en el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="c4e15-122">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="c4e15-123">Carga de datos desde un archivo único</span><span class="sxs-lookup"><span data-stu-id="c4e15-123">Load data from a single file</span></span>

<span data-ttu-id="c4e15-124">Para cargar datos desde un archivo, utilice el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) junto con el modelo de datos para que se carguen los datos.</span><span class="sxs-lookup"><span data-stu-id="c4e15-124">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="c4e15-125">Puesto que el parámetro `separatorChar` está delimitado por tabulaciones de forma predeterminada, cámbielo para el archivo de datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c4e15-125">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="c4e15-126">Si el archivo tiene un encabezado, establezca el parámetro `hasHeader` en `true` para omitir la primera línea en el archivo y comenzar a cargar datos de la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="c4e15-126">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="c4e15-127">Carga de datos de varios archivos</span><span class="sxs-lookup"><span data-stu-id="c4e15-127">Load data from multiple files</span></span>

<span data-ttu-id="c4e15-128">En caso de que los datos se almacenen en varios archivos, siempre y cuando el esquema de datos sea el mismo, ML.NET permite cargar datos desde varios archivos que están en el mismo directorio o en varios directorios.</span><span class="sxs-lookup"><span data-stu-id="c4e15-128">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="c4e15-129">Carga de archivos en un único directorio</span><span class="sxs-lookup"><span data-stu-id="c4e15-129">Load from files in a single directory</span></span>

<span data-ttu-id="c4e15-130">Cuando todos los archivos de datos se encuentran en el mismo directorio, utilice caracteres comodín en el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).</span><span class="sxs-lookup"><span data-stu-id="c4e15-130">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="c4e15-131">Carga de archivos en varios directorios</span><span class="sxs-lookup"><span data-stu-id="c4e15-131">Load from files in multiple directories</span></span>

<span data-ttu-id="c4e15-132">Para cargar datos desde varios directorios, utilice el método [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) para crear un [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="c4e15-132">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="c4e15-133">A continuación, utilice el método [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) y especifique las rutas de acceso de archivo individuales (no se pueden usar caracteres comodín).</span><span class="sxs-lookup"><span data-stu-id="c4e15-133">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a><span data-ttu-id="c4e15-134">Carga de datos desde un origen de transmisión</span><span class="sxs-lookup"><span data-stu-id="c4e15-134">Load data from a streaming source</span></span>

<span data-ttu-id="c4e15-135">Además de cargar los datos almacenados en disco, ML.NET admite la carga de datos desde diversos orígenes de transmisión, entre los que se incluyen, aunque sin carácter restrictivo:</span><span class="sxs-lookup"><span data-stu-id="c4e15-135">In addition to loading data stored on disk, ML.NET supports loading data from various streaming sources that include but are not limited to:</span></span>

- <span data-ttu-id="c4e15-136">Colecciones en memoria</span><span class="sxs-lookup"><span data-stu-id="c4e15-136">In-memory collections</span></span>
- <span data-ttu-id="c4e15-137">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="c4e15-137">JSON/XML</span></span>
- <span data-ttu-id="c4e15-138">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="c4e15-138">Databases</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4e15-139">Tenga en cuenta que al trabajar con orígenes de transmisión, ML.NET espera que la entrada tenga la forma de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="c4e15-139">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="c4e15-140">Por lo tanto, cuando se trabaja con orígenes como JSON o XML, asegúrese de dar a los datos el formato de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="c4e15-140">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="c4e15-141">Dada la siguiente colección en memoria:</span><span class="sxs-lookup"><span data-stu-id="c4e15-141">Given the following in-memory collection:</span></span>

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

<span data-ttu-id="c4e15-142">Cargue la colección en memoria en un [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="c4e15-142">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
