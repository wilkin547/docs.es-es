---
title: Guía de programación (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 6f6ab1634769a54bd8dbafe8c9d41b11ff787d50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638017"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="32464-102">Guía de programación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="32464-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="32464-103">En esta sección se ofrece información conceptual y ejemplos de programación con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32464-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32464-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32464-104">In This Section</span></span>  
 [<span data-ttu-id="32464-105">Consultas en LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="32464-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="32464-106">Proporciona información acerca del modo de escribir consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32464-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="32464-107">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="32464-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="32464-108">Describe cómo consultar objetos <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="32464-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="32464-109">Comparación de objetos DataRow</span><span class="sxs-lookup"><span data-stu-id="32464-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="32464-110">Describe cómo utilizar el objeto <xref:System.Data.DataRowComparer> para comparar filas de datos.</span><span class="sxs-lookup"><span data-stu-id="32464-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="32464-111">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="32464-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="32464-112">Proporciona información sobre cómo crear un <xref:System.Data.DataTable> desde un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta utilizando el <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32464-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="32464-113">Cómo: Implementar CopyToDataTable\<T > donde el tipo genérico T no es un objeto DataRow</span><span class="sxs-lookup"><span data-stu-id="32464-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="32464-114">Describe cómo implementar un método `CopyToDataTable<T>` personalizado en el que el parámetro genérico T no es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="32464-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="32464-115">Métodos genéricos Field y SetField</span><span class="sxs-lookup"><span data-stu-id="32464-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="32464-116">Proporciona información acerca de los métodos genéricos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="32464-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="32464-117">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="32464-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="32464-118">Describe el enlace de datos mediante el objeto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="32464-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="32464-119">Depuración de consultas de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="32464-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="32464-120">Proporciona información sobre la depuración y solución de problemas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consultas.</span><span class="sxs-lookup"><span data-stu-id="32464-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="32464-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="32464-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="32464-122">Describe problemas de seguridad en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32464-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="32464-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="32464-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="32464-124">Proporciona ejemplos de consultas que utilizan operadores [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32464-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="32464-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="32464-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="32464-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="32464-126">See also</span></span>

- [<span data-ttu-id="32464-127">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32464-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="32464-128">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="32464-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
