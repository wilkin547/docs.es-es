---
title: Preparación de los datos para la compilación de un modelo
description: Aprenda cómo utilizar las transformaciones de ML.NET para manipular y preparar datos para su procesamiento adicional o la creación de modelos.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/11/2019
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: e9bfad4724b353b0f3bfc615a40f1d72b80a2cd4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976979"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="604b4-103">Preparación de los datos para la compilación de un modelo</span><span class="sxs-lookup"><span data-stu-id="604b4-103">Prepare data for building a model</span></span>

<span data-ttu-id="604b4-104">Aprenda cómo utilizar ML.NET para preparar datos para el procesamiento adicional o la creación de un modelo.</span><span class="sxs-lookup"><span data-stu-id="604b4-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="604b4-105">Los datos suelen estar dispersos o sin limpiar.</span><span class="sxs-lookup"><span data-stu-id="604b4-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="604b4-106">Los algoritmos de aprendizaje automático de ML.NET esperan que las entradas o características estén en un vector numérico único.</span><span class="sxs-lookup"><span data-stu-id="604b4-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="604b4-107">Del mismo modo, el valor que se va a predecir (etiqueta), especialmente cuando se trata de datos categóricos, debe estar codificado.</span><span class="sxs-lookup"><span data-stu-id="604b4-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="604b4-108">Por lo tanto, uno de los objetivos de la preparación de datos es obtener los datos en el formato esperado por los algoritmos de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="604b4-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="604b4-109">Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="604b4-109">Filter data</span></span>

<span data-ttu-id="604b4-110">En ocasiones, no todos los datos de un conjunto de datos son relevantes para el análisis.</span><span class="sxs-lookup"><span data-stu-id="604b4-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="604b4-111">Un método para quitar los datos irrelevantes es el filtrado.</span><span class="sxs-lookup"><span data-stu-id="604b4-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="604b4-112">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un conjunto de operaciones de filtro que recibe un [`IDataView`](xref:Microsoft.ML.IDataView) que contiene todos los datos y devuelve un [IDataView](xref:Microsoft.ML.IDataView) que contiene únicamente los puntos de datos de interés.</span><span class="sxs-lookup"><span data-stu-id="604b4-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="604b4-113">Es importante tener en cuenta que dado que las operaciones de filtro no son un [`IEstimator`](xref:Microsoft.ML.IEstimator%601) o un [`ITransformer`](xref:Microsoft.ML.ITransformer) como las de [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), no pueden incluirse como parte de una canalización de preparación de datos de [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="604b4-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="604b4-114">Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-114">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-115">Para filtrar datos según el valor de una columna, use el método [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).</span><span class="sxs-lookup"><span data-stu-id="604b4-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="604b4-116">El ejemplo anterior toma filas del conjunto de datos con un precio entre 200 000 y 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="604b4-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="604b4-117">El resultado de aplicar este filtro podría devolver solo las dos últimas filas de los datos y excluir la primera fila porque su precio es de 100 000 y no está dentro del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="604b4-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="604b4-118">Reemplazar los valores ausentes</span><span class="sxs-lookup"><span data-stu-id="604b4-118">Replace missing values</span></span>

