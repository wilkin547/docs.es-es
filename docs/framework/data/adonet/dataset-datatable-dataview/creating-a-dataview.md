---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: b88df66ef2e065d1db8d4033eb1fb0e47ebdd189
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46322379"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="9b60a-102">Crear un objeto DataView</span><span class="sxs-lookup"><span data-stu-id="9b60a-102">Creating a DataView</span></span>
<span data-ttu-id="9b60a-103">Hay dos formas de crear una <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="9b60a-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="9b60a-104">Puede usar el **DataView** constructor, o bien puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de la <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="9b60a-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9b60a-105">El **DataView** constructor puede estar vacío o puede aceptar también una **DataTable** como un solo argumento, o un **DataTable** junto con los criterios de filtro, los criterios de ordenación y una fila filtro de estado.</span><span class="sxs-lookup"><span data-stu-id="9b60a-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="9b60a-106">Para obtener más información acerca de los argumentos adicionales disponibles para su uso con el **DataView**, consulte [ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="9b60a-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="9b60a-107">Porque el índice para un **DataView** se compila cuando la **DataView** se crea y cuando cualquiera de los **ordenación**, **RowFilter**, o  **RowStateFilter** se modifican las propiedades, lograr el mejor rendimiento suministra cualquier criterio de ordenación inicial o criterios de filtro como argumentos de constructor al crear el **DataView**.</span><span class="sxs-lookup"><span data-stu-id="9b60a-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="9b60a-108">Creación de un **DataView** sin especificar el criterio de ordenación o filtro y, a continuación, establecer el **ordenación**, **RowFilter**, o **RowStateFilter** las propiedades más adelante hace que el índice que se crea al menos dos veces: una vez cuando el **DataView** se crea, y vuelva a cualquiera de las propiedades de ordenación o filtro se modificó.</span><span class="sxs-lookup"><span data-stu-id="9b60a-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="9b60a-109">Tenga en cuenta que si crea un **DataView** utilizando el constructor que no toma ningún argumento, no podrá usar el **DataView** hasta que haya establecido el **tabla** propiedad .</span><span class="sxs-lookup"><span data-stu-id="9b60a-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="9b60a-110">En el ejemplo de código siguiente se muestra cómo crear un **DataView** utilizando el **DataView** constructor.</span><span class="sxs-lookup"><span data-stu-id="9b60a-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="9b60a-111">Un **RowFilter**, **ordenación** columna, y **DataViewRowState** se suministran junto con el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="9b60a-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="9b60a-112">En el ejemplo de código siguiente se muestra cómo obtener una referencia al valor predeterminado **DataView** de un **DataTable** utilizando el **DefaultView** propiedad de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b60a-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b60a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b60a-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="9b60a-114">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="9b60a-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="9b60a-115">Ordenación y filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="9b60a-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="9b60a-116">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="9b60a-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="9b60a-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="9b60a-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
