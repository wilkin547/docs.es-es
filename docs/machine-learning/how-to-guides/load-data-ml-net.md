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
# <a name="load-data-from-files-and-other-sources"></a>Carga de datos de archivos y otros orígenes

Obtenga información sobre cómo cargar datos para su procesamiento y entrenamiento en ML.NET con la API. Los datos originalmente se almacenan en archivos u otros orígenes de datos, como colecciones en memoria, JSON, XML o bases de datos.

Si utiliza el generador de modelos, vea [Carga de datos de entrenamiento en el Generador de modelos](load-data-model-builder.md).

## <a name="create-the-data-model"></a>Crear el modelo de datos

ML.NET permite definir los modelos de datos mediante clases. Por ejemplo, dado los siguientes datos de entrada:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

Cree un modelo de datos que represente el fragmento de código siguiente:

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

### <a name="annotating-the-data-model-with-column-attributes"></a>Anotar el modelo de datos con atributos de columna

Los atributos proporcionan a ML.NET más información sobre el modelo de datos y el origen de datos.

El atributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) especifica los índices de columna de las propiedades.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) solo es necesario cuando se cargan datos desde un archivo.

Cargar columnas como:

- Columnas individuales como `Size` y `CurrentPrices` en la clase `HousingData`.
- Varias columnas a la vez en forma de un vector como `HistoricalPrices` en la clase `HousingData`.

Si tiene una propiedad de vector, aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) a la propiedad en el modelo de datos. Es importante tener en cuenta que todos los elementos del vector deben ser del mismo tipo. Mantener las columnas separadas ofrece facilidad y flexibilidad para la ingeniería de características, pero para un gran número de columnas, el funcionamiento de las columnas individuales provoca un impacto en la velocidad del entrenamiento.

ML.NET funciona a través de los nombres de columna. Si desea cambiar el nombre de una columna a otro nombre que no sea el de la propiedad, utilice el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute). Al crear objetos en memoria, debe crear todavía objetos mediante el nombre de la propiedad. Sin embargo, para el procesamiento de datos y la compilación de modelos de aprendizaje automático, ML.NET invalida la propiedad y hace referencia a esta con el valor proporcionado en el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).

## <a name="load-data-from-a-single-file"></a>Carga de datos desde un archivo único

Para cargar datos desde un archivo, utilice el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) junto con el modelo de datos para que se carguen los datos. Puesto que el parámetro `separatorChar` está delimitado por tabulaciones de forma predeterminada, cámbielo para el archivo de datos según sea necesario. Si el archivo tiene un encabezado, establezca el parámetro `hasHeader` en `true` para omitir la primera línea en el archivo y comenzar a cargar datos de la segunda línea.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Carga de datos de varios archivos

En caso de que los datos se almacenen en varios archivos, siempre y cuando el esquema de datos sea el mismo, ML.NET permite cargar datos desde varios archivos que están en el mismo directorio o en varios directorios.

### <a name="load-from-files-in-a-single-directory"></a>Carga de archivos en un único directorio

Cuando todos los archivos de datos se encuentran en el mismo directorio, utilice caracteres comodín en el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Carga de archivos en varios directorios

Para cargar datos desde varios directorios, utilice el método [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) para crear un [`TextLoader`](xref:Microsoft.ML.Data.TextLoader). A continuación, utilice el método [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) y especifique las rutas de acceso de archivo individuales (no se pueden usar caracteres comodín).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a>Cargar datos desde una base de datos relacional

ML.NET admite la carga de datos desde una variedad de bases de datos relacionales admitidas por [`System.Data`](xref:System.Data), entre las que se incluyen SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 y muchas más.

> [!NOTE]
> Para usar `DatabaseLoader`, haga referencia al paquete NuGet [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient).

Dada una base de datos con una tabla denominada `House` y el esquema siguiente:

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

Los datos se pueden modelar mediante una clase como `HouseData`.

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

Después, dentro de la aplicación, cree un `DatabaseLoader`.

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

Defina la cadena de conexión, así como el comando SQL que se va a ejecutar en la base de datos y cree una instancia `DatabaseSource`. En este ejemplo se utiliza una base de datos de SQL Server LocalDB con una ruta de acceso de archivo. Pero DatabaseLoader admite cualquier otra cadena de conexión válida para bases de datos locales y en la nube.

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

Los datos numéricos que no son del tipo [`Real`](xref:System.Data.SqlDbType) deben convertirse en [`Real`](xref:System.Data.SqlDbType). El tipo [`Real`](xref:System.Data.SqlDbType) se representa como un valor de punto flotante de precisión sencilla o [`Single`](xref:System.Single), el tipo de entrada que esperan los algoritmos de ML.NET. En este ejemplo, la columna `NumBed` es un entero de la base de datos. Con la función integrada `CAST`, se convierte en [`Real`](xref:System.Data.SqlDbType). Como la propiedad `Price` ya es del tipo [`Real`](xref:System.Data.SqlDbType) se carga tal cual.

Use el método `Load` para cargar los datos en [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a>Carga de datos desde otros orígenes

Además de cargar los datos almacenados en archivos, ML.NET admite la carga de datos desde orígenes entre los que se incluyen, aunque sin carácter restrictivo:

- Colecciones en memoria
- JSON/XML

Tenga en cuenta que al trabajar con orígenes de transmisión, ML.NET espera que la entrada tenga la forma de una colección en memoria. Por lo tanto, cuando se trabaja con orígenes como JSON o XML, asegúrese de dar a los datos el formato de una colección en memoria.

Dada la siguiente colección en memoria:

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

Cargue la colección en memoria en un [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) supone que [`IEnumerable`](xref:System.Collections.IEnumerable) de donde se carga es seguro para subprocesos.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a>Pasos siguientes

- Para limpiar o de otro modo procesar datos, vea [Preparación de los datos para la compilación de un modelo](prepare-data-ml-net.md).
- Cuando esté listo para crear un modelo, vea [Entrenamiento y evaluación de un modelo](train-machine-learning-model-ml-net.md).