<span data-ttu-id="604b4-119">En los conjuntos de datos suelen haber valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="604b4-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="604b4-120">Un enfoque para tratar con los valores ausentes es reemplazarlos por el valor predeterminado para el tipo especificado, si lo hay, o por otro valor significativo como, por ejemplo, el valor medio de los datos.</span><span class="sxs-lookup"><span data-stu-id="604b4-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="604b4-121">Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-121">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-122">Tenga en cuenta que el último elemento de nuestra lista tiene un valor ausente para `Price`.</span><span class="sxs-lookup"><span data-stu-id="604b4-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="604b4-123">Para reemplazar los valores ausentes en la columna `Price`, use el método [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) para rellenar ese valor ausente.</span><span class="sxs-lookup"><span data-stu-id="604b4-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="604b4-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) solo funciona con datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="604b4-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="604b4-125">ML.NET admite varios [modos de reemplazo](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="604b4-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="604b4-126">El ejemplo anterior usa el modo de reemplazo `Mean` que rellenará el valor ausente con el valor medio de esa columna.</span><span class="sxs-lookup"><span data-stu-id="604b4-126">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="604b4-127">El resultado del reemplazo se rellena en la propiedad `Price` para el último elemento en nuestros datos con 200 000, ya que es la media de 100 000 y 300 000.</span><span class="sxs-lookup"><span data-stu-id="604b4-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="604b4-128">Usar normalizadores</span><span class="sxs-lookup"><span data-stu-id="604b4-128">Use normalizers</span></span>

<span data-ttu-id="604b4-129">La [normalización](https://en.wikipedia.org/wiki/Feature_scaling) es una técnica de preprocesamiento de datos que se utiliza para normalizar las características que no están en la misma escala, lo que ayuda a los algoritmos a converger con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="604b4-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="604b4-130">Por ejemplo, los intervalos de valores como la edad y los ingresos varían significativamente, ya que la edad suele estar en el intervalo de 0 a 100 y los ingresos suelen estar en el intervalo de cero a miles.</span><span class="sxs-lookup"><span data-stu-id="604b4-130">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="604b4-131">Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de normalización.</span><span class="sxs-lookup"><span data-stu-id="604b4-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="604b4-132">Normalización mínima-máxima</span><span class="sxs-lookup"><span data-stu-id="604b4-132">Min-Max normalization</span></span>

<span data-ttu-id="604b4-133">Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-133">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-134">La normalización se puede aplicar a las columnas con valores numéricos individuales, así como a los vectores.</span><span class="sxs-lookup"><span data-stu-id="604b4-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="604b4-135">Normalice los datos de la columna `Price` mediante la normalización mínima-máxima con el método [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).</span><span class="sxs-lookup"><span data-stu-id="604b4-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="604b4-136">Los valores originales del precio `[200000,100000]` se convierten en `[ 1, 0.5 ]` mediante la fórmula de normalización `MinMax` que genera valores de salida en el intervalo entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="604b4-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="604b4-137">Discretización</span><span class="sxs-lookup"><span data-stu-id="604b4-137">Binning</span></span>

<span data-ttu-id="604b4-138">La [discretización](https://en.wikipedia.org/wiki/Data_binning) convierte valores continuos en una representación discreta de la entrada.</span><span class="sxs-lookup"><span data-stu-id="604b4-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="604b4-139">Por ejemplo, suponga que una de sus características es la edad.</span><span class="sxs-lookup"><span data-stu-id="604b4-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="604b4-140">En lugar de usar el valor de edad real, la discretización crea intervalos para ese valor.</span><span class="sxs-lookup"><span data-stu-id="604b4-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="604b4-141">0-18 puede ser un rango, otro podría ser 19-35 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="604b4-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="604b4-142">Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-142">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-143">Normalice los datos en rangos con el método [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*).</span><span class="sxs-lookup"><span data-stu-id="604b4-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="604b4-144">El parámetro `maximumBinCount` permite especificar el número de rangos necesarios para clasificar los datos.</span><span class="sxs-lookup"><span data-stu-id="604b4-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="604b4-145">En este ejemplo, los datos se colocarán en dos rangos.</span><span class="sxs-lookup"><span data-stu-id="604b4-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="604b4-146">El resultado de la discretización crea límites de rangos de `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="604b4-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="604b4-147">Por lo tanto, los rangos resultantes son `[0,1,1]` porque la primera observación está comprendida entre 0 y 200 000 y las demás son mayores que 200 000, pero menores que infinito.</span><span class="sxs-lookup"><span data-stu-id="604b4-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="604b4-148">Trabajar con datos categóricos</span><span class="sxs-lookup"><span data-stu-id="604b4-148">Work with categorical data</span></span>

<span data-ttu-id="604b4-149">Los datos de categorías no numéricas deben convertirse en un número antes de usarse para generar un modelo de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="604b4-149">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span>

<span data-ttu-id="604b4-150">Uso de los siguientes datos de entrada que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-150">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-151">La propiedad `VehicleType` categórica se puede convertir en un número con el método [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*).</span><span class="sxs-lookup"><span data-stu-id="604b4-151">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span>

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="604b4-152">La transformación resultante convierte el valor de texto de `VehicleType` en un número.</span><span class="sxs-lookup"><span data-stu-id="604b4-152">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="604b4-153">Las entradas de la columna `VehicleType` se convierten en lo siguiente cuando se aplica la transformación:</span><span class="sxs-lookup"><span data-stu-id="604b4-153">The entries in the `VehicleType` column become the following when the transform is applied:</span></span>

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="604b4-154">Trabajar con datos de texto</span><span class="sxs-lookup"><span data-stu-id="604b4-154">Work with text data</span></span>

<span data-ttu-id="604b4-155">Los datos de texto deben transformarse en números antes de usarlos para crear un modelo de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="604b4-155">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="604b4-156">Visite la [página de transformaciones](../resources/transforms.md) para ver una lista más detallada y una descripción de las transformaciones de texto.</span><span class="sxs-lookup"><span data-stu-id="604b4-156">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="604b4-157">Uso de datos, como los datos siguientes que se han cargado en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="604b4-157">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="604b4-158">El paso mínimo para convertir texto en una representación numérica del vector es usar el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="604b4-158">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="604b4-159">Mediante el uso de la transformación [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*), se aplican una serie de transformaciones a la columna de texto de entrada resultante en un vector numérico que representa la palabra lp-normalizada y las n-gramas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="604b4-159">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="604b4-160">La transformación resultante podría convertir los valores de texto en la columna `Description` en un vector numérico que es similar a la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="604b4-160">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="604b4-161">Combine pasos complejos de procesamiento de texto en un [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) para quitar ruido y reducir potencialmente la cantidad de recursos de procesamiento requeridos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="604b4-161">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="604b4-162">`textEstimator` contiene un subconjunto de operaciones realizadas por el método [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="604b4-162">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="604b4-163">La ventaja de una canalización más compleja es el control y la visibilidad sobre las transformaciones aplicadas a los datos.</span><span class="sxs-lookup"><span data-stu-id="604b4-163">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="604b4-164">Con la primera entrada como ejemplo, la siguiente es una descripción detallada de los resultados producidos por los pasos de transformación definidos por `textEstimator`:</span><span class="sxs-lookup"><span data-stu-id="604b4-164">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="604b4-165">**Texto original: Este es un buen producto**</span><span class="sxs-lookup"><span data-stu-id="604b4-165">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="604b4-166">Transformación</span><span class="sxs-lookup"><span data-stu-id="604b4-166">Transform</span></span> | <span data-ttu-id="604b4-167">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="604b4-167">Description</span></span> | <span data-ttu-id="604b4-168">Resultado</span><span class="sxs-lookup"><span data-stu-id="604b4-168">Result</span></span>
|--|--|--|
|<span data-ttu-id="604b4-169">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="604b4-169">1. NormalizeText</span></span> | <span data-ttu-id="604b4-170">Convierte todas las letras en minúsculas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="604b4-170">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="604b4-171">este es un buen producto</span><span class="sxs-lookup"><span data-stu-id="604b4-171">this is a good product</span></span>
|<span data-ttu-id="604b4-172">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="604b4-172">2. TokenizeWords</span></span> | <span data-ttu-id="604b4-173">Divide la cadena en palabras individuales</span><span class="sxs-lookup"><span data-stu-id="604b4-173">Splits string into individual words</span></span> | <span data-ttu-id="604b4-174">["este","es","un","buen","producto"]</span><span class="sxs-lookup"><span data-stu-id="604b4-174">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="604b4-175">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="604b4-175">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="604b4-176">Quita las palabras irrelevantes como *es* y *un*.</span><span class="sxs-lookup"><span data-stu-id="604b4-176">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="604b4-177">["buen","producto"]</span><span class="sxs-lookup"><span data-stu-id="604b4-177">["good","product"]</span></span>
|<span data-ttu-id="604b4-178">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="604b4-178">4. MapValueToKey</span></span> | <span data-ttu-id="604b4-179">Asigna los valores a las claves (categorías), según los datos de entrada</span><span class="sxs-lookup"><span data-stu-id="604b4-179">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="604b4-180">[1,2]</span><span class="sxs-lookup"><span data-stu-id="604b4-180">[1,2]</span></span>
|<span data-ttu-id="604b4-181">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="604b4-181">5. ProduceNGrams</span></span> | <span data-ttu-id="604b4-182">Transforma texto en secuencia de palabras consecutivas</span><span class="sxs-lookup"><span data-stu-id="604b4-182">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="604b4-183">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="604b4-183">[1,1,1,0,0]</span></span>
|<span data-ttu-id="604b4-184">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="604b4-184">6. NormalizeLpNorm</span></span> | <span data-ttu-id="604b4-185">Escala las entradas por su valor lp-norm</span><span class="sxs-lookup"><span data-stu-id="604b4-185">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="604b4-186">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="604b4-186">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
