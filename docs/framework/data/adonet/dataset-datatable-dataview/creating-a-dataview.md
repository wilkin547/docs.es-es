---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 3e1c31dac458594eee70ddd99469aca7cf63b848
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785477"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="51f1f-102">Crear un objeto DataView</span><span class="sxs-lookup"><span data-stu-id="51f1f-102">Creating a DataView</span></span>
<span data-ttu-id="51f1f-103">Hay dos formas de crear una <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="51f1f-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="51f1f-104">Puede usar el constructor **DataView** o puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de. <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="51f1f-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="51f1f-105">El constructor de **DataView** puede estar vacío o puede tomar un **DataTable** como un solo argumento, o un **DataTable** junto con criterios de filtro, criterios de ordenación y un filtro de estado de fila.</span><span class="sxs-lookup"><span data-stu-id="51f1f-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="51f1f-106">Para obtener más información sobre los argumentos adicionales disponibles para su uso con **DataView**, vea [ordenar y filtrar datos](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="51f1f-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="51f1f-107">Dado que el índice de una **DataView** se genera cuando se crea la **DataView** y cuando se modifica cualquiera de las propiedades **Sort**, **RowFilter**o **RowStateFilter** , se obtiene el mejor rendimiento al proporcionar cualquier criterio de ordenación o filtrado como argumentos del constructor al crear **DataView**.</span><span class="sxs-lookup"><span data-stu-id="51f1f-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="51f1f-108">Crear una **DataView** sin especificar criterios de ordenación o de filtro y, a continuación, establecer las propiedades **Sort**, **RowFilter**o **RowStateFilter** más adelante hace que el índice se compile al menos dos veces: una vez cuando **DataView** es se crea y de nuevo cuando se modifica cualquiera de las propiedades de ordenación o filtro.</span><span class="sxs-lookup"><span data-stu-id="51f1f-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="51f1f-109">Tenga en cuenta que si crea una **DataView** con el constructor que no toma ningún argumento, no podrá usar la **DataView** hasta que haya establecido la propiedad de **tabla** .</span><span class="sxs-lookup"><span data-stu-id="51f1f-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="51f1f-110">En el ejemplo de código siguiente se muestra cómo crear una **DataView** mediante el constructor **DataView** .</span><span class="sxs-lookup"><span data-stu-id="51f1f-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="51f1f-111">Se proporcionan un **RowFilter**, una columna de **ordenación** y un **DataViewRowState** junto con la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="51f1f-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="51f1f-112">En el ejemplo de código siguiente se muestra cómo obtener una referencia a la **DataView** predeterminada de un **DataTable** mediante la propiedad **DefaultView** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="51f1f-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="51f1f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="51f1f-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="51f1f-114">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="51f1f-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="51f1f-115">Ordenación y filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="51f1f-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="51f1f-116">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="51f1f-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="51f1f-117">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="51f1f-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
