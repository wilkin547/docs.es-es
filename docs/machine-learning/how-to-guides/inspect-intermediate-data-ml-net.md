---
title: Inspección de los valores de datos intermedios durante el procesamiento de ML.NET
description: Obtenga más información sobre cómo inspeccionar los valores reales de los datos intermedios durante el procesamiento de canalizaciones de aprendizaje de automático de ML.NET.
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 06c4a473841db62a10dfc24025f842df7ae2c583
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063515"
---
# <a name="inspect-intermediate-data-values-during-processing"></a><span data-ttu-id="713ce-103">Inspección de los valores de datos intermedios durante el procesamiento</span><span class="sxs-lookup"><span data-stu-id="713ce-103">Inspect intermediate data values during processing</span></span>

<span data-ttu-id="713ce-104">Obtenga información sobre cómo inspeccionar valores durante los pasos de carga, procesamiento y entrenamiento en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="713ce-104">Learn how to inspect values during loading, processing and training steps in ML.NET.</span></span>

<span data-ttu-id="713ce-105">Los datos como los representados a continuación, que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView), pueden inspeccionarse de varias maneras en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="713ce-105">Data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>
 
```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="713ce-106">Conversión de IDataView en IEnumerable</span><span class="sxs-lookup"><span data-stu-id="713ce-106">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="713ce-107">Una de las formas más rápidas de inspeccionar los valores de una clase [`IDataView`](xref:Microsoft.ML.IDataView) es convertirla en una clase [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="713ce-107">One of the quickest ways to inspect the values of an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="713ce-108">Para convertir una clase [`IDataView`](xref:Microsoft.ML.IDataView) en [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), utilice el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).</span><span class="sxs-lookup"><span data-stu-id="713ce-108">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span> 

<span data-ttu-id="713ce-109">Para optimizar el rendimiento, establezca el valor de `reuseRowObject` en `true`.</span><span class="sxs-lookup"><span data-stu-id="713ce-109">To optimize performance, set the value of `reuseRowObject` to `true`.</span></span> <span data-ttu-id="713ce-110">De esta forma, se rellenará de forma diferida el mismo objeto con los datos de la fila actual a medida que se evalúa, en lugar de crear un nuevo objeto para cada fila del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="713ce-110">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

<span data-ttu-id="713ce-111">Si solo necesita acceder a parte de los datos o a índices específicos, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) y establezca el valor del parámetro `reuseRowObject` en `false` para que se cree un objeto por cada una de las filas solicitadas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="713ce-111">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="713ce-112">Después, convierta [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) en una matriz o lista.</span><span class="sxs-lookup"><span data-stu-id="713ce-112">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="713ce-113">Al convertir el resultado de [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) en una matriz o lista, se cargarán todas las filas de [`IDataView`](xref:Microsoft.ML.IDataView) solicitadas en la memoria, lo que puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="713ce-113">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="713ce-114">Cuando se haya creado la colección, podrá realizar operaciones en los datos.</span><span class="sxs-lookup"><span data-stu-id="713ce-114">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="713ce-115">El siguiente fragmento de código toma las tres primeras filas del conjunto de datos y calcula el promedio de precio actual.</span><span class="sxs-lookup"><span data-stu-id="713ce-115">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
``` 

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="713ce-116">Inspección de valores de una sola columna</span><span class="sxs-lookup"><span data-stu-id="713ce-116">Inspect values in a single column</span></span>

<span data-ttu-id="713ce-117">En cualquier momento del proceso de compilación del modelo, se puede acceder a los valores de una sola columna de una [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="713ce-117">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="713ce-118">El método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) devuelve todos los valores en una sola columna como una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="713ce-118">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="713ce-119">Inspección de valores de IDataView fila por fila</span><span class="sxs-lookup"><span data-stu-id="713ce-119">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="713ce-120">[`IDataView`](xref:Microsoft.ML.IDataView) se evalúa de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="713ce-120">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="713ce-121">Para recorrer en iteración las filas de una [`IDataView`](xref:Microsoft.ML.IDataView) sin convertirla en una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) como se ha mostrado en las secciones anteriores de este documento, cree una clase [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) usando el método [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) y pasando la clase [DataViewSchema](xref:Microsoft.ML.DataViewSchema) de su [`IDataView`](xref:Microsoft.ML.IDataView) como parámetro.</span><span class="sxs-lookup"><span data-stu-id="713ce-121">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="713ce-122">Luego, para recorrer las filas en iteración, utilice el método de cursor [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) junto con delegados de [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) para extraer los valores correspondientes de cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="713ce-122">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="713ce-123">A efectos de rendimiento, los vectores en ML.NET utilizan [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) en lugar de los tipos de colección nativos (es decir, `Vector`,`float[]`).</span><span class="sxs-lookup"><span data-stu-id="713ce-123">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span> 

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);
    
    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="713ce-124">Vista previa de los resultados de preprocesamiento o entrenamiento en un subconjunto de los datos</span><span class="sxs-lookup"><span data-stu-id="713ce-124">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="713ce-125">No use `Preview` en código de producción porque está pensado para depuración y puede reducir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="713ce-125">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="713ce-126">El proceso de compilación de modelos es experimental e iterativo.</span><span class="sxs-lookup"><span data-stu-id="713ce-126">The model building process is experimental and iterative.</span></span> <span data-ttu-id="713ce-127">Para obtener una vista previa de los datos después del preprocesamiento o entrenamiento de un modelo de Machine Learning en un subconjunto de los datos, utilice el método [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) que devuelve una [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span><span class="sxs-lookup"><span data-stu-id="713ce-127">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="713ce-128">El resultado es un objeto con las propiedades `ColumnView` y `RowView` que son ambas una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) y contienen los valores de una fila o columna en particular.</span><span class="sxs-lookup"><span data-stu-id="713ce-128">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="713ce-129">Especifique el número de filas a las que se aplicará la transformación con el parámetro `maxRows`.</span><span class="sxs-lookup"><span data-stu-id="713ce-129">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![Objeto de vista previa del depurador de datos](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="713ce-131">El resultado de inspeccionar una [`IDataView`](xref:Microsoft.ML.IDataView) tendría un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="713ce-131">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![Vista de filas de vista previa del depurador de datos](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
