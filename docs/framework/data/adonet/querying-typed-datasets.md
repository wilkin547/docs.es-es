---
title: Consultar objetos DataSet con tipo
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200950"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="79ba5-102">Consultar objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="79ba5-102">Query typed DataSets</span></span>

<span data-ttu-id="79ba5-103">Si el esquema de la <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda que use un tipo <xref:System.Data.DataSet> al usar LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="79ba5-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="79ba5-104">Un tipo <xref:System.Data.DataSet> es una clase que deriva de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="79ba5-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="79ba5-105">Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="79ba5-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="79ba5-106">Además, un tipo <xref:System.Data.DataSet> proporciona propiedades, eventos y métodos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="79ba5-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="79ba5-107">Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.</span><span class="sxs-lookup"><span data-stu-id="79ba5-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="79ba5-108">Esto hace que las consultas sean más sencillas y más legibles.</span><span class="sxs-lookup"><span data-stu-id="79ba5-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="79ba5-109">Para obtener más información, consulte [DataSets con tipo](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="79ba5-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="79ba5-110">LINQ to DataSet también admite consultas a través de un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="79ba5-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="79ba5-111">Con un tipo <xref:System.Data.DataSet>, no es necesario usar el tipo genérico <xref:System.Data.DataRowExtensions.Field%2A> método o <xref:System.Data.DataRowExtensions.SetField%2A> método para acceder a los datos de columna.</span><span class="sxs-lookup"><span data-stu-id="79ba5-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="79ba5-112">Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo se incluye en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="79ba5-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="79ba5-113">LINQ to DataSet proporciona acceso a los valores de columna del tipo correcto, por lo que se detectan errores de coincidencia de tipo cuando se compila el código en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="79ba5-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="79ba5-114">Antes de poder empezar a consultar con tipo <xref:System.Data.DataSet>, debe generar la clase mediante el **Diseñador de DataSet** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="79ba5-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="79ba5-115">Para obtener más información, consulte [crear y configurar conjuntos de datos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="79ba5-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="79ba5-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79ba5-116">Example</span></span>

<span data-ttu-id="79ba5-117">En el siguiente ejemplo se muestra una consulta sobre un <xref:System.Data.DataSet> con tipo:</span><span class="sxs-lookup"><span data-stu-id="79ba5-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="79ba5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="79ba5-118">See also</span></span>

- [<span data-ttu-id="79ba5-119">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="79ba5-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="79ba5-120">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="79ba5-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="79ba5-121">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="79ba5-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
