---
description: 'Más información sobre: ordenación y filtrado de datos'
title: Ordenar y filtrar datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: a8b74dc13e88f8d5e70bb27291e0e6e34817f0ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651618"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="59723-103">Ordenar y filtrar datos</span><span class="sxs-lookup"><span data-stu-id="59723-103">Sorting and Filtering Data</span></span>

<span data-ttu-id="59723-104">La <xref:System.Data.DataView> proporciona varias formas de ordenación y filtrado de datos en una <xref:System.Data.DataTable>:</span><span class="sxs-lookup"><span data-stu-id="59723-104">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="59723-105">Mediante la propiedad <xref:System.Data.DataView.Sort%2A> puede especificar criterios simples o múltiples de ordenación de columnas e incluir parámetros ASC (ascendente) y DESC (descendente).</span><span class="sxs-lookup"><span data-stu-id="59723-105">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="59723-106">Mediante la propiedad <xref:System.Data.DataView.ApplyDefaultSort%2A> puede crear automáticamente un criterio de ordenación, en orden ascendente, basado en la columna o columnas de clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="59723-106">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="59723-107"><xref:System.Data.DataView.ApplyDefaultSort%2A> solo se aplica cuando la propiedad **Sort** es una referencia nula o una cadena vacía y cuando la tabla tiene definida una clave principal.</span><span class="sxs-lookup"><span data-stu-id="59723-107"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="59723-108">Mediante la propiedad <xref:System.Data.DataView.RowFilter%2A> puede especificar subconjuntos de filas basándose en sus valores de columna.</span><span class="sxs-lookup"><span data-stu-id="59723-108">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="59723-109">Para obtener más información sobre las expresiones válidas para la propiedad **RowFilter** , vea la información de referencia de la <xref:System.Data.DataColumn.Expression%2A> propiedad de la <xref:System.Data.DataColumn> clase.</span><span class="sxs-lookup"><span data-stu-id="59723-109">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="59723-110">Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, use los <xref:System.Data.DataView.Find%2A> métodos o <xref:System.Data.DataView.FindRows%2A> de **DataView** para lograr el mejor rendimiento en lugar de establecer la propiedad **RowFilter** .</span><span class="sxs-lookup"><span data-stu-id="59723-110">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="59723-111">Al establecer la propiedad **RowFilter** se vuelve a generar el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="59723-111">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="59723-112">La propiedad **RowFilter** se utiliza mejor en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados.</span><span class="sxs-lookup"><span data-stu-id="59723-112">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="59723-113">Los métodos **Find** y **FindRows** aprovechan el índice actual sin necesidad de que se vuelva a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="59723-113">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="59723-114">Para obtener más información sobre los métodos **Find** y **FindRows** , vea [Buscar filas](finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="59723-114">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="59723-115">Mediante la propiedad <xref:System.Data.DataView.RowStateFilter%2A> puede especificar las versiones de fila que desea ver.</span><span class="sxs-lookup"><span data-stu-id="59723-115">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="59723-116">**DataView** administra implícitamente la versión de fila que se va a exponer según el **RowState** de la fila subyacente.</span><span class="sxs-lookup"><span data-stu-id="59723-116">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="59723-117">Por ejemplo, si el **RowStateFilter** está establecido en **DataViewRowState. Deleted**, la **DataView** expone la versión de fila **original** de todas las filas **eliminadas** porque no hay ninguna versión de fila **actual** .</span><span class="sxs-lookup"><span data-stu-id="59723-117">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="59723-118">Puede determinar la versión de fila de una fila que se expone mediante la propiedad **rowversion** de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="59723-118">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="59723-119">En la tabla siguiente se muestran las opciones de **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="59723-119">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="59723-120">Opciones de DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="59723-120">DataViewRowState options</span></span>|<span data-ttu-id="59723-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="59723-121">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="59723-122">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="59723-122">**CurrentRows**</span></span>|<span data-ttu-id="59723-123">Versión de fila **actual** de todas las filas **sin modificar**, **agregadas** y **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-123">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="59723-124">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="59723-124">This is the default.</span></span>|  
    |<span data-ttu-id="59723-125">**Agregado**</span><span class="sxs-lookup"><span data-stu-id="59723-125">**Added**</span></span>|<span data-ttu-id="59723-126">Versión de fila **actual** de todas las filas **agregadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-126">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="59723-127">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="59723-127">**Deleted**</span></span>|<span data-ttu-id="59723-128">La versión de fila **original** de todas las filas **eliminadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-128">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="59723-129">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="59723-129">**ModifiedCurrent**</span></span>|<span data-ttu-id="59723-130">Versión de fila **actual** de todas las filas **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-130">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="59723-131">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="59723-131">**ModifiedOriginal**</span></span>|<span data-ttu-id="59723-132">La versión de fila **original** de todas las filas **modificadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-132">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="59723-133">**Ninguno**</span><span class="sxs-lookup"><span data-stu-id="59723-133">**None**</span></span>|<span data-ttu-id="59723-134">Ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="59723-134">No rows.</span></span>|  
    |<span data-ttu-id="59723-135">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="59723-135">**OriginalRows**</span></span>|<span data-ttu-id="59723-136">La versión de fila **original** de todas las filas **sin modificar**, **modificadas** y **eliminadas** .</span><span class="sxs-lookup"><span data-stu-id="59723-136">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="59723-137">**Sin cambios**</span><span class="sxs-lookup"><span data-stu-id="59723-137">**Unchanged**</span></span>|<span data-ttu-id="59723-138">Versión de fila **actual** de todas las filas **sin modificar** .</span><span class="sxs-lookup"><span data-stu-id="59723-138">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="59723-139">Para obtener más información sobre los Estados de fila y las versiones de fila, vea [Estados de fila y versiones](row-states-and-row-versions.md)de fila.</span><span class="sxs-lookup"><span data-stu-id="59723-139">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="59723-140">En el siguiente ejemplo de código se crea una vista que muestra todos los productos cuyo número de unidades en existencia es menor o igual que el nivel de nuevo pedido, ordenados en primer lugar por id. de proveedor y después por nombre de producto.</span><span class="sxs-lookup"><span data-stu-id="59723-140">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59723-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="59723-141">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="59723-142">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="59723-142">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="59723-143">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="59723-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
