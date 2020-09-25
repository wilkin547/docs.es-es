---
title: Ordenar y filtrar datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 89e2fdf656fb06ee545ba936f033646ad86182d4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183382"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="b349d-102">Ordenar y filtrar datos</span><span class="sxs-lookup"><span data-stu-id="b349d-102">Sorting and Filtering Data</span></span>

<span data-ttu-id="b349d-103">La <xref:System.Data.DataView> proporciona varias formas de ordenación y filtrado de datos en una <xref:System.Data.DataTable>:</span><span class="sxs-lookup"><span data-stu-id="b349d-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="b349d-104">Mediante la propiedad <xref:System.Data.DataView.Sort%2A> puede especificar criterios simples o múltiples de ordenación de columnas e incluir parámetros ASC (ascendente) y DESC (descendente).</span><span class="sxs-lookup"><span data-stu-id="b349d-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="b349d-105">Mediante la propiedad <xref:System.Data.DataView.ApplyDefaultSort%2A> puede crear automáticamente un criterio de ordenación, en orden ascendente, basado en la columna o columnas de clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b349d-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="b349d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> solo se aplica cuando la propiedad **Sort** es una referencia nula o una cadena vacía y cuando la tabla tiene definida una clave principal.</span><span class="sxs-lookup"><span data-stu-id="b349d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="b349d-107">Mediante la propiedad <xref:System.Data.DataView.RowFilter%2A> puede especificar subconjuntos de filas basándose en sus valores de columna.</span><span class="sxs-lookup"><span data-stu-id="b349d-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="b349d-108">Para obtener más información sobre las expresiones válidas para la propiedad **RowFilter** , vea la información de referencia de la <xref:System.Data.DataColumn.Expression%2A> propiedad de la <xref:System.Data.DataColumn> clase.</span><span class="sxs-lookup"><span data-stu-id="b349d-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="b349d-109">Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, use los <xref:System.Data.DataView.Find%2A> métodos o <xref:System.Data.DataView.FindRows%2A> de **DataView** para lograr el mejor rendimiento en lugar de establecer la propiedad **RowFilter** .</span><span class="sxs-lookup"><span data-stu-id="b349d-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="b349d-110">Al establecer la propiedad **RowFilter** se vuelve a generar el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b349d-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="b349d-111">La propiedad **RowFilter** se utiliza mejor en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados.</span><span class="sxs-lookup"><span data-stu-id="b349d-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="b349d-112">Los métodos **Find** y **FindRows** aprovechan el índice actual sin necesidad de que se vuelva a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="b349d-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="b349d-113">Para obtener más información sobre los métodos **Find** y **FindRows** , vea [Buscar filas](finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="b349d-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="b349d-114">Mediante la propiedad <xref:System.Data.DataView.RowStateFilter%2A> puede especificar las versiones de fila que desea ver.</span><span class="sxs-lookup"><span data-stu-id="b349d-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="b349d-115">**DataView** administra implícitamente la versión de fila que se va a exponer según el **RowState** de la fila subyacente.</span><span class="sxs-lookup"><span data-stu-id="b349d-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="b349d-116">Por ejemplo, si el **RowStateFilter** está establecido en **DataViewRowState. Deleted**, la **DataView** expone la versión de fila **original** de todas las filas **eliminadas** porque no hay ninguna versión de fila **actual** .</span><span class="sxs-lookup"><span data-stu-id="b349d-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="b349d-117">Puede determinar la versión de fila de una fila que se expone mediante la propiedad **rowversion** de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b349d-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="b349d-118">En la tabla siguiente se muestran las opciones de **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="b349d-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="b349d-119">Opciones de DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="b349d-119">DataViewRowState options</span></span>|<span data-ttu-id="b349d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b349d-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="b349d-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="b349d-121">**CurrentRows**</span></span>|<span data-ttu-id="b349d-122">Versión de fila **actual** de todas las filas **sin modificar**, **agregadas**y **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="b349d-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b349d-123">This is the default.</span></span>|  
    |<span data-ttu-id="b349d-124">**Agregado**</span><span class="sxs-lookup"><span data-stu-id="b349d-124">**Added**</span></span>|<span data-ttu-id="b349d-125">Versión de fila **actual** de todas las filas **agregadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="b349d-126">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="b349d-126">**Deleted**</span></span>|<span data-ttu-id="b349d-127">La versión de fila **original** de todas las filas **eliminadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="b349d-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="b349d-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="b349d-129">Versión de fila **actual** de todas las filas **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="b349d-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="b349d-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="b349d-131">La versión de fila **original** de todas las filas **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="b349d-132">**None**</span><span class="sxs-lookup"><span data-stu-id="b349d-132">**None**</span></span>|<span data-ttu-id="b349d-133">Ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="b349d-133">No rows.</span></span>|  
    |<span data-ttu-id="b349d-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="b349d-134">**OriginalRows**</span></span>|<span data-ttu-id="b349d-135">La versión de fila **original** de todas las filas **sin modificar**, **modificadas**y **eliminadas** .</span><span class="sxs-lookup"><span data-stu-id="b349d-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="b349d-136">**Sin cambios**</span><span class="sxs-lookup"><span data-stu-id="b349d-136">**Unchanged**</span></span>|<span data-ttu-id="b349d-137">Versión de fila **actual** de todas las filas **sin modificar** .</span><span class="sxs-lookup"><span data-stu-id="b349d-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="b349d-138">Para obtener más información sobre los Estados de fila y las versiones de fila, vea [Estados de fila y versiones](row-states-and-row-versions.md)de fila.</span><span class="sxs-lookup"><span data-stu-id="b349d-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="b349d-139">En el siguiente ejemplo de código se crea una vista que muestra todos los productos cuyo número de unidades en existencia es menor o igual que el nivel de nuevo pedido, ordenados en primer lugar por id. de proveedor y después por nombre de producto.</span><span class="sxs-lookup"><span data-stu-id="b349d-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b349d-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b349d-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="b349d-141">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="b349d-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="b349d-142">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b349d-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
