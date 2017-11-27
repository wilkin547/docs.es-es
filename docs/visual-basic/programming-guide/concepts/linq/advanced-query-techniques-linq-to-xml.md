---
title: "Técnicas avanzadas de consulta (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79be877c-fadc-4dfb-9f03-426082b13656
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21a12ba1929b0e8fd24ae9e12404691222e397cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-query-techniques-linq-to-xml-visual-basic"></a><span data-ttu-id="bc3b9-102">Técnicas avanzadas de consulta (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-102">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="bc3b9-103">En esta sección se proporcionan ejemplos de técnicas de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc3b9-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bc3b9-104">In This Section</span></span>  
  
|<span data-ttu-id="bc3b9-105">Tema</span><span class="sxs-lookup"><span data-stu-id="bc3b9-105">Topic</span></span>|<span data-ttu-id="bc3b9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc3b9-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bc3b9-107">Cómo: combinar dos colecciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-107">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="bc3b9-108">Muestra cómo utilizar la cláusula `Join` para aprovechar las relaciones de los datos XML.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="bc3b9-109">Cómo: crear la jerarquía con la agrupación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-109">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="bc3b9-110">Muestra cómo agrupar datos y después generar XML basado en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="bc3b9-111">Cómo: consultar LINQ to XML utilizando XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-111">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="bc3b9-112">Muestra cómo recuperar las recopilaciones basadas en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="bc3b9-113">Cómo: escribir un LINQ en método de eje XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-113">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="bc3b9-114">Muestra cómo escribir un método de eje de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc3b9-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="bc3b9-115">Cómo: mostrar todos los nodos en un árbol (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-115">How to: List All Nodes in a Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="bc3b9-116">Presenta un método de utilidad que enumera todos los nodos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-116">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="bc3b9-117">Esto es útil para el código de depuración que modifica un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-117">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="bc3b9-118">Cómo: recuperar párrafos de un documento XML abierto de Office (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-118">How to: Retrieve Paragraphs from an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="bc3b9-119">Presenta código que abre un documento XML abierto de Office, recupera el párrafo en una colección de objetos XElement, el texto y el estilo de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-119">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="bc3b9-120">Cómo: modificar un documento XML abierto de Office (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-120">How to: Modify an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="bc3b9-121">Presenta código que abre, modifica y guarda un documento XML abierto de Office.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-121">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="bc3b9-122">Cómo: rellenar un árbol XML desde el sistema de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-122">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="bc3b9-123">Presenta código que crea un árbol XML a partir del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="bc3b9-123">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc3b9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc3b9-124">See Also</span></span>  
 [<span data-ttu-id="bc3b9-125">Consultar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc3b9-125">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
