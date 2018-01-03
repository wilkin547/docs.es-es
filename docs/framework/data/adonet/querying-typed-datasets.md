---
title: Consultar objetos DataSet con tipo
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c232ca2888c957bea33d06c84a62b00fdc7fd80c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="146ef-102">Consultar objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="146ef-102">Querying Typed DataSets</span></span>
<span data-ttu-id="146ef-103">Si el esquema de <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda usar un <xref:System.Data.DataSet> con tipo al utilizar [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="146ef-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="146ef-104">Un tipo <xref:System.Data.DataSet> es una clase que deriva de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="146ef-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="146ef-105">Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="146ef-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="146ef-106">Además, un tipo <xref:System.Data.DataSet> proporciona métodos fuertemente tipados, eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="146ef-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="146ef-107">Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.</span><span class="sxs-lookup"><span data-stu-id="146ef-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="146ef-108">Esto hace que las consultas sean más sencillas y más legibles.</span><span class="sxs-lookup"><span data-stu-id="146ef-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="146ef-109">Para obtener más información, consulte [conjuntos de datos con tipo](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="146ef-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="146ef-110">también admite las consultas en un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="146ef-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="146ef-111">Con un tipo <xref:System.Data.DataSet>, no es necesario utilizar la interfaz genérica <xref:System.Data.DataRowExtensions.Field%2A> método o <xref:System.Data.DataRowExtensions.SetField%2A> método para acceder a los datos de columna.</span><span class="sxs-lookup"><span data-stu-id="146ef-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="146ef-112">Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo se incluye en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="146ef-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="146ef-113">proporciona acceso a valores de columna como tipo correcto para que los errores de falta de coincidencia de tipos se interceptan cuando se compila el código en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="146ef-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="146ef-114">Antes de poder empezar a consultar un <xref:System.Data.DataSet> con tipo se debe generar la clase usando el Diseñador de DataSet de [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="146ef-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="146ef-115">Para obtener más información, vea [Crear y configurar conjuntos de datos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="146ef-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="146ef-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="146ef-116">Example</span></span>  
 <span data-ttu-id="146ef-117">En el siguiente ejemplo se muestra una consulta sobre un <xref:System.Data.DataSet> con tipo:</span><span class="sxs-lookup"><span data-stu-id="146ef-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="146ef-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="146ef-118">See Also</span></span>  
 [<span data-ttu-id="146ef-119">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="146ef-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="146ef-120">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="146ef-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="146ef-121">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="146ef-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
