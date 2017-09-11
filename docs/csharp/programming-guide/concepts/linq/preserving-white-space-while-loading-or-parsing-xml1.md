---
title: Mantener un espacio en blanco al cargar o analizar XML
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
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dce6d2afc6c146c346dadeb9d7e4af6fcca1b987
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="1e9c9-102">Mantener un espacio en blanco al cargar o analizar XML</span><span class="sxs-lookup"><span data-stu-id="1e9c9-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="1e9c9-103">En este tema se describe cómo controlar el comportamiento de los espacios en blanco de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e9c9-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="1e9c9-104">Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="1e9c9-105">Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="1e9c9-106">Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e9c9-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="1e9c9-107">Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="1e9c9-108">Es posible que no desee modificar esta sangría de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="1e9c9-109">Para hacerlo en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="1e9c9-110">En este tema se describe el comportamiento de espacios en blanco de métodos que rellenan los árboles XML.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="1e9c9-111">Para obtener información sobre cómo controlar los espacios en blanco al serializar árboles XML, consulte [Mantener un espacio en blanco al serializar](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="1e9c9-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="1e9c9-112">Comportamiento de métodos que rellenan árboles XML</span><span class="sxs-lookup"><span data-stu-id="1e9c9-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="1e9c9-113">Los siguientes métodos de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> rellenan un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="1e9c9-114">Puede rellenar un árbol XML desde un archivo, un <xref:System.IO.TextReader>, un <xref:System.Xml.XmlReader> o una cadena:</span><span class="sxs-lookup"><span data-stu-id="1e9c9-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 <span data-ttu-id="1e9c9-115">Si el método no toma <xref:System.Xml.Linq.LoadOptions> como argumento, el método no conservará espacios en blanco no significativos.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-115">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="1e9c9-116">En la mayoría de casos, si el método toma <xref:System.Xml.Linq.LoadOptions> como argumento, opcionalmente se pueden conservar los espacios en blanco no significativos como nodos de texto en el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-116">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="1e9c9-117">No obstante, si el método carga XML desde <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> determina si los espacios en blanco se conservan.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-117">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="1e9c9-118">Establecer <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> no tendrá ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-118">Setting <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> will have no effect.</span></span>  
  
 <span data-ttu-id="1e9c9-119">Con estos métodos, si se conservan los espacios en blanco, se inserta un espacio en blanco insignificante en el árbol XML como nodos <xref:System.Xml.Linq.XText>.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-119">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="1e9c9-120">Si no se conservan los espacios en blanco, entonces no se insertan los nodos de texto.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-120">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="1e9c9-121">Puede crear un árbol XML mediante <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-121">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="1e9c9-122">Los nodos escritos en <xref:System.Xml.XmlWriter> se rellenan en el árbol.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-122">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="1e9c9-123">No obstante, al crear un árbol XML usando este método se conservan todos los nodos, independientemente de si el nodo es o no un espacio en blanco, o si el espacio en blanco es o no significativo.</span><span class="sxs-lookup"><span data-stu-id="1e9c9-123">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9c9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e9c9-124">See Also</span></span>  
 [<span data-ttu-id="1e9c9-125">Analizar XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1e9c9-125">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

