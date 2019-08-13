---
title: Carga de datos de archivos y otros orígenes
description: Este procedimiento muestra cómo cargar datos para su procesamiento y entrenamiento en ML.NET. Los datos originalmente se almacenan en archivos u otros orígenes de datos, como colecciones en memoria, JSON, XML o bases de datos.
ms.date: 08/01/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: d5f3aab14a60a8c9860dc67f1cc98f3b1b3188ed
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733371"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="71ea0-104">Carga de datos de archivos y otros orígenes</span><span class="sxs-lookup"><span data-stu-id="71ea0-104">Load data from files and other sources</span></span>

<span data-ttu-id="71ea0-105">Este procedimiento muestra cómo cargar datos para su procesamiento y entrenamiento en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="71ea0-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="71ea0-106">Los datos originalmente se almacenan en archivos u otros orígenes de datos, como colecciones en memoria, JSON, XML o bases de datos.</span><span class="sxs-lookup"><span data-stu-id="71ea0-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="71ea0-107">Crear el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="71ea0-107">Create the data model</span></span>

<span data-ttu-id="71ea0-108">ML.NET permite definir los modelos de datos mediante clases.</span><span class="sxs-lookup"><span data-stu-id="71ea0-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="71ea0-109">Por ejemplo, dado los siguientes datos de entrada:</span><span class="sxs-lookup"><span data-stu-id="71ea0-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="71ea0-110">Cree un modelo de datos que represente el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="71ea0-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="71ea0-111">Anotar el modelo de datos con atributos de columna</span><span class="sxs-lookup"><span data-stu-id="71ea0-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="71ea0-112">Los atributos proporcionan a ML.NET más información sobre el modelo de datos y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="71ea0-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="71ea0-113">El atributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) especifica los índices de columna de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="71ea0-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ea0-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) solo es necesario cuando se cargan datos desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="71ea0-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="71ea0-115">Cargar columnas como:</span><span class="sxs-lookup"><span data-stu-id="71ea0-115">Load columns as:</span></span> 
- <span data-ttu-id="71ea0-116">Columnas individuales como `Size` y `CurrentPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="71ea0-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="71ea0-117">Varias columnas a la vez en forma de un vector como `HistoricalPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="71ea0-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="71ea0-118">Si tiene una propiedad de vector, aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) a la propiedad en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="71ea0-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="71ea0-119">Es importante tener en cuenta que todos los elementos del vector deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="71ea0-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="71ea0-120">Mantener las columnas separadas ofrece facilidad y flexibilidad para la ingeniería de características, pero para un gran número de columnas, el funcionamiento de las columnas individuales provoca un impacto en la velocidad del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="71ea0-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="71ea0-121">ML.NET funciona a través de los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="71ea0-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="71ea0-122">Si desea cambiar el nombre de una columna a otro nombre que no sea el de la propiedad, utilice el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="71ea0-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="71ea0-123">Al crear objetos en memoria, debe crear todavía objetos mediante el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="71ea0-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="71ea0-124">Sin embargo, para el procesamiento de datos y la compilación de modelos de aprendizaje automático, ML.NET invalida la propiedad y hace referencia a esta con el valor proporcionado en el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="71ea0-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="71ea0-125">Carga de datos desde un archivo único</span><span class="sxs-lookup"><span data-stu-id="71ea0-125">Load data from a single file</span></span>

<span data-ttu-id="71ea0-126">Para cargar datos desde un archivo, utilice el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) junto con el modelo de datos para que se carguen los datos.</span><span class="sxs-lookup"><span data-stu-id="71ea0-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="71ea0-127">Puesto que el parámetro `separatorChar` está delimitado por tabulaciones de forma predeterminada, cámbielo para el archivo de datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="71ea0-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="71ea0-128">Si el archivo tiene un encabezado, establezca el parámetro `hasHeader` en `true` para omitir la primera línea en el archivo y comenzar a cargar datos de la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="71ea0-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="71ea0-129">Carga de datos de varios archivos</span><span class="sxs-lookup"><span data-stu-id="71ea0-129">Load data from multiple files</span></span>

<span data-ttu-id="71ea0-130">En caso de que los datos se almacenen en varios archivos, siempre y cuando el esquema de datos sea el mismo, ML.NET permite cargar datos desde varios archivos que están en el mismo directorio o en varios directorios.</span><span class="sxs-lookup"><span data-stu-id="71ea0-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="71ea0-131">Carga de archivos en un único directorio</span><span class="sxs-lookup"><span data-stu-id="71ea0-131">Load from files in a single directory</span></span>

<span data-ttu-id="71ea0-132">Cuando todos los archivos de datos se encuentran en el mismo directorio, utilice caracteres comodín en el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).</span><span class="sxs-lookup"><span data-stu-id="71ea0-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="71ea0-133">Carga de archivos en varios directorios</span><span class="sxs-lookup"><span data-stu-id="71ea0-133">Load from files in multiple directories</span></span>

<span data-ttu-id="71ea0-134">Para cargar datos desde varios directorios, utilice el método [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) para crear un [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="71ea0-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="71ea0-135">A continuación, utilice el método [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) y especifique las rutas de acceso de archivo individuales (no se pueden usar caracteres comodín).</span><span class="sxs-lookup"><span data-stu-id="71ea0-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="71ea0-136">Carga de datos desde otros orígenes</span><span class="sxs-lookup"><span data-stu-id="71ea0-136">Load data from other sources</span></span>

<span data-ttu-id="71ea0-137">Además de cargar los datos almacenados en archivos, ML.NET admite la carga de datos desde orígenes entre los que se incluyen, aunque sin carácter restrictivo:</span><span class="sxs-lookup"><span data-stu-id="71ea0-137">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="71ea0-138">Colecciones en memoria</span><span class="sxs-lookup"><span data-stu-id="71ea0-138">In-memory collections</span></span>
- <span data-ttu-id="71ea0-139">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="71ea0-139">JSON/XML</span></span>
- <span data-ttu-id="71ea0-140">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="71ea0-140">Databases</span></span>

<span data-ttu-id="71ea0-141">Tenga en cuenta que al trabajar con orígenes de transmisión, ML.NET espera que la entrada tenga la forma de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="71ea0-141">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="71ea0-142">Por lo tanto, cuando se trabaja con orígenes como JSON o XML, asegúrese de dar a los datos el formato de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="71ea0-142">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="71ea0-143">Dada la siguiente colección en memoria:</span><span class="sxs-lookup"><span data-stu-id="71ea0-143">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="71ea0-144">Cargue la colección en memoria en un [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="71ea0-144">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ea0-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) supone que [`IEnumerable`](xref:System.Collections.IEnumerable) de donde se carga es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="71ea0-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span> 

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
