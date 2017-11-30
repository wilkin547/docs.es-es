---
title: "Consultar árboles XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1516cdc58effaa3e738210b948b43d7ed170890a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="3bfc3-102">Consultar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="3bfc3-103">En esta sección se ofrecen ejemplos de consultas de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bfc3-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="3bfc3-104">Para obtener más información acerca de la escritura [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de las consultas, vea [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="3bfc3-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="3bfc3-105">Una vez que haya creado una instancia del árbol XML, escribir consultas será la manera más eficaz de extraer datos de dicho árbol.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="3bfc3-106">Asimismo, la consulta, combinada con la construcción funcional, permite generar un documento XML nuevo que tiene una forma diferente del documento original.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bfc3-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3bfc3-107">In This Section</span></span>  
  
|<span data-ttu-id="3bfc3-108">Tema</span><span class="sxs-lookup"><span data-stu-id="3bfc3-108">Topic</span></span>|<span data-ttu-id="3bfc3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bfc3-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3bfc3-110">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="3bfc3-111">Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="3bfc3-112">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="3bfc3-113">Proporciona ejemplos comunes acerca de la proyección desde árboles XML y la transformación de éstos.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="3bfc3-114">Técnicas avanzadas de consulta (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="3bfc3-115">Proporciona técnicas de consulta que resultan útiles en escenarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="3bfc3-116">LINQ to XML para usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="3bfc3-117">Presenta varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bfc3-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="3bfc3-118">Transformaciones funcionales puras de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="3bfc3-119">Presenta un pequeño tutorial acerca de cómo escribir consultas en el estilo de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="3bfc3-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bfc3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bfc3-120">See Also</span></span>  
 [<span data-ttu-id="3bfc3-121">Guía de programación (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bfc3-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  
 [<span data-ttu-id="3bfc3-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bfc3-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
