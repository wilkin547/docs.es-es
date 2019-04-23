---
title: Crear columnas de expresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 6e19e4e7cc0ea92e9d93e45c2a50d009e46b78c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175505"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="e69dd-102">Crear columnas de expresión</span><span class="sxs-lookup"><span data-stu-id="e69dd-102">Creating Expression Columns</span></span>
<span data-ttu-id="e69dd-103">Se puede definir una expresión para una columna, a fin de que pueda contener un valor calculado a partir de los valores de otra columna de la misma fila o de los valores de columna de varias filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e69dd-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="e69dd-104">Para definir la expresión que se va a evaluar, utilice la propiedad <xref:System.Data.DataColumn.Expression%2A> de la columna de destino y la propiedad <xref:System.Data.DataColumn.ColumnName%2A> para hacer referencia a otras columnas en la expresión.</span><span class="sxs-lookup"><span data-stu-id="e69dd-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="e69dd-105">El <xref:System.Data.DataColumn.DataType%2A> para la columna de expresión debe ser adecuado para el valor que dicha expresión devuelve.</span><span class="sxs-lookup"><span data-stu-id="e69dd-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="e69dd-106">En la tabla siguiente se enumeran varios usos posibles de las columnas de expresión de una tabla.</span><span class="sxs-lookup"><span data-stu-id="e69dd-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="e69dd-107">Tipo de expresión</span><span class="sxs-lookup"><span data-stu-id="e69dd-107">Expression type</span></span>|<span data-ttu-id="e69dd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e69dd-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="e69dd-109">Comparación</span><span class="sxs-lookup"><span data-stu-id="e69dd-109">Comparison</span></span>|<span data-ttu-id="e69dd-110">"Total > = 500"</span><span class="sxs-lookup"><span data-stu-id="e69dd-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="e69dd-111">Cálculo</span><span class="sxs-lookup"><span data-stu-id="e69dd-111">Computation</span></span>|<span data-ttu-id="e69dd-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="e69dd-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="e69dd-113">Agregación</span><span class="sxs-lookup"><span data-stu-id="e69dd-113">Aggregation</span></span>|<span data-ttu-id="e69dd-114">Sum(Precio)</span><span class="sxs-lookup"><span data-stu-id="e69dd-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="e69dd-115">Puede establecer el **expresión** propiedad en una existente **DataColumn** objeto, o puede incluir la propiedad como el tercer argumento pasado a la <xref:System.Data.DataColumn> constructor, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e69dd-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="e69dd-116">Las expresiones pueden hacer referencia a otras columnas de expresión; sin embargo, una referencia circular, en la que dos expresiones se hacen referencia una a otra, generará una excepción.</span><span class="sxs-lookup"><span data-stu-id="e69dd-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="e69dd-117">Las reglas de escritura de expresiones, vea el <xref:System.Data.DataColumn.Expression%2A> propiedad de la **DataColumn** clase.</span><span class="sxs-lookup"><span data-stu-id="e69dd-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69dd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e69dd-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="e69dd-119">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="e69dd-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="e69dd-120">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="e69dd-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="e69dd-121">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e69dd-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
