---
title: Crear un objeto DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1a8529c317025dbabd9c7467557b244b2f452a77
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-dataview"></a><span data-ttu-id="8d4e0-102">Crear un objeto DataView</span><span class="sxs-lookup"><span data-stu-id="8d4e0-102">Creating a DataView</span></span>
<span data-ttu-id="8d4e0-103">Hay dos formas de crear una <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="8d4e0-104">Puede usar el **DataView** constructor, o puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de la <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="8d4e0-105">El **DataView** constructor puede estar vacío o puede aceptar también un **DataTable** como un argumento único, o un **DataTable** junto con los criterios de filtro, criterios de ordenación y una fila filtro de estado.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="8d4e0-106">Para obtener más información acerca de los argumentos adicionales disponibles para su uso con el **DataView**, consulte [ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="8d4e0-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="8d4e0-107">Dado que el índice de un **DataView** se compila cuando el **DataView** se crea y cuando se da alguna de la **ordenación**, **RowFilter**, o  **RowStateFilter** se modifican propiedades, conseguirá un rendimiento óptimo suministra cualquier criterio inicial de ordenación o criterios de filtrado como argumentos del constructor al crear el **DataView**.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="8d4e0-108">Crear un **DataView** sin especificar el criterio de ordenación o filtro y, a continuación, establecer el **ordenación**, **RowFilter**, o **RowStateFilter** propiedades más adelante hace que el índice que se crea al menos dos veces: una vez cuando el **DataView** se crea, y otra cuando cualquiera de las propiedades de ordenación o filtro se modifica.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="8d4e0-109">Tenga en cuenta que si crea un **DataView** utilizando el constructor que no toma ningún argumento, no podrá usar la **DataView** hasta que haya establecido la **tabla** propiedad .</span><span class="sxs-lookup"><span data-stu-id="8d4e0-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="8d4e0-110">En el ejemplo de código siguiente se muestra cómo crear un **DataView** mediante la **DataView** constructor.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="8d4e0-111">A **RowFilter**, **ordenación** columna, y **DataViewRowState** se suministran junto con el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="8d4e0-112">En el ejemplo de código siguiente se muestra cómo obtener una referencia a la predeterminada **DataView** de un **DataTable** mediante la **DefaultView** propiedad de la tabla.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d4e0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d4e0-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="8d4e0-114">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="8d4e0-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="8d4e0-115">Ordenación y filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="8d4e0-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="8d4e0-116">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="8d4e0-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="8d4e0-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8d4e0-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
