---
title: "Guía de programación (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 298ff0c6bfc5bc251483de8e90e3a394a2337369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="49cde-102">Guía de programación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="49cde-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="49cde-103">En esta sección se ofrece información conceptual y ejemplos de programación con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49cde-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49cde-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="49cde-104">In This Section</span></span>  
 [<span data-ttu-id="49cde-105">Consultas en LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="49cde-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="49cde-106">Proporciona información acerca del modo de escribir consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49cde-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="49cde-107">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="49cde-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="49cde-108">Describe cómo consultar objetos <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="49cde-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="49cde-109">Comparación de objetos DataRow</span><span class="sxs-lookup"><span data-stu-id="49cde-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="49cde-110">Describe cómo utilizar el objeto <xref:System.Data.DataRowComparer> para comparar filas de datos.</span><span class="sxs-lookup"><span data-stu-id="49cde-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="49cde-111">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="49cde-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="49cde-112">Proporciona información acerca de cómo crear un <xref:System.Data.DataTable> desde una [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta mediante el uso de la <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> método.</span><span class="sxs-lookup"><span data-stu-id="49cde-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="49cde-113">Cómo: implementar CopyToDataTable\<T > donde el tipo genérico T no es un objeto DataRow</span><span class="sxs-lookup"><span data-stu-id="49cde-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="49cde-114">Describe cómo implementar un método `CopyToDataTable<T>` personalizado en el que el parámetro genérico T no es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="49cde-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="49cde-115">Métodos genéricos Field y SetField</span><span class="sxs-lookup"><span data-stu-id="49cde-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="49cde-116">Proporciona información acerca de los métodos genéricos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="49cde-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="49cde-117">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="49cde-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="49cde-118">Describe el enlace de datos mediante el objeto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="49cde-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="49cde-119">Depuración de consultas de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="49cde-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="49cde-120">Proporciona información sobre la depuración y solución de problemas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consultas.</span><span class="sxs-lookup"><span data-stu-id="49cde-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="49cde-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="49cde-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="49cde-122">Describe problemas de seguridad en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49cde-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="49cde-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="49cde-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="49cde-124">Proporciona ejemplos de consultas que utilizan operadores [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49cde-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="49cde-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="49cde-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="49cde-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="49cde-126">See Also</span></span>  
 [<span data-ttu-id="49cde-127">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="49cde-127">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [<span data-ttu-id="49cde-128">NO está en la compilación: Guía de programación de General de LINQ</span><span class="sxs-lookup"><span data-stu-id="49cde-128">NOT IN BUILD: LINQ General Programming Guide</span></span>](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049)  
 [<span data-ttu-id="49cde-129">Marco de trabajo LINQ</span><span class="sxs-lookup"><span data-stu-id="49cde-129">LINQ Framework</span></span>](http://msdn.microsoft.com/en-us/897ea0fc-40db-4694-bbe5-7dd339d5bf94)
