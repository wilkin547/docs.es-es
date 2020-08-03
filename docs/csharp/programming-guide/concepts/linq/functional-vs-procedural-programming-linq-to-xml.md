---
title: Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)
description: Para procesar XML, LINQ to XML admite tanto la modificación del árbol XML en memoria basada en procedimientos como una construcción funcional que usa un enfoque declarativo.
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e19f9311c56f4fe2c5e7e5f228aca6c03c6fe04d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103657"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="303c6-103">Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="303c6-103">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="303c6-104">Existen varios tipos de aplicaciones XML:</span><span class="sxs-lookup"><span data-stu-id="303c6-104">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="303c6-105">Algunas aplicaciones toman los documentos XML de origen y crean nuevos documentos XML que tienen una forma diferente que los documentos de origen.</span><span class="sxs-lookup"><span data-stu-id="303c6-105">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="303c6-106">Algunas aplicaciones toman documentos XML de origen y crean documentos de resultado de una forma totalmente diferente, como archivos HTML o de texto CSV.</span><span class="sxs-lookup"><span data-stu-id="303c6-106">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="303c6-107">Algunas aplicaciones toman documentos XML de origen e insertan registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="303c6-107">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="303c6-108">Algunas aplicaciones toman datos de otro origen de datos, como una base de datos y crean documentos XML a partir de él.</span><span class="sxs-lookup"><span data-stu-id="303c6-108">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="303c6-109">Estos no son todos los tipos de aplicaciones XML, pero son un conjunto representativo de los tipos de funcionalidad que un programador XML debe implementar.</span><span class="sxs-lookup"><span data-stu-id="303c6-109">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="303c6-110">Con todos esos tipos de aplicaciones un desarrollador puede tomar dos enfoques opuestos:</span><span class="sxs-lookup"><span data-stu-id="303c6-110">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="303c6-111">Construcción funcional usando un enfoque declarativo.</span><span class="sxs-lookup"><span data-stu-id="303c6-111">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="303c6-112">Modificación del árbol XML en memoria usando código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="303c6-112">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="303c6-113">LINQ to XML admite ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="303c6-113">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="303c6-114">Cuando se utiliza el enfoque funcional, se escriben transformaciones que toman los documentos de origen y generan documentos de resultados completamente nuevos con la forma que se desee.</span><span class="sxs-lookup"><span data-stu-id="303c6-114">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="303c6-115">Cuando se modifica un árbol XML, se escribe código que atraviese los nodos de un árbol XML y navegue por ellos en memoria para insertar, eliminar y modificar nodos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="303c6-115">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="303c6-116">Puede usar LINQ to XML con cualquier enfoque.</span><span class="sxs-lookup"><span data-stu-id="303c6-116">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="303c6-117">Se usan las mismas clases y, en algunos casos, los mismos métodos.</span><span class="sxs-lookup"><span data-stu-id="303c6-117">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="303c6-118">No obstante, la estructura y los objetivos de los dos enfoques son muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="303c6-118">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="303c6-119">Por ejemplo, en situaciones diferentes, uno u otro enfoque tendrá a menudo un rendimiento mejor y usará más o menos memoria.</span><span class="sxs-lookup"><span data-stu-id="303c6-119">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="303c6-120">Asimismo, uno u otro enfoque será más fácil de escribir y proporcionará código más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="303c6-120">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="303c6-121">Para obtener una comparación de los dos enfoques, vea [Diferencias entre la modificación del árbol XML en memoria y la construcción funcional (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="303c6-121">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="303c6-122">Para obtener un tutorial sobre la escritura de transformaciones funcionales, vea [Pure Functional Transformations of XML (C#) (Transformaciones funcionales puras de XML (C#))](./introduction-to-pure-functional-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="303c6-122">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](./introduction-to-pure-functional-transformations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303c6-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="303c6-123">See also</span></span>

- [<span data-ttu-id="303c6-124">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="303c6-124">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
