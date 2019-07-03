---
title: Preparar los datos
description: Aprenda cómo utilizar las transformaciones de ML.NET para manipular y preparar datos para su procesamiento adicional o la creación de modelos.
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: abf43260a438c9b1febffc77cf39e7328e0377ee
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268238"
---
# <a name="prepare-data"></a>Preparar los datos

Aprenda cómo utilizar ML.NET para preparar datos para el procesamiento adicional o la creación de un modelo.

Los datos suelen estar dispersos o sin limpiar. Además, los algoritmos de aprendizaje automático de ML.NET esperan que las entradas o características estén en un vector numérico único. Por lo tanto, uno de los objetivos de la preparación de datos es obtener los datos en el formato esperado por los algoritmos de ML.NET. 

## <a name="filter-data"></a>Filtrar datos

En ocasiones, no todos los datos de un conjunto de datos son relevantes para el análisis. Un método para quitar los datos irrelevantes es el filtrado. [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un conjunto de operaciones de filtro que recibe un [`IDataView`](xref:Microsoft.ML.IDataView) que contiene todos los datos y devuelve un [IDataView](xref:Microsoft.ML.IDataView) que contiene únicamente los puntos de datos de interés. Es importante tener en cuenta que dado que las operaciones de filtro no son un [`IEstimator`](xref:Microsoft.ML.IEstimator%601) o un [`ITransformer`](xref:Microsoft.ML.ITransformer) como las de [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), no pueden incluirse como parte de una canalización de preparación de datos de [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601). 

Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

Para filtrar datos según el valor de una columna, use el método [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

El ejemplo anterior toma filas del conjunto de datos con un precio entre 200 000 y 1 000 000. El resultado de aplicar este filtro podría devolver solo las dos últimas filas de los datos y excluir la primera fila porque su precio es de 100 000 y no está dentro del intervalo especificado.

## <a name="replace-missing-values"></a>Reemplazar los valores ausentes

En los conjuntos de datos suelen haber valores ausentes. Un enfoque para tratar con los valores ausentes es reemplazarlos por el valor predeterminado para el tipo especificado, si lo hay, o por otro valor significativo como, por ejemplo, el valor medio de los datos. 

Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

Tenga en cuenta que el último elemento de nuestra lista tiene un valor ausente para `Price`. Para reemplazar los valores ausentes en la columna `Price`, use el método [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) para rellenar ese valor ausente.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) solo funciona con datos numéricos.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET admite varios [modos de reemplazo](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). El ejemplo anterior usa el modo de reemplazo `Mean` que rellenará el valor ausente con el valor medio de esa columna. El resultado del reemplazo se rellena en la propiedad `Price` para el último elemento en nuestros datos con 200 000, ya que es la media de 100 000 y 300 000. 

## <a name="use-normalizers"></a>Usar normalizadores

La [normalización](https://en.wikipedia.org/wiki/Feature_scaling) es una técnica de preprocesamiento de datos que se utiliza para normalizar las características que no están en la misma escala, lo que ayuda a los algoritmos a converger con mayor rapidez. Por ejemplo, los intervalos de valores como la edad y los ingresos varían significativamente, ya que la edad suele estar en el intervalo de 0 a 100 y los ingresos suelen estar en el intervalo de cero a miles. Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de normalización. 

### <a name="min-max-normalization"></a>Normalización mínima-máxima

Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

La normalización se puede aplicar a las columnas con valores numéricos individuales, así como a los vectores. Normalice los datos de la columna `Price` mediante la normalización mínima-máxima con el método [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

Los valores originales del precio `[200000,100000]` se convierten en `[ 1, 0.5 ]` mediante la fórmula de normalización `MinMax` que genera valores de salida en el intervalo entre 0 y 1.

### <a name="binning"></a>Discretización

La [discretización](https://en.wikipedia.org/wiki/Data_binning) convierte valores continuos en una representación discreta de la entrada. Por ejemplo, suponga que una de sus características es la edad. En lugar de usar el valor de edad real, la discretización crea intervalos para ese valor. 0-18 puede ser un rango, otro podría ser 19-35 y así sucesivamente. 

Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

Normalice los datos en rangos con el método [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*). El parámetro `maximumBinCount` permite especificar el número de rangos necesarios para clasificar los datos. En este ejemplo, los datos se colocarán en dos rangos.  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

El resultado de la discretización crea límites de rangos de `[0,200000,Infinity]`. Por lo tanto, los rangos resultantes son `[0,1,1]` porque la primera observación está comprendida entre 0 y 200 000 y las demás son mayores que 200 000, pero menores que infinito.

## <a name="work-with-categorical-data"></a>Trabajar con datos categóricos

Los datos de categorías no numéricas deben convertirse en un número antes de usarse para generar un modelo de Machine Learning. 

Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

La propiedad `VehicleType` categórica se puede convertir en un número con el método [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*). 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

La transformación resultante convierte el valor de texto de `VehicleType` en un número. Las entradas de la columna `VehicleType` se convierten en lo siguiente cuando se aplica la transformación: 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a>Trabajar con datos de texto

Los datos de texto deben transformarse en números antes de usarlos para crear un modelo de Machine Learning. Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de texto.

Uso de datos, como los datos siguientes que se han cargado en un [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

El paso mínimo para convertir texto en una representación numérica del vector es usar el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). Mediante el uso de la transformación [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*), se aplican una serie de transformaciones a la columna de texto de entrada resultante en un vector numérico que representa la palabra lp-normalizada y las n-gramas de caracteres. 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

La transformación resultante podría convertir los valores de texto en la columna `Description` en un vector numérico que es similar a la salida siguiente:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Combine pasos complejos de procesamiento de texto en un [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) para quitar ruido y reducir potencialmente la cantidad de recursos de procesamiento requeridos según sea necesario.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` contiene un subconjunto de operaciones realizadas por el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). La ventaja de una canalización más compleja es el control y la visibilidad sobre las transformaciones aplicadas a los datos. 

Con la primera entrada como ejemplo, la siguiente es una descripción detallada de los resultados producidos por los pasos de transformación definidos por `textEstimator`:

**Texto original: Este es un buen producto**

|Transformación | DESCRIPCIÓN | Resultado
|--|--|--|
|1. NormalizeText | Convierte todas las letras en minúsculas de forma predeterminada | este es un buen producto
|2. TokenizeWords | Divide la cadena en palabras individuales | ["este","es","un","buen","producto"]
|3. RemoveDefaultStopWords | Quita las palabras irrelevantes como *es* y *un*. | ["buen","producto"]
|4. MapValueToKey | Asigna los valores a las claves (categorías), según los datos de entrada |  [1,2]
|5. ProduceNGrams | Transforma texto en secuencia de palabras consecutivas | [1,1,1,0,0]
|6. NormalizeLpNorm | Escala las entradas por su valor lp-norm | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]
