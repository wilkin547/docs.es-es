---
title: Guía de programación (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 720d9a90583a0dcf3453689a362f6043157a326c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161564"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="5be5f-102">Guía de programación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="5be5f-102">Programming Guide (LINQ to DataSet)</span></span>

<span data-ttu-id="5be5f-103">En esta sección se proporciona información conceptual y ejemplos para programar con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="5be5f-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5be5f-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5be5f-104">In This Section</span></span>  

 [<span data-ttu-id="5be5f-105">Consultas en LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5be5f-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-106">Proporciona información sobre cómo escribir consultas de LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="5be5f-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="5be5f-107">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="5be5f-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-108">Describe cómo consultar objetos <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="5be5f-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="5be5f-109">Comparación de objetos DataRow</span><span class="sxs-lookup"><span data-stu-id="5be5f-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-110">Describe cómo utilizar el objeto <xref:System.Data.DataRowComparer> para comparar filas de datos.</span><span class="sxs-lookup"><span data-stu-id="5be5f-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="5be5f-111">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="5be5f-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-112">Proporciona información sobre la creación <xref:System.Data.DataTable> de un a partir de una consulta de LINQ to DataSet mediante el <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5be5f-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="5be5f-113">Cómo: implementar CopyToDataTable \<T> donde el tipo genérico T no es DataRow</span><span class="sxs-lookup"><span data-stu-id="5be5f-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="5be5f-114">Describe cómo implementar un método `CopyToDataTable<T>` personalizado en el que el parámetro genérico T no es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="5be5f-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="5be5f-115">Métodos genéricos Field y SetField</span><span class="sxs-lookup"><span data-stu-id="5be5f-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-116">Proporciona información acerca de los métodos genéricos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="5be5f-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="5be5f-117">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5be5f-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-118">Describe el enlace de datos mediante el objeto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="5be5f-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="5be5f-119">Depurar consultas de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5be5f-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="5be5f-120">Proporciona información sobre la depuración y solución de problemas de consultas LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="5be5f-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="5be5f-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5be5f-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="5be5f-122">Describe problemas de seguridad en LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="5be5f-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="5be5f-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5be5f-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="5be5f-124">Proporciona ejemplos de consultas que utilizan los operadores de LINQ.</span><span class="sxs-lookup"><span data-stu-id="5be5f-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5be5f-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="5be5f-125">Reference</span></span>  

 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="5be5f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5be5f-126">See also</span></span>

- [<span data-ttu-id="5be5f-127">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5be5f-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="5be5f-128">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5be5f-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
