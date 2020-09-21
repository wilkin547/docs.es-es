---
title: Inspección de los datos intermedios durante el procesamiento de ML.NET
description: Obtenga información sobre cómo inspeccionar los datos intermedios durante los pasos de entrenamiento del modelo, procesamiento y carga de canalización de aprendizaje automático en ML.NET.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 4f168653297594a604e6f381947f31cba5376178
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679630"
---
# <a name="inspect-intermediate-data-during-processing"></a>Inspección de los datos intermedios durante el procesamiento

Obtenga información sobre cómo inspeccionar los datos intermedios durante los pasos de entrenamiento del modelo, procesamiento y carga en ML.NET. Los datos intermedios son el resultado de cada fase de la canalización de aprendizaje automático.

Los datos intermedios, como los representados a continuación, que se cargan en un [`IDataView`](xref:Microsoft.ML.IDataView), pueden inspeccionarse de varias maneras en ML.NET.

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

## <a name="convert-idataview-to-ienumerable"></a>Conversión de IDataView en IEnumerable

Una de las formas más rápidas de inspeccionar una clase [`IDataView`](xref:Microsoft.ML.IDataView) es convertirla en una clase [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601). Para convertir una clase [`IDataView`](xref:Microsoft.ML.IDataView) en [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), utilice el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A).

Para optimizar el rendimiento, establezca `reuseRowObject` en `true`. De esta forma, se rellenará de forma diferida el mismo objeto con los datos de la fila actual a medida que se evalúa, en lugar de crear un nuevo objeto para cada fila del conjunto de datos.

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

## <a name="accessing-specific-indices-with-ienumerable"></a>Obtener acceso a índices específicos con IEnumerable

Si solo necesita acceder a parte de los datos o a índices específicos, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) y establezca el valor del parámetro `reuseRowObject` en `false` para que se cree un objeto por cada una de las filas solicitadas del conjunto de datos. Después, convierta [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) en una matriz o lista.

> [!WARNING]
> Al convertir el resultado de [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) en una matriz o lista, se cargarán todas las filas de [`IDataView`](xref:Microsoft.ML.IDataView) solicitadas en la memoria, lo que puede afectar al rendimiento.

Cuando se haya creado la colección, podrá realizar operaciones en los datos. El siguiente fragmento de código toma las tres primeras filas del conjunto de datos y calcula el promedio de precio actual.

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

## <a name="inspect-values-in-a-single-column"></a>Inspección de valores de una sola columna

En cualquier momento del proceso de compilación del modelo, se puede acceder a los valores de una sola columna de una [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A). El método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A) devuelve todos los valores en una sola columna como una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a>Inspección de valores de IDataView fila por fila

[`IDataView`](xref:Microsoft.ML.IDataView) se evalúa de forma diferida. Para recorrer en iteración las filas de una [`IDataView`](xref:Microsoft.ML.IDataView) sin convertirla en una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) como se ha mostrado en las secciones anteriores de este documento, cree una clase [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) usando el método [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor%2A) y pasando la clase [DataViewSchema](xref:Microsoft.ML.DataViewSchema) de su [`IDataView`](xref:Microsoft.ML.IDataView) como parámetro. Luego, para recorrer las filas en iteración, utilice el método de cursor [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext%2A) junto con delegados de [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) para extraer los valores correspondientes de cada una de las columnas.

> [!IMPORTANT]
> A efectos de rendimiento, los vectores en ML.NET utilizan [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) en lugar de los tipos de colección nativos (es decir, `Vector`,`float[]`).

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

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a>Vista previa de los resultados de preprocesamiento o entrenamiento en un subconjunto de los datos

> [!WARNING]
> No use `Preview` en código de producción porque está pensado para depuración y puede reducir el rendimiento.

El proceso de compilación de modelos es experimental e iterativo. Para obtener una vista previa de los datos después del preprocesamiento o entrenamiento de un modelo de Machine Learning en un subconjunto de los datos, utilice el método [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview%2A) que devuelve una [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview). El resultado es un objeto con las propiedades `ColumnView` y `RowView` que son ambas una [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) y contienen los valores de una fila o columna en particular. Especifique el número de filas a las que se aplicará la transformación con el parámetro `maxRows`.

![Objeto de vista previa del depurador de datos](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

El resultado de inspeccionar una [`IDataView`](xref:Microsoft.ML.IDataView) tendría un aspecto similar al siguiente:

![Vista de filas de vista previa del depurador de datos](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
