---
title: Preparación de los datos para la compilación de un modelo
description: Aprenda cómo utilizar las transformaciones de ML.NET para manipular y preparar datos para su procesamiento adicional o la creación de modelos.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452992"
---
# <a name="prepare-data-for-building-a-model"></a>Preparación de los datos para la compilación de un modelo

Aprenda cómo utilizar ML.NET para preparar datos para el procesamiento adicional o la creación de un modelo.

Los datos suelen estar dispersos o sin limpiar. Los algoritmos de aprendizaje automático de ML.NET esperan que las entradas o características estén en un vector numérico único. Del mismo modo, el valor que se va a predecir (etiqueta), especialmente cuando se trata de datos categóricos, debe estar codificado. Por lo tanto, uno de los objetivos de la preparación de datos es obtener los datos en el formato esperado por los algoritmos de ML.NET.

## <a name="filter-data"></a>Filtrar datos

En ocasiones, no todos los datos de un conjunto de datos son relevantes para el análisis. Un método para quitar los datos irrelevantes es el filtrado. [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un conjunto de operaciones de filtro que recibe un [`IDataView`](xref:Microsoft.ML.IDataView) que contiene todos los datos y devuelve un [IDataView](xref:Microsoft.ML.IDataView) que contiene únicamente los puntos de datos de interés. Es importante tener en cuenta que dado que las operaciones de filtro no son un [`IEstimator`](xref:Microsoft.ML.IEstimator%601) o un [`ITransformer`](xref:Microsoft.ML.ITransformer) como las de [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), no pueden incluirse como parte de una canalización de preparación de datos de [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).

Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:

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

Para filtrar datos según el valor de una columna, use el método [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

El ejemplo anterior toma filas del conjunto de datos con un precio entre 200 000 y 1 000 000. El resultado de aplicar este filtro podría devolver solo las dos últimas filas de los datos y excluir la primera fila porque su precio es de 100 000 y no está dentro del intervalo especificado.

## <a name="replace-missing-values"></a>Reemplazar los valores ausentes

En los conjuntos de datos suelen haber valores ausentes. Un enfoque para tratar con los valores ausentes es reemplazarlos por el valor predeterminado para el tipo especificado, si lo hay, o por otro valor significativo como, por ejemplo, el valor medio de los datos.

Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:

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

Tenga en cuenta que el último elemento de nuestra lista tiene un valor ausente para `Price`. Para reemplazar los valores ausentes en la columna `Price`, use el método [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) para rellenar ese valor ausente.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) solo funciona con datos numéricos.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET admite varios [modos de reemplazo](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). El ejemplo anterior usa el modo de reemplazo `Mean` que rellena el valor ausente con el valor medio de esa columna. El resultado del reemplazo se rellena en la propiedad `Price` para el último elemento en nuestros datos con 200 000, ya que es la media de 100 000 y 300 000.

## <a name="use-normalizers"></a>Usar normalizadores

La [normalización](https://en.wikipedia.org/wiki/Feature_scaling) es una técnica de procesamiento previo de datos que se usa para escalar características de forma que estén en el mismo intervalo, normalmente entre 0 y 1, para que un algoritmo de aprendizaje automático pueda procesarlas con más precisión. Por ejemplo, los intervalos de edad e ingresos varían significativamente, ya que la edad suele estar en el intervalo de 0 a 100 y los ingresos suelen estar en el intervalo de cero a miles. Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de normalización.

### <a name="min-max-normalization"></a>Normalización mínima-máxima

Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:

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

La normalización se puede aplicar a las columnas con valores numéricos individuales, así como a los vectores. Normalice los datos de la columna `Price` mediante la normalización mínima-máxima con el método [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A).

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

Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:

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

Normalice los datos en rangos con el método [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A). El parámetro `maximumBinCount` permite especificar el número de rangos necesarios para clasificar los datos. En este ejemplo, los datos se colocarán en dos rangos.

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

Uno de los tipos de datos más comunes son los datos categóricos. Los datos categóricos tienen un número finito de categorías. Por ejemplo, los estados de EE. UU. o una lista de los tipos de animales que se encuentran en un conjunto de imágenes. Si los datos categóricos son características o etiquetas, deben asignarse a un valor numérico para que se puedan usar para generar un modelo de aprendizaje automático. Hay varias maneras de trabajar con datos categóricos en ML.NET, en función del problema que quiera resolver.

### <a name="key-value-mapping"></a>Asignación de valores de clave

En ML.NET, una clave es un valor entero que representa una categoría. La asignación de valores de clave se usa con más frecuencia para asignar etiquetas de cadena en valores enteros únicos para el entrenamiento y, después, volver a sus valores de cadena cuando el modelo se utilice para realizar una predicción.

Las transformaciones utilizadas para realizar la asignación de valores de clave son [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) y [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).

`MapValueToKey` agrega un diccionario de asignaciones en el modelo, de modo que `MapKeyToValue` pueda realizar la transformación inversa al realizar una predicción.

### <a name="one-hot-encoding"></a>Codificación frecuente

Una codificación frecuente toma un conjunto finito de valores y los asigna a enteros cuya representación binaria tiene un valor `1` único en posiciones únicas en la cadena. Una codificación frecuente puede ser la mejor opción si no hay una ordenación implícita de los datos categóricos. En la tabla siguiente se muestra un ejemplo con códigos postales como valores sin formato.

|Valor sin formato|Valor codificado frecuente|
|---------|---------------------|
|98052|00...01|
|98100|00...10|
|...|...|
|98109|10...00|

La transformación para convertir los datos categóricos en números codificados de acceso frecuente es [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).

### <a name="hashing"></a>Aplicación de algoritmo hash

La aplicación de algoritmo hash es otra manera de convertir los datos categóricos en números. Una función hash asigna datos de tamaño arbitrario (una cadena de texto, por ejemplo) a un número con un intervalo fijo. La aplicación de algoritmo hash puede ser una forma rápida y eficaz de vectorizar las características. Un ejemplo importante de aplicación de algoritmo hash en el aprendizaje automático es el filtrado de correo no deseado, donde, en lugar de mantener un diccionario de palabras conocidas, se aplica un algoritmo hash a cada palabra del correo electrónico y se agrega a un vector de características grande. Este uso de la aplicación de algoritmo hash evita el problema de la elusión de filtrado del correo no deseado malintencionado mediante el uso de palabras que no están en el diccionario.

ML.NET proporciona transformación [hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) para realizar operaciones de aplicación de algoritmo hash en texto, fechas y datos numéricos. Al igual que la asignación de claves de valor, las salidas de la transformación hash son tipos de clave.

## <a name="work-with-text-data"></a>Trabajar con datos de texto

Al igual que los datos categóricos, los datos de texto deben transformarse en características numéricas antes de usarlos para crear un modelo de aprendizaje automático. Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de texto.

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

ML.NET proporciona la transformación [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A), que toma el valor de cadena de un texto y crea un conjunto de características a partir del texto, aplicando una serie de transformaciones individuales.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

La transformación resultante convierte los valores de texto en la columna `Description` en un vector numérico que es similar a la salida siguiente:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Las transformaciones que componen `FeaturizeText` también pueden aplicarse individualmente para conseguir un mayor control de la generación de características.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` contiene un subconjunto de operaciones realizadas por el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A). La ventaja de una canalización más compleja es el control y la visibilidad sobre las transformaciones aplicadas a los datos.

Con la primera entrada como ejemplo, la siguiente es una descripción detallada de los resultados producidos por los pasos de transformación definidos por `textEstimator`:

**Texto original: Este es un buen producto**

|Transformación | Descripción | Resultado
|--|--|--|
|1. NormalizeText | Convierte todas las letras en minúsculas de forma predeterminada | este es un buen producto
|2. TokenizeWords | Divide la cadena en palabras individuales | ["este","es","un","buen","producto"]
|3. RemoveDefaultStopWords | Quita las palabras irrelevantes como *es* y *un*. | ["buen","producto"]
|4. MapValueToKey | Asigna los valores a las claves (categorías), según los datos de entrada |  [1,2]
|5. ProduceNGrams | Transforma texto en secuencia de palabras consecutivas | [1,1,1,0,0]
|6. NormalizeLpNorm | Escala las entradas por su valor lp-norm | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]
