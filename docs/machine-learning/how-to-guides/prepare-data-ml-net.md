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
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="e7bda-103">Preparación de los datos para la compilación de un modelo</span><span class="sxs-lookup"><span data-stu-id="e7bda-103">Prepare data for building a model</span></span>

<span data-ttu-id="e7bda-104">Aprenda cómo utilizar ML.NET para preparar datos para el procesamiento adicional o la creación de un modelo.</span><span class="sxs-lookup"><span data-stu-id="e7bda-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="e7bda-105">Los datos suelen estar dispersos o sin limpiar.</span><span class="sxs-lookup"><span data-stu-id="e7bda-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="e7bda-106">Los algoritmos de aprendizaje automático de ML.NET esperan que las entradas o características estén en un vector numérico único.</span><span class="sxs-lookup"><span data-stu-id="e7bda-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="e7bda-107">Del mismo modo, el valor que se va a predecir (etiqueta), especialmente cuando se trata de datos categóricos, debe estar codificado.</span><span class="sxs-lookup"><span data-stu-id="e7bda-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="e7bda-108">Por lo tanto, uno de los objetivos de la preparación de datos es obtener los datos en el formato esperado por los algoritmos de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="e7bda-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="e7bda-109">Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="e7bda-109">Filter data</span></span>

<span data-ttu-id="e7bda-110">En ocasiones, no todos los datos de un conjunto de datos son relevantes para el análisis.</span><span class="sxs-lookup"><span data-stu-id="e7bda-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="e7bda-111">Un método para quitar los datos irrelevantes es el filtrado.</span><span class="sxs-lookup"><span data-stu-id="e7bda-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="e7bda-112">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un conjunto de operaciones de filtro que recibe un [`IDataView`](xref:Microsoft.ML.IDataView) que contiene todos los datos y devuelve un [IDataView](xref:Microsoft.ML.IDataView) que contiene únicamente los puntos de datos de interés.</span><span class="sxs-lookup"><span data-stu-id="e7bda-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="e7bda-113">Es importante tener en cuenta que dado que las operaciones de filtro no son un [`IEstimator`](xref:Microsoft.ML.IEstimator%601) o un [`ITransformer`](xref:Microsoft.ML.ITransformer) como las de [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), no pueden incluirse como parte de una canalización de preparación de datos de [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="e7bda-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="e7bda-114">Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:</span><span class="sxs-lookup"><span data-stu-id="e7bda-114">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="e7bda-115">Para filtrar datos según el valor de una columna, use el método [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="e7bda-116">El ejemplo anterior toma filas del conjunto de datos con un precio entre 200 000 y 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="e7bda-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="e7bda-117">El resultado de aplicar este filtro podría devolver solo las dos últimas filas de los datos y excluir la primera fila porque su precio es de 100 000 y no está dentro del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="e7bda-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="e7bda-118">Reemplazar los valores ausentes</span><span class="sxs-lookup"><span data-stu-id="e7bda-118">Replace missing values</span></span>

<span data-ttu-id="e7bda-119">En los conjuntos de datos suelen haber valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="e7bda-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="e7bda-120">Un enfoque para tratar con los valores ausentes es reemplazarlos por el valor predeterminado para el tipo especificado, si lo hay, o por otro valor significativo como, por ejemplo, el valor medio de los datos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="e7bda-121">Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:</span><span class="sxs-lookup"><span data-stu-id="e7bda-121">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="e7bda-122">Tenga en cuenta que el último elemento de nuestra lista tiene un valor ausente para `Price`.</span><span class="sxs-lookup"><span data-stu-id="e7bda-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="e7bda-123">Para reemplazar los valores ausentes en la columna `Price`, use el método [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) para rellenar ese valor ausente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7bda-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) solo funciona con datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="e7bda-125">ML.NET admite varios [modos de reemplazo](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="e7bda-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="e7bda-126">El ejemplo anterior usa el modo de reemplazo `Mean` que rellena el valor ausente con el valor medio de esa columna.</span><span class="sxs-lookup"><span data-stu-id="e7bda-126">The sample above uses the `Mean` replacement mode, which fills in the missing value with that column's average value.</span></span> <span data-ttu-id="e7bda-127">El resultado del reemplazo se rellena en la propiedad `Price` para el último elemento en nuestros datos con 200 000, ya que es la media de 100 000 y 300 000.</span><span class="sxs-lookup"><span data-stu-id="e7bda-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="e7bda-128">Usar normalizadores</span><span class="sxs-lookup"><span data-stu-id="e7bda-128">Use normalizers</span></span>

<span data-ttu-id="e7bda-129">La [normalización](https://en.wikipedia.org/wiki/Feature_scaling) es una técnica de procesamiento previo de datos que se usa para escalar características de forma que estén en el mismo intervalo, normalmente entre 0 y 1, para que un algoritmo de aprendizaje automático pueda procesarlas con más precisión.</span><span class="sxs-lookup"><span data-stu-id="e7bda-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to scale features to be in the same range, usually between 0 and 1, so that they can be more accurately processed by a machine learning algorithm.</span></span> <span data-ttu-id="e7bda-130">Por ejemplo, los intervalos de edad e ingresos varían significativamente, ya que la edad suele estar en el intervalo de 0 a 100 y los ingresos suelen estar en el intervalo de cero a miles.</span><span class="sxs-lookup"><span data-stu-id="e7bda-130">For example, the ranges for age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="e7bda-131">Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de normalización.</span><span class="sxs-lookup"><span data-stu-id="e7bda-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="e7bda-132">Normalización mínima-máxima</span><span class="sxs-lookup"><span data-stu-id="e7bda-132">Min-Max normalization</span></span>

<span data-ttu-id="e7bda-133">Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:</span><span class="sxs-lookup"><span data-stu-id="e7bda-133">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="e7bda-134">La normalización se puede aplicar a las columnas con valores numéricos individuales, así como a los vectores.</span><span class="sxs-lookup"><span data-stu-id="e7bda-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="e7bda-135">Normalice los datos de la columna `Price` mediante la normalización mínima-máxima con el método [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="e7bda-136">Los valores originales del precio `[200000,100000]` se convierten en `[ 1, 0.5 ]` mediante la fórmula de normalización `MinMax` que genera valores de salida en el intervalo entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="e7bda-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula that generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="e7bda-137">Discretización</span><span class="sxs-lookup"><span data-stu-id="e7bda-137">Binning</span></span>

<span data-ttu-id="e7bda-138">La [discretización](https://en.wikipedia.org/wiki/Data_binning) convierte valores continuos en una representación discreta de la entrada.</span><span class="sxs-lookup"><span data-stu-id="e7bda-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="e7bda-139">Por ejemplo, suponga que una de sus características es la edad.</span><span class="sxs-lookup"><span data-stu-id="e7bda-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="e7bda-140">En lugar de usar el valor de edad real, la discretización crea intervalos para ese valor.</span><span class="sxs-lookup"><span data-stu-id="e7bda-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="e7bda-141">0-18 puede ser un rango, otro podría ser 19-35 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="e7bda-142">Tome los siguientes datos de entrada y cárguelos en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) denominado `data`:</span><span class="sxs-lookup"><span data-stu-id="e7bda-142">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="e7bda-143">Normalice los datos en rangos con el método [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) method.</span></span> <span data-ttu-id="e7bda-144">El parámetro `maximumBinCount` permite especificar el número de rangos necesarios para clasificar los datos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="e7bda-145">En este ejemplo, los datos se colocarán en dos rangos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="e7bda-146">El resultado de la discretización crea límites de rangos de `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="e7bda-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="e7bda-147">Por lo tanto, los rangos resultantes son `[0,1,1]` porque la primera observación está comprendida entre 0 y 200 000 y las demás son mayores que 200 000, pero menores que infinito.</span><span class="sxs-lookup"><span data-stu-id="e7bda-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="e7bda-148">Trabajar con datos categóricos</span><span class="sxs-lookup"><span data-stu-id="e7bda-148">Work with categorical data</span></span>

<span data-ttu-id="e7bda-149">Uno de los tipos de datos más comunes son los datos categóricos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-149">One of the most common types of data is categorical data.</span></span> <span data-ttu-id="e7bda-150">Los datos categóricos tienen un número finito de categorías.</span><span class="sxs-lookup"><span data-stu-id="e7bda-150">Categorical data has a finite number of categories.</span></span> <span data-ttu-id="e7bda-151">Por ejemplo, los estados de EE. UU. o una lista de los tipos de animales que se encuentran en un conjunto de imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7bda-151">For example, the states of the USA, or a list of the types of animals found in a set of pictures.</span></span> <span data-ttu-id="e7bda-152">Si los datos categóricos son características o etiquetas, deben asignarse a un valor numérico para que se puedan usar para generar un modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="e7bda-152">Whether the categorical data are features or labels, they must be mapped onto a numerical value so they can be used to generate a machine learning model.</span></span> <span data-ttu-id="e7bda-153">Hay varias maneras de trabajar con datos categóricos en ML.NET, en función del problema que quiera resolver.</span><span class="sxs-lookup"><span data-stu-id="e7bda-153">There are a number of ways of working with categorical data in ML.NET, depending on the problem you are solving.</span></span>

### <a name="key-value-mapping"></a><span data-ttu-id="e7bda-154">Asignación de valores de clave</span><span class="sxs-lookup"><span data-stu-id="e7bda-154">Key value mapping</span></span>

<span data-ttu-id="e7bda-155">En ML.NET, una clave es un valor entero que representa una categoría.</span><span class="sxs-lookup"><span data-stu-id="e7bda-155">In ML.NET, a key is an integer value that represents a category.</span></span> <span data-ttu-id="e7bda-156">La asignación de valores de clave se usa con más frecuencia para asignar etiquetas de cadena en valores enteros únicos para el entrenamiento y, después, volver a sus valores de cadena cuando el modelo se utilice para realizar una predicción.</span><span class="sxs-lookup"><span data-stu-id="e7bda-156">Key value mapping is most often used to map string labels into unique integer values for training, then back to their string values when the model is used to make a prediction.</span></span>

<span data-ttu-id="e7bda-157">Las transformaciones utilizadas para realizar la asignación de valores de clave son [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) y [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-157">The transforms used to perform key value mapping are [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) and [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span></span>

<span data-ttu-id="e7bda-158">`MapValueToKey` agrega un diccionario de asignaciones en el modelo, de modo que `MapKeyToValue` pueda realizar la transformación inversa al realizar una predicción.</span><span class="sxs-lookup"><span data-stu-id="e7bda-158">`MapValueToKey` adds a dictionary of mappings in the model, so that `MapKeyToValue` can perform the reverse transform when making a prediction.</span></span>

### <a name="one-hot-encoding"></a><span data-ttu-id="e7bda-159">Codificación frecuente</span><span class="sxs-lookup"><span data-stu-id="e7bda-159">One hot encoding</span></span>

<span data-ttu-id="e7bda-160">Una codificación frecuente toma un conjunto finito de valores y los asigna a enteros cuya representación binaria tiene un valor `1` único en posiciones únicas en la cadena.</span><span class="sxs-lookup"><span data-stu-id="e7bda-160">One hot encoding takes a finite set of values and maps them onto integers whose binary representation has a single `1` value in unique positions in the string.</span></span> <span data-ttu-id="e7bda-161">Una codificación frecuente puede ser la mejor opción si no hay una ordenación implícita de los datos categóricos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-161">One hot encoding can be the best choice if there is no implicit ordering of the categorical data.</span></span> <span data-ttu-id="e7bda-162">En la tabla siguiente se muestra un ejemplo con códigos postales como valores sin formato.</span><span class="sxs-lookup"><span data-stu-id="e7bda-162">The following table shows an example with zip codes as raw values.</span></span>

|<span data-ttu-id="e7bda-163">Valor sin formato</span><span class="sxs-lookup"><span data-stu-id="e7bda-163">Raw value</span></span>|<span data-ttu-id="e7bda-164">Valor codificado frecuente</span><span class="sxs-lookup"><span data-stu-id="e7bda-164">One hot encoded value</span></span>|
|---------|---------------------|
|<span data-ttu-id="e7bda-165">98052</span><span class="sxs-lookup"><span data-stu-id="e7bda-165">98052</span></span>|<span data-ttu-id="e7bda-166">00...01</span><span class="sxs-lookup"><span data-stu-id="e7bda-166">00...01</span></span>|
|<span data-ttu-id="e7bda-167">98100</span><span class="sxs-lookup"><span data-stu-id="e7bda-167">98100</span></span>|<span data-ttu-id="e7bda-168">00...10</span><span class="sxs-lookup"><span data-stu-id="e7bda-168">00...10</span></span>|
|<span data-ttu-id="e7bda-169">...</span><span class="sxs-lookup"><span data-stu-id="e7bda-169">...</span></span>|<span data-ttu-id="e7bda-170">...</span><span class="sxs-lookup"><span data-stu-id="e7bda-170">...</span></span>|
|<span data-ttu-id="e7bda-171">98109</span><span class="sxs-lookup"><span data-stu-id="e7bda-171">98109</span></span>|<span data-ttu-id="e7bda-172">10...00</span><span class="sxs-lookup"><span data-stu-id="e7bda-172">10...00</span></span>|

<span data-ttu-id="e7bda-173">La transformación para convertir los datos categóricos en números codificados de acceso frecuente es [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-173">The transform to convert categorical data to one-hot encoded numbers is [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span></span>

### <a name="hashing"></a><span data-ttu-id="e7bda-174">Aplicación de algoritmo hash</span><span class="sxs-lookup"><span data-stu-id="e7bda-174">Hashing</span></span>

<span data-ttu-id="e7bda-175">La aplicación de algoritmo hash es otra manera de convertir los datos categóricos en números.</span><span class="sxs-lookup"><span data-stu-id="e7bda-175">Hashing is another way to convert categorical data to numbers.</span></span> <span data-ttu-id="e7bda-176">Una función hash asigna datos de tamaño arbitrario (una cadena de texto, por ejemplo) a un número con un intervalo fijo.</span><span class="sxs-lookup"><span data-stu-id="e7bda-176">A hash function maps data of an arbitrary size (a string of text for example) onto a number with a fixed range.</span></span> <span data-ttu-id="e7bda-177">La aplicación de algoritmo hash puede ser una forma rápida y eficaz de vectorizar las características.</span><span class="sxs-lookup"><span data-stu-id="e7bda-177">Hashing can be a fast and space-efficient way of vectorizing features.</span></span> <span data-ttu-id="e7bda-178">Un ejemplo importante de aplicación de algoritmo hash en el aprendizaje automático es el filtrado de correo no deseado, donde, en lugar de mantener un diccionario de palabras conocidas, se aplica un algoritmo hash a cada palabra del correo electrónico y se agrega a un vector de características grande.</span><span class="sxs-lookup"><span data-stu-id="e7bda-178">One notable example of hashing in machine learning is email spam filtering where, instead of maintaining a dictionary of known words, every word in the email is hashed and added to a large feature vector.</span></span> <span data-ttu-id="e7bda-179">Este uso de la aplicación de algoritmo hash evita el problema de la elusión de filtrado del correo no deseado malintencionado mediante el uso de palabras que no están en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="e7bda-179">Using hashing in this way avoids the problem of malicious spam filtering circumvention by the use of words that are not in the dictionary.</span></span>

<span data-ttu-id="e7bda-180">ML.NET proporciona transformación [hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) para realizar operaciones de aplicación de algoritmo hash en texto, fechas y datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-180">ML.NET provides [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) transform to perform hashing on text, dates, and numerical data.</span></span> <span data-ttu-id="e7bda-181">Al igual que la asignación de claves de valor, las salidas de la transformación hash son tipos de clave.</span><span class="sxs-lookup"><span data-stu-id="e7bda-181">Like value key mapping, the outputs of the hash transform are key types.</span></span>

## <a name="work-with-text-data"></a><span data-ttu-id="e7bda-182">Trabajar con datos de texto</span><span class="sxs-lookup"><span data-stu-id="e7bda-182">Work with text data</span></span>

<span data-ttu-id="e7bda-183">Al igual que los datos categóricos, los datos de texto deben transformarse en características numéricas antes de usarlos para crear un modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="e7bda-183">Like categorical data, text data needs to be transformed into numerical features before using it to build a machine learning model.</span></span> <span data-ttu-id="e7bda-184">Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de texto.</span><span class="sxs-lookup"><span data-stu-id="e7bda-184">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="e7bda-185">Uso de datos, como los datos siguientes que se han cargado en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e7bda-185">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e7bda-186">ML.NET proporciona la transformación [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A), que toma el valor de cadena de un texto y crea un conjunto de características a partir del texto, aplicando una serie de transformaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="e7bda-186">ML.NET provides the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) transform that takes a text's string value and creates a set of features from the text, by applying a series of individual transforms.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="e7bda-187">La transformación resultante convierte los valores de texto en la columna `Description` en un vector numérico que es similar a la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7bda-187">The resulting transform converts the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="e7bda-188">Las transformaciones que componen `FeaturizeText` también pueden aplicarse individualmente para conseguir un mayor control de la generación de características.</span><span class="sxs-lookup"><span data-stu-id="e7bda-188">The transforms that make up `FeaturizeText` can also be applied individually for finer grain control over feature generation.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="e7bda-189">`textEstimator` contiene un subconjunto de operaciones realizadas por el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A).</span><span class="sxs-lookup"><span data-stu-id="e7bda-189">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) method.</span></span> <span data-ttu-id="e7bda-190">La ventaja de una canalización más compleja es el control y la visibilidad sobre las transformaciones aplicadas a los datos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-190">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="e7bda-191">Con la primera entrada como ejemplo, la siguiente es una descripción detallada de los resultados producidos por los pasos de transformación definidos por `textEstimator`:</span><span class="sxs-lookup"><span data-stu-id="e7bda-191">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="e7bda-192">**Texto original: Este es un buen producto**</span><span class="sxs-lookup"><span data-stu-id="e7bda-192">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="e7bda-193">Transformación</span><span class="sxs-lookup"><span data-stu-id="e7bda-193">Transform</span></span> | <span data-ttu-id="e7bda-194">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7bda-194">Description</span></span> | <span data-ttu-id="e7bda-195">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7bda-195">Result</span></span>
|--|--|--|
|<span data-ttu-id="e7bda-196">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="e7bda-196">1. NormalizeText</span></span> | <span data-ttu-id="e7bda-197">Convierte todas las letras en minúsculas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="e7bda-197">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="e7bda-198">este es un buen producto</span><span class="sxs-lookup"><span data-stu-id="e7bda-198">this is a good product</span></span>
|<span data-ttu-id="e7bda-199">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="e7bda-199">2. TokenizeWords</span></span> | <span data-ttu-id="e7bda-200">Divide la cadena en palabras individuales</span><span class="sxs-lookup"><span data-stu-id="e7bda-200">Splits string into individual words</span></span> | <span data-ttu-id="e7bda-201">["este","es","un","buen","producto"]</span><span class="sxs-lookup"><span data-stu-id="e7bda-201">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="e7bda-202">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="e7bda-202">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="e7bda-203">Quita las palabras irrelevantes como *es* y *un*.</span><span class="sxs-lookup"><span data-stu-id="e7bda-203">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="e7bda-204">["buen","producto"]</span><span class="sxs-lookup"><span data-stu-id="e7bda-204">["good","product"]</span></span>
|<span data-ttu-id="e7bda-205">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="e7bda-205">4. MapValueToKey</span></span> | <span data-ttu-id="e7bda-206">Asigna los valores a las claves (categorías), según los datos de entrada</span><span class="sxs-lookup"><span data-stu-id="e7bda-206">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="e7bda-207">[1,2]</span><span class="sxs-lookup"><span data-stu-id="e7bda-207">[1,2]</span></span>
|<span data-ttu-id="e7bda-208">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="e7bda-208">5. ProduceNGrams</span></span> | <span data-ttu-id="e7bda-209">Transforma texto en secuencia de palabras consecutivas</span><span class="sxs-lookup"><span data-stu-id="e7bda-209">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="e7bda-210">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="e7bda-210">[1,1,1,0,0]</span></span>
|<span data-ttu-id="e7bda-211">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="e7bda-211">6. NormalizeLpNorm</span></span> | <span data-ttu-id="e7bda-212">Escala las entradas por su valor lp-norm</span><span class="sxs-lookup"><span data-stu-id="e7bda-212">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="e7bda-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="e7bda-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
