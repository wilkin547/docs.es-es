---
title: Consultar árboles XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 0d3855a562ce5ec43b28fba21b2ab4db0583a2d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839631"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="4848a-102">Consultar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="4848a-103">En esta sección se ofrecen ejemplos de consultas de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4848a-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="4848a-104">Para obtener más información acerca de cómo escribir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consultas, vea [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="4848a-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="4848a-105">Una vez que haya creado una instancia del árbol XML, escribir consultas será la manera más eficaz de extraer datos de dicho árbol.</span><span class="sxs-lookup"><span data-stu-id="4848a-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="4848a-106">Asimismo, la consulta, combinada con la construcción funcional, permite generar un documento XML nuevo que tiene una forma diferente del documento original.</span><span class="sxs-lookup"><span data-stu-id="4848a-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4848a-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4848a-107">In This Section</span></span>  
  
|<span data-ttu-id="4848a-108">Tema</span><span class="sxs-lookup"><span data-stu-id="4848a-108">Topic</span></span>|<span data-ttu-id="4848a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4848a-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4848a-110">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="4848a-111">Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.</span><span class="sxs-lookup"><span data-stu-id="4848a-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="4848a-112">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="4848a-113">Proporciona ejemplos comunes acerca de la proyección desde árboles XML y la transformación de éstos.</span><span class="sxs-lookup"><span data-stu-id="4848a-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="4848a-114">Consulta técnicas avanzadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="4848a-115">Proporciona técnicas de consulta que resultan útiles en escenarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="4848a-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="4848a-116">LINQ to XML para usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="4848a-117">Presenta varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4848a-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="4848a-118">Transformaciones funcionales puras de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="4848a-119">Presenta un pequeño tutorial acerca de cómo escribir consultas en el estilo de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="4848a-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4848a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4848a-120">See also</span></span>

- [<span data-ttu-id="4848a-121">Guía de programación (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4848a-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
- [<span data-ttu-id="4848a-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4848a-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
