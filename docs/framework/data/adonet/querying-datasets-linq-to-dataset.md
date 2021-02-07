---
description: Más información acerca de cómo consultar conjuntos de valores (LINQ to DataSet)
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 609de99069d39317d8d372cb2a7f43ea301ada2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663461"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="15656-103">Consultar conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="15656-103">Querying DataSets (LINQ to DataSet)</span></span>

<span data-ttu-id="15656-104">Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él.</span><span class="sxs-lookup"><span data-stu-id="15656-104">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="15656-105">La formulación de consultas con LINQ to DataSet es similar a usar Language-Integrated Query (LINQ) en otros orígenes de datos habilitados para LINQ.</span><span class="sxs-lookup"><span data-stu-id="15656-105">Formulating queries with LINQ to DataSet is similar to using Language-Integrated Query (LINQ) against other LINQ-enabled data sources.</span></span> <span data-ttu-id="15656-106">No obstante, recuerde que cuando utiliza consultas LINQ sobre un <xref:System.Data.DataSet> objeto, está consultando una enumeración de <xref:System.Data.DataRow> objetos en lugar de una enumeración de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="15656-106">Remember, however, that when you use LINQ queries over a <xref:System.Data.DataSet> object, you're querying an enumeration of <xref:System.Data.DataRow> objects instead of an enumeration of a custom type.</span></span> <span data-ttu-id="15656-107">Esto significa que puede usar cualquiera de los miembros de la <xref:System.Data.DataRow> clase en las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="15656-107">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your LINQ queries.</span></span> <span data-ttu-id="15656-108">Esto permite crear consultas enriquecidas y complejas.</span><span class="sxs-lookup"><span data-stu-id="15656-108">This lets you create rich, complex queries.</span></span>  
  
 <span data-ttu-id="15656-109">Como con otras implementaciones de LINQ, puede crear LINQ to DataSet consultas de dos formas diferentes: sintaxis de expresiones de consulta y sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="15656-109">As with other implementations of LINQ, you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="15656-110">Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="15656-110">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15656-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="15656-111">In This Section</span></span>  

 [<span data-ttu-id="15656-112">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="15656-112">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="15656-113">Describe cómo realizar consultas en una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="15656-113">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="15656-114">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="15656-114">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="15656-115">Describe cómo realizar consultas entre tablas.</span><span class="sxs-lookup"><span data-stu-id="15656-115">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="15656-116">Consultar objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="15656-116">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="15656-117">Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="15656-117">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15656-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="15656-118">See also</span></span>

- [<span data-ttu-id="15656-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="15656-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="15656-120">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="15656-120">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
