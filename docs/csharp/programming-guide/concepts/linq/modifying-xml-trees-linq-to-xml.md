---
title: "Modificar árboles XML (LINQ to XML) (C#)"
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
ms.assetid: 8ec47e6d-2363-4694-be46-8d5ca4d15fc9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cb4ff851dbea97f254d5290ce021d560849e3d9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="modifying-xml-trees-linq-to-xml-c"></a><span data-ttu-id="63b9a-102">Modificar árboles XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-102">Modifying XML Trees (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="63b9a-103"> es el almacén de datos en memoria para un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="63b9a-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="63b9a-104">Una vez haya cargado o analizado un árbol XML a partir de un origen, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permitirá modificarlo en el momento, para luego serializarlo, quizá con el objetivo de guardarlo en un archivo o de enviarlo a un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="63b9a-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="63b9a-105">A la hora de modificar un árbol, puede utilizar ciertos métodos, como por ejemplo, <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="63b9a-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="63b9a-106">No obstante, existe otra aproximación posible, la cual consiste en utilizar una construcción funcional para generar un árbol nuevo que tenga un aspecto diferente.</span><span class="sxs-lookup"><span data-stu-id="63b9a-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="63b9a-107">Dependiendo de los tipos de cambios que necesite hacer en el árbol XML y del tamaño de éste, es posible que esta aproximación resulte más robusta y sencilla de desarrollar.</span><span class="sxs-lookup"><span data-stu-id="63b9a-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="63b9a-108">El primer punto de esta sección compara ambas aproximaciones.</span><span class="sxs-lookup"><span data-stu-id="63b9a-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63b9a-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="63b9a-109">In This Section</span></span>  
  
|<span data-ttu-id="63b9a-110">Tema</span><span class="sxs-lookup"><span data-stu-id="63b9a-110">Topic</span></span>|<span data-ttu-id="63b9a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b9a-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="63b9a-112">Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)|<span data-ttu-id="63b9a-113">Comparación entre modificar un árbol XML en memoria y mediante una construcción funcional</span><span class="sxs-lookup"><span data-stu-id="63b9a-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="63b9a-114">Agregar elementos, atributos y nodos a un árbol XML (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-114">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="63b9a-115">Proporciona información acerca de cómo agregar elementos, atributos o nodos a un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="63b9a-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="63b9a-116">Modificar elementos, atributos y nodos de un árbol XML</span><span class="sxs-lookup"><span data-stu-id="63b9a-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="63b9a-117">Proporciona información acerca de cómo modificar elementos, atributos o nodos ya existentes.</span><span class="sxs-lookup"><span data-stu-id="63b9a-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="63b9a-118">Quitar elementos, atributos y nodos de un árbol XML (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-118">Removing Elements, Attributes, and Nodes from an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="63b9a-119">Proporciona información acerca de cómo eliminar elementos, atributos o nodos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="63b9a-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="63b9a-120">Mantener pares nombre-valor (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-120">Maintaining Name/Value Pairs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="63b9a-121">Describe cómo mantener aquella información de la aplicación que es mejor guardar en forma de pares nombre/valor, como por ejemplo, información sobre configuración o valores globales.</span><span class="sxs-lookup"><span data-stu-id="63b9a-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="63b9a-122">Cómo: Cambiar el espacio de nombres de todo un árbol XML (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-122">How to: Change the Namespace for an Entire XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="63b9a-123">Muestra cómo mover un árbol XML de un espacio de nombres a otro.</span><span class="sxs-lookup"><span data-stu-id="63b9a-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63b9a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="63b9a-124">See Also</span></span>  
 [<span data-ttu-id="63b9a-125">Guía de programación (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63b9a-125">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

