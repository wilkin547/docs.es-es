---
title: Carga de datos de archivos y otros orígenes
description: Obtenga información sobre cómo cargar datos para su procesamiento y entrenamiento en ML.NET con la API. Los datos se almacenan en archivos, bases de datos, JSON, XML o colecciones en memoria.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74344752"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="f34c1-104">Carga de datos de archivos y otros orígenes</span><span class="sxs-lookup"><span data-stu-id="f34c1-104">Load data from files and other sources</span></span>

<span data-ttu-id="f34c1-105">Obtenga información sobre cómo cargar datos para su procesamiento y entrenamiento en ML.NET con la API.</span><span class="sxs-lookup"><span data-stu-id="f34c1-105">Learn how to load data for processing and training into ML.NET using the API.</span></span> <span data-ttu-id="f34c1-106">Los datos originalmente se almacenan en archivos u otros orígenes de datos, como colecciones en memoria, JSON, XML o bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

<span data-ttu-id="f34c1-107">Si utiliza el generador de modelos, vea [Carga de datos de entrenamiento en el Generador de modelos](load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f34c1-107">If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="f34c1-108">Crear el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="f34c1-108">Create the data model</span></span>

<span data-ttu-id="f34c1-109">ML.NET permite definir los modelos de datos mediante clases.</span><span class="sxs-lookup"><span data-stu-id="f34c1-109">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="f34c1-110">Por ejemplo, dado los siguientes datos de entrada:</span><span class="sxs-lookup"><span data-stu-id="f34c1-110">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="f34c1-111">Cree un modelo de datos que represente el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f34c1-111">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="f34c1-112">Anotar el modelo de datos con atributos de columna</span><span class="sxs-lookup"><span data-stu-id="f34c1-112">Annotating the data model with column attributes</span></span>

<span data-ttu-id="f34c1-113">Los atributos proporcionan a ML.NET más información sobre el modelo de datos y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-113">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="f34c1-114">El atributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) especifica los índices de columna de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f34c1-114">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f34c1-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) solo es necesario cuando se cargan datos desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="f34c1-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="f34c1-116">Cargar columnas como:</span><span class="sxs-lookup"><span data-stu-id="f34c1-116">Load columns as:</span></span>

- <span data-ttu-id="f34c1-117">Columnas individuales como `Size` y `CurrentPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="f34c1-117">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="f34c1-118">Varias columnas a la vez en forma de un vector como `HistoricalPrices` en la clase `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="f34c1-118">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="f34c1-119">Si tiene una propiedad de vector, aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) a la propiedad en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-119">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="f34c1-120">Es importante tener en cuenta que todos los elementos del vector deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f34c1-120">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="f34c1-121">Mantener las columnas separadas ofrece facilidad y flexibilidad para la ingeniería de características, pero para un gran número de columnas, el funcionamiento de las columnas individuales provoca un impacto en la velocidad del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f34c1-121">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="f34c1-122">ML.NET funciona a través de los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="f34c1-122">ML.NET Operates through column names.</span></span> <span data-ttu-id="f34c1-123">Si desea cambiar el nombre de una columna a otro nombre que no sea el de la propiedad, utilice el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="f34c1-123">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="f34c1-124">Al crear objetos en memoria, debe crear todavía objetos mediante el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f34c1-124">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="f34c1-125">Sin embargo, para el procesamiento de datos y la compilación de modelos de aprendizaje automático, ML.NET invalida la propiedad y hace referencia a esta con el valor proporcionado en el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="f34c1-125">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="f34c1-126">Carga de datos desde un archivo único</span><span class="sxs-lookup"><span data-stu-id="f34c1-126">Load data from a single file</span></span>

<span data-ttu-id="f34c1-127">Para cargar datos desde un archivo, utilice el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) junto con el modelo de datos para que se carguen los datos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-127">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="f34c1-128">Puesto que el parámetro `separatorChar` está delimitado por tabulaciones de forma predeterminada, cámbielo para el archivo de datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f34c1-128">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="f34c1-129">Si el archivo tiene un encabezado, establezca el parámetro `hasHeader` en `true` para omitir la primera línea en el archivo y comenzar a cargar datos de la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="f34c1-129">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="f34c1-130">Carga de datos de varios archivos</span><span class="sxs-lookup"><span data-stu-id="f34c1-130">Load data from multiple files</span></span>

<span data-ttu-id="f34c1-131">En caso de que los datos se almacenen en varios archivos, siempre y cuando el esquema de datos sea el mismo, ML.NET permite cargar datos desde varios archivos que están en el mismo directorio o en varios directorios.</span><span class="sxs-lookup"><span data-stu-id="f34c1-131">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="f34c1-132">Carga de archivos en un único directorio</span><span class="sxs-lookup"><span data-stu-id="f34c1-132">Load from files in a single directory</span></span>

<span data-ttu-id="f34c1-133">Cuando todos los archivos de datos se encuentran en el mismo directorio, utilice caracteres comodín en el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).</span><span class="sxs-lookup"><span data-stu-id="f34c1-133">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="f34c1-134">Carga de archivos en varios directorios</span><span class="sxs-lookup"><span data-stu-id="f34c1-134">Load from files in multiple directories</span></span>

