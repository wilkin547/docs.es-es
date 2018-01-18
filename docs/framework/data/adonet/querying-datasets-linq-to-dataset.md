---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c9830587e70d7671200fac20c8384f1a470a751e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="b7f8d-102">Consultar conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b7f8d-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="b7f8d-103">Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="b7f8d-104">Formular consultas con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] es similar a usar [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] contra otros orígenes de datos habilitados para [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7f8d-104">Formulating queries with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="b7f8d-105">Recuerde, no obstante, que cuando se usa [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas con un <xref:System.Data.DataSet> objeto que está consultando una enumeración de <xref:System.Data.DataRow> objetos, en lugar de una enumeración de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="b7f8d-106">Esto significa que puede utilizar cualquiera de los miembros de la <xref:System.Data.DataRow> clase en su [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="b7f8d-107">Esto permite crear consultas amplias y complejas.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="b7f8d-108">Al igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consultas de dos formas diferentes: sintaxis de expresión consulta y sintaxis de consultas basadas en métodos.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="b7f8d-109">Para obtener más información acerca de estas dos formas, consulte [Introducción a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span><span class="sxs-lookup"><span data-stu-id="b7f8d-109">For more information about these two forms, see [Getting Started with LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span></span> <span data-ttu-id="b7f8d-110">Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-110">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7f8d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7f8d-111">In This Section</span></span>  
 [<span data-ttu-id="b7f8d-112">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="b7f8d-112">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="b7f8d-113">Describe cómo realizar consultas en una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-113">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="b7f8d-114">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="b7f8d-114">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="b7f8d-115">Describe cómo realizar consultas entre tablas.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-115">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="b7f8d-116">Consultar objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="b7f8d-116">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 <span data-ttu-id="b7f8d-117">Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="b7f8d-117">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f8d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7f8d-118">See Also</span></span>  
 [<span data-ttu-id="b7f8d-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b7f8d-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="b7f8d-120">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b7f8d-120">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
