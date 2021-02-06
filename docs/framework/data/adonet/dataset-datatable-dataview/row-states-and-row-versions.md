---
description: 'Más información sobre: Estados de fila y versiones de fila'
title: Estados y versiones de filas
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 7d436ffcfcf59f5daa4fc6eaa9f9018b92e5c608
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651683"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="98eec-103">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="98eec-103">Row States and Row Versions</span></span>

<span data-ttu-id="98eec-104">ADO.NET administra las filas de las tablas mediante estados de fila y versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-104">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="98eec-105">Un estado de fila indica el estado de una fila; las versiones de fila mantienen los valores almacenados en una fila en cuanto se modifica, incluyendo los valores actuales, originales y predeterminados.</span><span class="sxs-lookup"><span data-stu-id="98eec-105">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="98eec-106">Por ejemplo, después de realizar una modificación en una columna de una fila, ésta adquiere el estado de fila `Modified` y dos versiones de fila:`Current`, que contiene los valores actuales de fila, y `Original`, que contiene los valores de fila antes de la modificación de la columna.</span><span class="sxs-lookup"><span data-stu-id="98eec-106">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="98eec-107">Cada objeto <xref:System.Data.DataRow> cuenta con la propiedad <xref:System.Data.DataRow.RowState%2A> que puede examinar para determinar el estado actual de la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-107">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="98eec-108">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración de `RowState`.</span><span class="sxs-lookup"><span data-stu-id="98eec-108">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="98eec-109">Valor de RowState</span><span class="sxs-lookup"><span data-stu-id="98eec-109">RowState value</span></span>|<span data-ttu-id="98eec-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="98eec-110">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="98eec-111">No se han hecho cambios desde la última llamada a `AcceptChanges` o desde que `DataAdapter.Fill` creó la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-111">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="98eec-112">Se ha agregado la fila a la tabla, pero no se ha llamado a `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="98eec-112">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="98eec-113">Se ha cambiado algún elemento de la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-113">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="98eec-114">Se ha eliminado la fila de una tabla y no se ha llamado a `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="98eec-114">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="98eec-115">La fila no forma parte de ninguna `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="98eec-115">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="98eec-116">El valor de `RowState` de una fila recién creada se establece en `Detached`.</span><span class="sxs-lookup"><span data-stu-id="98eec-116">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="98eec-117">Una vez que se ha agregado la nueva `DataRow` a `DataRowCollection` llamando al método `Add`, el valor de la propiedad `RowState` se establece en `Added`.</span><span class="sxs-lookup"><span data-stu-id="98eec-117">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> <span data-ttu-id="98eec-118">También se establece `Detached` en una fila que se ha quitado de una `DataRowCollection` con el método `Remove`, o mediante el método `Delete` seguido del método `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="98eec-118">`Detached` is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="98eec-119">Si se llama a `AcceptChanges` en un objeto <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow>, se quitan todas las filas con el estado de fila `Deleted`.</span><span class="sxs-lookup"><span data-stu-id="98eec-119">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="98eec-120">Las filas que quedan reciben el estado de fila `Unchanged` y los valores de la versión de fila `Original` se sobrescriben con los valores de la versión de fila `Current`.</span><span class="sxs-lookup"><span data-stu-id="98eec-120">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="98eec-121">Si se llama a `RejectChanges`, se quitan todas las filas con el estado de fila `Added`.</span><span class="sxs-lookup"><span data-stu-id="98eec-121">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="98eec-122">Las filas que quedan reciben el estado de fila `Unchanged` y los valores de la versión de fila `Current` se sobrescriben con los valores de la versión de fila `Original`.</span><span class="sxs-lookup"><span data-stu-id="98eec-122">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="98eec-123">Las distintas versiones de una fila se pueden ver pasando un parámetro <xref:System.Data.DataRowVersion> con la referencia de la columna, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="98eec-123">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="98eec-124">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración de `DataRowVersion`.</span><span class="sxs-lookup"><span data-stu-id="98eec-124">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="98eec-125">Valor de DataRowVersion</span><span class="sxs-lookup"><span data-stu-id="98eec-125">DataRowVersion value</span></span>|<span data-ttu-id="98eec-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="98eec-126">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="98eec-127">Valores actuales de la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-127">The current values for the row.</span></span> <span data-ttu-id="98eec-128">Esta versión de fila no está disponible para filas con un valor `RowState` en `Deleted`.</span><span class="sxs-lookup"><span data-stu-id="98eec-128">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="98eec-129">Ésta es la versión de fila predeterminada para una fila determinada.</span><span class="sxs-lookup"><span data-stu-id="98eec-129">The default row version for a particular row.</span></span> <span data-ttu-id="98eec-130">La versión de fila predeterminada para una fila `Added`, `Modified` o `Deleted` es `Current`.</span><span class="sxs-lookup"><span data-stu-id="98eec-130">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="98eec-131">La versión de fila predeterminada para una fila `Detached` es `Proposed`.</span><span class="sxs-lookup"><span data-stu-id="98eec-131">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="98eec-132">Valores originales de la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-132">The original values for the row.</span></span> <span data-ttu-id="98eec-133">Esta versión de fila no está disponible para filas con un valor `RowState` en `Added`.</span><span class="sxs-lookup"><span data-stu-id="98eec-133">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="98eec-134">Valores propuestos para la fila.</span><span class="sxs-lookup"><span data-stu-id="98eec-134">The proposed values for the row.</span></span> <span data-ttu-id="98eec-135">Esta versión de fila existe mientras dura una operación de edición en una fila, o para una fila que no forma parte de una `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="98eec-135">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="98eec-136">Se puede comprobar si una `DataRow` tiene una versión de fila concreta llamando al método <xref:System.Data.DataRow.HasVersion%2A> y pasando `DataRowVersion` como argumento.</span><span class="sxs-lookup"><span data-stu-id="98eec-136">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="98eec-137">Por ejemplo, `DataRow.HasVersion(DataRowVersion.Original)` devolverá `false` para las filas recién agregadas antes de llamar a `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="98eec-137">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="98eec-138">En el siguiente ejemplo de código, se muestran los valores en todas las filas eliminadas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="98eec-138">The following code example displays the values in all the deleted rows of a table.</span></span> <span data-ttu-id="98eec-139">Las filas `Deleted` no tienen una versión de fila `Current` y, por lo tanto, debe pasar `DataRowVersion.Original` cuando obtenga acceso a los valores de columna.</span><span class="sxs-lookup"><span data-stu-id="98eec-139">`Deleted` rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="98eec-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="98eec-140">See also</span></span>

- [<span data-ttu-id="98eec-141">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="98eec-141">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="98eec-142">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="98eec-142">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="98eec-143">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="98eec-143">DataAdapters and DataReaders</span></span>](../dataadapters-and-datareaders.md)
- [<span data-ttu-id="98eec-144">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98eec-144">ADO.NET Overview</span></span>](../ado-net-overview.md)
