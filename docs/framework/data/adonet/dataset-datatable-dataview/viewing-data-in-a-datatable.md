---
title: Ver datos en un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: c13f0b802b2714a17ea4014625a65ebd1b0011f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785855"
---
# <a name="viewing-data-in-a-datatable"></a>Ver datos en un objeto DataTable

Puede tener <xref:System.Data.DataTable> acceso al contenido de mediante las colecciones **Rows** y **Columns** de **DataTable**. También puede utilizar el <xref:System.Data.DataTable.Select%2A> método para devolver subconjuntos de los datos de una **DataTable** según criterios, como criterios de búsqueda, criterio de ordenación y estado de fila. Además, puede utilizar el <xref:System.Data.DataRowCollection.Find%2A> método de la **DataRowCollection** al buscar una fila determinada mediante un valor de clave principal.

El método **Select** del objeto **DataTable** devuelve un conjunto de <xref:System.Data.DataRow> objetos que coinciden con los criterios especificados. **Select** toma argumentos opcionales de una expresión de filtro, una expresión de ordenación y un **DataViewRowState**. La expresión de filtro identifica qué filas se van a devolver en función de los valores `LastName = 'Smith'`DataColumn, como. La expresión de ordenación sigue convenciones SQL estándar para ordenar columnas, por ejemplo `LastName ASC, FirstName ASC`. Para obtener las reglas sobre la escritura de <xref:System.Data.DataColumn.Expression%2A> expresiones, vea la propiedad de la clase **DataColumn** .

> [!TIP]
> Si está realizando una serie de llamadas al método **Select** de una **DataTable**, puede aumentar el rendimiento creando primero un <xref:System.Data.DataView> para el **DataTable**. Al crear el **DataView** , se indizan las filas de la tabla. A continuación, el método **Select** utiliza ese índice, lo que reduce significativamente el tiempo para generar el resultado de la consulta. Para obtener información sobre cómo crear una **DataView** para una **DataTable**, vea la [vista](dataviews.md)datos.

El método **Select** determina qué versión de las filas se van a ver o manipular basándose <xref:System.Data.DataViewRowState>en un. En la tabla siguiente se describen los posibles valores de enumeración de **DataViewRowState** .

|Valor DataViewRowState|DESCRIPCIÓN|
|----------------------------|-----------------|
|**CurrentRows**|Filas actuales, incluidas las filas sin modificar, agregadas y modificadas.|
|**Borró**|Una fila eliminada.|
|**ModifiedCurrent**|Una versión actual, que es una versión modificada de los datos originales. (Vea **ModifiedOriginal**).|
|**ModifiedOriginal**|Versión original de todas las filas modificadas. La versión actual está disponible mediante **ModifiedCurrent**.|
|**Agregué**|Una fila nueva.|
|**None**|Ninguno.|
|**OriginalRows**|Filas originales, incluidas las filas sin modificar y las eliminadas.|
|**Sin cambios**|Una fila sin modificar.|

En el ejemplo siguiente, el objeto **DataSet** se filtra para que solo esté trabajando con filas cuyo **DataViewRowState** está establecido en **CurrentRows**.

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

El método **Select** se puede usar para devolver filas con valores de **RowState** o valores de campo diferentes. En el ejemplo siguiente se devuelve una matriz **DataRow** que hace referencia a todas las filas que se han eliminado y devuelve otra matriz **DataRow** que hace referencia a todas las filas, ordenadas por **CustLName**, donde la columna **CustID** es mayor que 5. Para obtener información sobre cómo ver la información de la fila **eliminada** , vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [Manipulación de datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Estados y versiones de filas](row-states-and-row-versions.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
