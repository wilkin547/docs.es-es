---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783051"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="52add-102">Consultar conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="52add-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="52add-103">Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él.</span><span class="sxs-lookup"><span data-stu-id="52add-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="52add-104">La formulación de consultas con LINQ to DataSet es similar a [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] usar en [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]otros orígenes de datos habilitados para.</span><span class="sxs-lookup"><span data-stu-id="52add-104">Formulating queries with LINQ to DataSet is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="52add-105">No obstante, recuerde que cuando utiliza [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas en un <xref:System.Data.DataSet> objeto, está consultando una enumeración de <xref:System.Data.DataRow> objetos, en lugar de una enumeración de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="52add-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="52add-106">Esto significa que puede usar cualquiera de los miembros de la <xref:System.Data.DataRow> clase [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en las consultas.</span><span class="sxs-lookup"><span data-stu-id="52add-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="52add-107">Esto permite crear consultas amplias y complejas.</span><span class="sxs-lookup"><span data-stu-id="52add-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="52add-108">Al igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear LINQ to DataSet consultas de dos formas diferentes: sintaxis de expresiones de consulta y sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="52add-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="52add-109">Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="52add-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52add-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52add-110">In This Section</span></span>  
 [<span data-ttu-id="52add-111">Consultas de tabla única</span><span class="sxs-lookup"><span data-stu-id="52add-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="52add-112">Describe cómo realizar consultas en una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="52add-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="52add-113">Consultas entre tablas</span><span class="sxs-lookup"><span data-stu-id="52add-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="52add-114">Describe cómo realizar consultas entre tablas.</span><span class="sxs-lookup"><span data-stu-id="52add-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="52add-115">Consultar objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="52add-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="52add-116">Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.</span><span class="sxs-lookup"><span data-stu-id="52add-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52add-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="52add-117">See also</span></span>

- [<span data-ttu-id="52add-118">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="52add-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="52add-119">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="52add-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
