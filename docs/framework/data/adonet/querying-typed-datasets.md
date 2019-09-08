---
title: Consultar objetos DataSet con tipo
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782966"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="026ea-102">Consultar conjuntos de DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="026ea-102">Query typed DataSets</span></span>

<span data-ttu-id="026ea-103">Si el esquema de se <xref:System.Data.DataSet> conoce en tiempo de diseño de la aplicación, se recomienda usar un <xref:System.Data.DataSet> tipo cuando se use LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="026ea-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="026ea-104">Un con tipo <xref:System.Data.DataSet> es una clase que se deriva <xref:System.Data.DataSet>de.</span><span class="sxs-lookup"><span data-stu-id="026ea-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="026ea-105">Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="026ea-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="026ea-106">Además, un con tipo <xref:System.Data.DataSet> proporciona métodos, eventos y propiedades fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="026ea-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="026ea-107">Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.</span><span class="sxs-lookup"><span data-stu-id="026ea-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="026ea-108">Esto hace que las consultas sean más sencillas y más legibles.</span><span class="sxs-lookup"><span data-stu-id="026ea-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="026ea-109">Para obtener más información, vea conjuntos de datos [con tipo](./dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="026ea-109">For more information, see [Typed DataSets](./dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="026ea-110">LINQ to DataSet también admite la consulta en un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="026ea-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="026ea-111">Con un tipo <xref:System.Data.DataSet>, no es necesario utilizar el método o <xref:System.Data.DataRowExtensions.SetField%2A> método genérico <xref:System.Data.DataRowExtensions.Field%2A> para tener acceso a los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="026ea-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="026ea-112">Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo <xref:System.Data.DataSet>se incluye en.</span><span class="sxs-lookup"><span data-stu-id="026ea-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="026ea-113">LINQ to DataSet proporciona acceso a los valores de columna como tipo correcto, de modo que los errores de coincidencia de tipos se detectan cuando se compila el código en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="026ea-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="026ea-114">Antes de poder empezar a consultar un tipo <xref:System.Data.DataSet>, debe generar la clase mediante el diseñador de **DataSet** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="026ea-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="026ea-115">Para obtener más información, vea [crear y configurar conjuntos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)de datos.</span><span class="sxs-lookup"><span data-stu-id="026ea-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="026ea-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="026ea-116">Example</span></span>

<span data-ttu-id="026ea-117">En el siguiente ejemplo se muestra una consulta sobre un <xref:System.Data.DataSet> con tipo:</span><span class="sxs-lookup"><span data-stu-id="026ea-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a><span data-ttu-id="026ea-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="026ea-118">See also</span></span>

- [<span data-ttu-id="026ea-119">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="026ea-119">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="026ea-120">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="026ea-120">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="026ea-121">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="026ea-121">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
