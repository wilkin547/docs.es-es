---
title: Guía de programación (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: d454448771e14b1a540b5a066683bd4c747991ec
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504777"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="784a4-102">Guía de programación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="784a4-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="784a4-103">Esta sección proporciona información conceptual y ejemplos para la programación con LINQ a conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="784a4-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="784a4-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="784a4-104">In This Section</span></span>  
 [<span data-ttu-id="784a4-105">Consultas en LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="784a4-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="784a4-106">Proporciona información sobre cómo escribir LINQ a consultas de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="784a4-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="784a4-107">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="784a4-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="784a4-108">Describe cómo consultar objetos <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="784a4-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="784a4-109">Comparación de objetos DataRow</span><span class="sxs-lookup"><span data-stu-id="784a4-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="784a4-110">Describe cómo utilizar el objeto <xref:System.Data.DataRowComparer> para comparar filas de datos.</span><span class="sxs-lookup"><span data-stu-id="784a4-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="784a4-111">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="784a4-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="784a4-112">Proporciona información sobre cómo crear un <xref:System.Data.DataTable> desde una consulta LINQ to DataSet mediante el uso de la <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> método.</span><span class="sxs-lookup"><span data-stu-id="784a4-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="784a4-113">Cómo: Implementar CopyToDataTable\<T > donde el tipo genérico T no es un objeto DataRow</span><span class="sxs-lookup"><span data-stu-id="784a4-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="784a4-114">Describe cómo implementar un método `CopyToDataTable<T>` personalizado en el que el parámetro genérico T no es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="784a4-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="784a4-115">Métodos genéricos Field y SetField</span><span class="sxs-lookup"><span data-stu-id="784a4-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="784a4-116">Proporciona información acerca de los métodos genéricos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="784a4-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="784a4-117">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="784a4-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="784a4-118">Describe el enlace de datos mediante el objeto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="784a4-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="784a4-119">Depuración de consultas de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="784a4-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="784a4-120">Proporciona información sobre la depuración y solución de problemas de LINQ a consultas de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="784a4-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="784a4-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="784a4-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="784a4-122">Describe problemas de seguridad en LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="784a4-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="784a4-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="784a4-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="784a4-124">Proporciona ejemplos de consultas que utilizan operadores [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="784a4-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="784a4-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="784a4-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="784a4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="784a4-126">See also</span></span>

- [<span data-ttu-id="784a4-127">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="784a4-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="784a4-128">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="784a4-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
