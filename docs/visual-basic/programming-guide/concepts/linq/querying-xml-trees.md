---
title: Consultar árboles XML
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 643b19a0cfcd2a81c6f685de65979f83ca32d918
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636905"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="78aba-102">Consultar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="78aba-103">En esta sección se ofrecen ejemplos de consultas de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78aba-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="78aba-104">Para obtener más información sobre cómo escribir consultas LINQ, vea [Introducción con LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="78aba-104">For more information about writing LINQ queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="78aba-105">Una vez que haya creado una instancia del árbol XML, escribir consultas será la manera más eficaz de extraer datos de dicho árbol.</span><span class="sxs-lookup"><span data-stu-id="78aba-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="78aba-106">Asimismo, la consulta, combinada con la construcción funcional, permite generar un documento XML nuevo que tiene una forma diferente del documento original.</span><span class="sxs-lookup"><span data-stu-id="78aba-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78aba-107">Esta sección</span><span class="sxs-lookup"><span data-stu-id="78aba-107">In This Section</span></span>  
  
|<span data-ttu-id="78aba-108">Tema</span><span class="sxs-lookup"><span data-stu-id="78aba-108">Topic</span></span>|<span data-ttu-id="78aba-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="78aba-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="78aba-110">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="78aba-111">Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.</span><span class="sxs-lookup"><span data-stu-id="78aba-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="78aba-112">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="78aba-113">Proporciona ejemplos comunes acerca de la proyección desde árboles XML y la transformación de éstos.</span><span class="sxs-lookup"><span data-stu-id="78aba-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="78aba-114">Técnicas de consulta avanzadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="78aba-115">Proporciona técnicas de consulta que resultan útiles en escenarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="78aba-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="78aba-116">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="78aba-117">Presenta varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78aba-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="78aba-118">Transformaciones funcionales puras de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="78aba-119">Presenta un pequeño tutorial acerca de cómo escribir consultas en el estilo de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="78aba-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78aba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="78aba-120">See also</span></span>

- [<span data-ttu-id="78aba-121">Guía de programación (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78aba-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
- [<span data-ttu-id="78aba-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78aba-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