<span data-ttu-id="f34c1-135">Para cargar datos desde varios directorios, utilice el método [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) para crear un [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="f34c1-135">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="f34c1-136">A continuación, utilice el método [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) y especifique las rutas de acceso de archivo individuales (no se pueden usar caracteres comodín).</span><span class="sxs-lookup"><span data-stu-id="f34c1-136">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="f34c1-137">Cargar datos desde una base de datos relacional</span><span class="sxs-lookup"><span data-stu-id="f34c1-137">Load data from a relational database</span></span>

<span data-ttu-id="f34c1-138">ML.NET admite la carga de datos desde una variedad de bases de datos relacionales admitidas por [`System.Data`](xref:System.Data), entre las que se incluyen SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 y muchas más.</span><span class="sxs-lookup"><span data-stu-id="f34c1-138">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

> [!NOTE]
> <span data-ttu-id="f34c1-139">Para usar `DatabaseLoader`, haga referencia al paquete NuGet [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient).</span><span class="sxs-lookup"><span data-stu-id="f34c1-139">To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.</span></span>

<span data-ttu-id="f34c1-140">Dada una base de datos con una tabla denominada `House` y el esquema siguiente:</span><span class="sxs-lookup"><span data-stu-id="f34c1-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="f34c1-141">Los datos se pueden modelar mediante una clase como `HouseData`.</span><span class="sxs-lookup"><span data-stu-id="f34c1-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="f34c1-142">Después, dentro de la aplicación, cree un `DatabaseLoader`.</span><span class="sxs-lookup"><span data-stu-id="f34c1-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="f34c1-143">Defina la cadena de conexión, así como el comando SQL que se va a ejecutar en la base de datos y cree una instancia `DatabaseSource`.</span><span class="sxs-lookup"><span data-stu-id="f34c1-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="f34c1-144">En este ejemplo se utiliza una base de datos de SQL Server LocalDB con una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="f34c1-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="f34c1-145">Pero DatabaseLoader admite cualquier otra cadena de conexión válida para bases de datos locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="f34c1-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

<span data-ttu-id="f34c1-146">Los datos numéricos que no son del tipo [`Real`](xref:System.Data.SqlDbType) deben convertirse en [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="f34c1-146">Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="f34c1-147">El tipo [`Real`](xref:System.Data.SqlDbType) se representa como un valor de punto flotante de precisión sencilla o [`Single`](xref:System.Single), el tipo de entrada que esperan los algoritmos de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="f34c1-147">The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms.</span></span> <span data-ttu-id="f34c1-148">En este ejemplo, la columna `NumBed` es un entero de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-148">In this sample, the `NumBed` column is an integer in the database.</span></span> <span data-ttu-id="f34c1-149">Con la función integrada `CAST`, se convierte en [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="f34c1-149">Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="f34c1-150">Como la propiedad `Price` ya es del tipo [`Real`](xref:System.Data.SqlDbType) se carga tal cual.</span><span class="sxs-lookup"><span data-stu-id="f34c1-150">Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.</span></span>

<span data-ttu-id="f34c1-151">Use el método `Load` para cargar los datos en [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="f34c1-151">Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="f34c1-152">Carga de datos desde otros orígenes</span><span class="sxs-lookup"><span data-stu-id="f34c1-152">Load data from other sources</span></span>

<span data-ttu-id="f34c1-153">Además de cargar los datos almacenados en archivos, ML.NET admite la carga de datos desde orígenes entre los que se incluyen, aunque sin carácter restrictivo:</span><span class="sxs-lookup"><span data-stu-id="f34c1-153">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="f34c1-154">Colecciones en memoria</span><span class="sxs-lookup"><span data-stu-id="f34c1-154">In-memory collections</span></span>
- <span data-ttu-id="f34c1-155">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="f34c1-155">JSON/XML</span></span>

<span data-ttu-id="f34c1-156">Tenga en cuenta que al trabajar con orígenes de transmisión, ML.NET espera que la entrada tenga la forma de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="f34c1-156">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="f34c1-157">Por lo tanto, cuando se trabaja con orígenes como JSON o XML, asegúrese de dar a los datos el formato de una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="f34c1-157">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="f34c1-158">Dada la siguiente colección en memoria:</span><span class="sxs-lookup"><span data-stu-id="f34c1-158">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="f34c1-159">Cargue la colección en memoria en un [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="f34c1-159">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f34c1-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) supone que [`IEnumerable`](xref:System.Collections.IEnumerable) de donde se carga es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f34c1-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a><span data-ttu-id="f34c1-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f34c1-161">Next steps</span></span>

- <span data-ttu-id="f34c1-162">Para limpiar o de otro modo procesar datos, vea [Preparación de los datos para la compilación de un modelo](prepare-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="f34c1-162">To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).</span></span>
- <span data-ttu-id="f34c1-163">Cuando esté listo para crear un modelo, vea [Entrenamiento y evaluación de un modelo](train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="f34c1-163">When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).</span></span>
