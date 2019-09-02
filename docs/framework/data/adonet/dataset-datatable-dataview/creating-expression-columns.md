---
title: Crear columnas de expresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 8ae8c8e020a3d8ada5bdcd5037187e6f3abd33a4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203834"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="96fb5-102">Crear columnas de expresión</span><span class="sxs-lookup"><span data-stu-id="96fb5-102">Creating Expression Columns</span></span>
<span data-ttu-id="96fb5-103">Se puede definir una expresión para una columna, a fin de que pueda contener un valor calculado a partir de los valores de otra columna de la misma fila o de los valores de columna de varias filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="96fb5-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="96fb5-104">Para definir la expresión que se va a evaluar, utilice la propiedad <xref:System.Data.DataColumn.Expression%2A> de la columna de destino y la propiedad <xref:System.Data.DataColumn.ColumnName%2A> para hacer referencia a otras columnas en la expresión.</span><span class="sxs-lookup"><span data-stu-id="96fb5-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="96fb5-105">El <xref:System.Data.DataColumn.DataType%2A> para la columna de expresión debe ser adecuado para el valor que dicha expresión devuelve.</span><span class="sxs-lookup"><span data-stu-id="96fb5-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="96fb5-106">En la tabla siguiente se enumeran varios usos posibles de las columnas de expresión de una tabla.</span><span class="sxs-lookup"><span data-stu-id="96fb5-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="96fb5-107">Tipo de expresión</span><span class="sxs-lookup"><span data-stu-id="96fb5-107">Expression type</span></span>|<span data-ttu-id="96fb5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96fb5-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="96fb5-109">Comparación</span><span class="sxs-lookup"><span data-stu-id="96fb5-109">Comparison</span></span>|<span data-ttu-id="96fb5-110">"Total > = 500"</span><span class="sxs-lookup"><span data-stu-id="96fb5-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="96fb5-111">Cálculo</span><span class="sxs-lookup"><span data-stu-id="96fb5-111">Computation</span></span>|<span data-ttu-id="96fb5-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="96fb5-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="96fb5-113">Agregación</span><span class="sxs-lookup"><span data-stu-id="96fb5-113">Aggregation</span></span>|<span data-ttu-id="96fb5-114">Sum(Precio)</span><span class="sxs-lookup"><span data-stu-id="96fb5-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="96fb5-115">Puede establecer la propiedad **Expression** en un objeto **DataColumn** existente, o puede incluir la propiedad como el tercer argumento <xref:System.Data.DataColumn> pasado al constructor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="96fb5-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="96fb5-116">Las expresiones pueden hacer referencia a otras columnas de expresión; sin embargo, una referencia circular, en la que dos expresiones se hacen referencia una a otra, generará una excepción.</span><span class="sxs-lookup"><span data-stu-id="96fb5-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="96fb5-117">Para obtener las reglas sobre la escritura de <xref:System.Data.DataColumn.Expression%2A> expresiones, vea la propiedad de la clase **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="96fb5-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96fb5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="96fb5-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="96fb5-119">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="96fb5-119">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="96fb5-120">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="96fb5-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="96fb5-121">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="96fb5-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
