---
title: "Consultar árboles XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4bad11434ed2610492854d5ec4a7a84bceb189f3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="8e65d-102">Consultar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="8e65d-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="8e65d-103">En esta sección se ofrecen ejemplos de consultas de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e65d-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="8e65d-104">Para obtener más información sobre cómo escribir consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], vea [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) (Introducción a LINQ en C#).</span><span class="sxs-lookup"><span data-stu-id="8e65d-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="8e65d-105">Una vez que haya creado una instancia del árbol XML, escribir consultas será la manera más eficaz de extraer datos de dicho árbol.</span><span class="sxs-lookup"><span data-stu-id="8e65d-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="8e65d-106">Asimismo, la consulta, combinada con la construcción funcional, permite generar un documento XML nuevo que tiene una forma diferente del documento original.</span><span class="sxs-lookup"><span data-stu-id="8e65d-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e65d-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8e65d-107">In This Section</span></span>  
  
|<span data-ttu-id="8e65d-108">Tema</span><span class="sxs-lookup"><span data-stu-id="8e65d-108">Topic</span></span>|<span data-ttu-id="8e65d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e65d-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8e65d-110">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8e65d-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="8e65d-111">Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.</span><span class="sxs-lookup"><span data-stu-id="8e65d-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="8e65d-112">Proyecciones y transformaciones (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8e65d-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="8e65d-113">Proporciona ejemplos comunes acerca de la proyección desde árboles XML y la transformación de éstos.</span><span class="sxs-lookup"><span data-stu-id="8e65d-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="8e65d-114">Técnicas de consulta avanzadas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8e65d-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="8e65d-115">Proporciona técnicas de consulta que resultan útiles en escenarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="8e65d-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="8e65d-116">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="8e65d-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="8e65d-117">Presenta varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e65d-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|<span data-ttu-id="8e65d-118">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) (Transformaciones funcionales puras de XML [C#])</span><span class="sxs-lookup"><span data-stu-id="8e65d-118">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)</span></span>|<span data-ttu-id="8e65d-119">Presenta un pequeño tutorial acerca de cómo escribir consultas en el estilo de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="8e65d-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e65d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e65d-120">See Also</span></span>  
 <span data-ttu-id="8e65d-121">[Programming Guide (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  (Guía de programación (LINQ to XML) [C#])</span><span class="sxs-lookup"><span data-stu-id="8e65d-121">[Programming Guide (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="8e65d-122">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="8e65d-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

