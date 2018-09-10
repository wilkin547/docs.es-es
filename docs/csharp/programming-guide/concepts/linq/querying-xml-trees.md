---
title: Consultar árboles XML (C#)
ms.date: 07/20/2015
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
ms.openlocfilehash: 349235689dba125f697d0df5ff90bd10a69432c5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501056"
---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="36ab6-102">Consultar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="36ab6-103">En esta sección se ofrecen ejemplos de consultas de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ab6-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="36ab6-104">Para obtener más información sobre cómo escribir consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], vea [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) (Introducción a LINQ en C#).</span><span class="sxs-lookup"><span data-stu-id="36ab6-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="36ab6-105">Una vez que haya creado una instancia del árbol XML, escribir consultas será la manera más eficaz de extraer datos de dicho árbol.</span><span class="sxs-lookup"><span data-stu-id="36ab6-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="36ab6-106">Asimismo, la consulta, combinada con la construcción funcional, permite generar un documento XML nuevo que tiene una forma diferente del documento original.</span><span class="sxs-lookup"><span data-stu-id="36ab6-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36ab6-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36ab6-107">In This Section</span></span>  
  
|<span data-ttu-id="36ab6-108">Tema</span><span class="sxs-lookup"><span data-stu-id="36ab6-108">Topic</span></span>|<span data-ttu-id="36ab6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="36ab6-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36ab6-110">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="36ab6-111">Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.</span><span class="sxs-lookup"><span data-stu-id="36ab6-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="36ab6-112">Proyecciones y transformaciones (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="36ab6-113">Proporciona ejemplos comunes acerca de la proyección desde árboles XML y la transformación de éstos.</span><span class="sxs-lookup"><span data-stu-id="36ab6-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="36ab6-114">Técnicas de consulta avanzadas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="36ab6-115">Proporciona técnicas de consulta que resultan útiles en escenarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="36ab6-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="36ab6-116">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="36ab6-117">Presenta varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ab6-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|<span data-ttu-id="36ab6-118">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) (Transformaciones funcionales puras de XML [C#])</span><span class="sxs-lookup"><span data-stu-id="36ab6-118">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)</span></span>|<span data-ttu-id="36ab6-119">Presenta un pequeño tutorial acerca de cómo escribir consultas en el estilo de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="36ab6-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36ab6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="36ab6-120">See Also</span></span>

- [<span data-ttu-id="36ab6-121">Guía de programación (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="36ab6-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  
- [<span data-ttu-id="36ab6-122">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="36ab6-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
