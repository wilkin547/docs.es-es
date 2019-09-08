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
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="47be9-102">Ver datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="47be9-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="47be9-103">Puede tener <xref:System.Data.DataTable> acceso al contenido de mediante las colecciones **Rows** y **Columns** de **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="47be9-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="47be9-104">También puede utilizar el <xref:System.Data.DataTable.Select%2A> método para devolver subconjuntos de los datos de una **DataTable** según criterios, como criterios de búsqueda, criterio de ordenación y estado de fila.</span><span class="sxs-lookup"><span data-stu-id="47be9-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="47be9-105">Además, puede utilizar el <xref:System.Data.DataRowCollection.Find%2A> método de la **DataRowCollection** al buscar una fila determinada mediante un valor de clave principal.</span><span class="sxs-lookup"><span data-stu-id="47be9-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="47be9-106">El método **Select** del objeto **DataTable** devuelve un conjunto de <xref:System.Data.DataRow> objetos que coinciden con los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="47be9-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="47be9-107">**Select** toma argumentos opcionales de una expresión de filtro, una expresión de ordenación y un **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="47be9-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="47be9-108">La expresión de filtro identifica qué filas se van a devolver en función de los valores `LastName = 'Smith'`DataColumn, como.</span><span class="sxs-lookup"><span data-stu-id="47be9-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="47be9-109">La expresión de ordenación sigue convenciones SQL estándar para ordenar columnas, por ejemplo `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="47be9-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="47be9-110">Para obtener las reglas sobre la escritura de <xref:System.Data.DataColumn.Expression%2A> expresiones, vea la propiedad de la clase **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="47be9-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="47be9-111">Si está realizando una serie de llamadas al método **Select** de una **DataTable**, puede aumentar el rendimiento creando primero un <xref:System.Data.DataView> para el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="47be9-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="47be9-112">Al crear el **DataView** , se indizan las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="47be9-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="47be9-113">A continuación, el método **Select** utiliza ese índice, lo que reduce significativamente el tiempo para generar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="47be9-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="47be9-114">Para obtener información sobre cómo crear una **DataView** para una **DataTable**, vea la [vista](dataviews.md)datos.</span><span class="sxs-lookup"><span data-stu-id="47be9-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="47be9-115">El método **Select** determina qué versión de las filas se van a ver o manipular basándose <xref:System.Data.DataViewRowState>en un.</span><span class="sxs-lookup"><span data-stu-id="47be9-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="47be9-116">En la tabla siguiente se describen los posibles valores de enumeración de **DataViewRowState** .</span><span class="sxs-lookup"><span data-stu-id="47be9-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="47be9-117">Valor DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="47be9-117">DataViewRowState value</span></span>|<span data-ttu-id="47be9-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="47be9-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="47be9-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="47be9-119">**CurrentRows**</span></span>|<span data-ttu-id="47be9-120">Filas actuales, incluidas las filas sin modificar, agregadas y modificadas.</span><span class="sxs-lookup"><span data-stu-id="47be9-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="47be9-121">**Borró**</span><span class="sxs-lookup"><span data-stu-id="47be9-121">**Deleted**</span></span>|<span data-ttu-id="47be9-122">Una fila eliminada.</span><span class="sxs-lookup"><span data-stu-id="47be9-122">A deleted row.</span></span>|
|<span data-ttu-id="47be9-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="47be9-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="47be9-124">Una versión actual, que es una versión modificada de los datos originales.</span><span class="sxs-lookup"><span data-stu-id="47be9-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="47be9-125">(Vea **ModifiedOriginal**).</span><span class="sxs-lookup"><span data-stu-id="47be9-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="47be9-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="47be9-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="47be9-127">Versión original de todas las filas modificadas.</span><span class="sxs-lookup"><span data-stu-id="47be9-127">The original version of all modified rows.</span></span> <span data-ttu-id="47be9-128">La versión actual está disponible mediante **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="47be9-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="47be9-129">**Agregué**</span><span class="sxs-lookup"><span data-stu-id="47be9-129">**Added**</span></span>|<span data-ttu-id="47be9-130">Una fila nueva.</span><span class="sxs-lookup"><span data-stu-id="47be9-130">A new row.</span></span>|
|<span data-ttu-id="47be9-131">**None**</span><span class="sxs-lookup"><span data-stu-id="47be9-131">**None**</span></span>|<span data-ttu-id="47be9-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47be9-132">None.</span></span>|
|<span data-ttu-id="47be9-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="47be9-133">**OriginalRows**</span></span>|<span data-ttu-id="47be9-134">Filas originales, incluidas las filas sin modificar y las eliminadas.</span><span class="sxs-lookup"><span data-stu-id="47be9-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="47be9-135">**Sin cambios**</span><span class="sxs-lookup"><span data-stu-id="47be9-135">**Unchanged**</span></span>|<span data-ttu-id="47be9-136">Una fila sin modificar.</span><span class="sxs-lookup"><span data-stu-id="47be9-136">An unchanged row.</span></span>|

<span data-ttu-id="47be9-137">En el ejemplo siguiente, el objeto **DataSet** se filtra para que solo esté trabajando con filas cuyo **DataViewRowState** está establecido en **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="47be9-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="47be9-138">El método **Select** se puede usar para devolver filas con valores de **RowState** o valores de campo diferentes.</span><span class="sxs-lookup"><span data-stu-id="47be9-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="47be9-139">En el ejemplo siguiente se devuelve una matriz **DataRow** que hace referencia a todas las filas que se han eliminado y devuelve otra matriz **DataRow** que hace referencia a todas las filas, ordenadas por **CustLName**, donde la columna **CustID** es mayor que 5.</span><span class="sxs-lookup"><span data-stu-id="47be9-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="47be9-140">Para obtener información sobre cómo ver la información de la fila **eliminada** , vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="47be9-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="47be9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="47be9-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="47be9-142">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="47be9-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="47be9-143">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="47be9-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="47be9-144">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47be9-144">ADO.NET Overview</span></span>](../ado-net-overview.md)
