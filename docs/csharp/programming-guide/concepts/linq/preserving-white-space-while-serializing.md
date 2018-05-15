---
title: Mantener un espacio en blanco al serializar
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a73c4ec01c1a4d2cebe71ae1afdcce0466762c9c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="e54fd-102">Mantener un espacio en blanco al serializar</span><span class="sxs-lookup"><span data-stu-id="e54fd-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="e54fd-103">En este tema se describe cómo controlar los espacios en blanco a la hora de serializar un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="e54fd-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="e54fd-104">Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin conservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y este se guarda con sangría.</span><span class="sxs-lookup"><span data-stu-id="e54fd-104">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="e54fd-105">Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos.</span><span class="sxs-lookup"><span data-stu-id="e54fd-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="e54fd-106">Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e54fd-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="e54fd-107">Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada.</span><span class="sxs-lookup"><span data-stu-id="e54fd-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="e54fd-108">Es posible que no desee modificar esta sangría de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="e54fd-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="e54fd-109">Para hacerlo en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.</span><span class="sxs-lookup"><span data-stu-id="e54fd-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="e54fd-110">Tratamiento de los espacios en blanco en los métodos que serializan árboles XML</span><span class="sxs-lookup"><span data-stu-id="e54fd-110">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="e54fd-111">Los siguientes métodos de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> serializan un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="e54fd-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="e54fd-112">Es posible serializar un árbol XML en un archivo, un <xref:System.IO.TextReader> o un <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="e54fd-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e54fd-113">El método `ToString` serializa en una cadena.</span><span class="sxs-lookup"><span data-stu-id="e54fd-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e54fd-114">Si el método no recibe un <xref:System.Xml.Linq.SaveOptions> como argumento, entonces el método realizará un formato (sangría) del XML serializado.</span><span class="sxs-lookup"><span data-stu-id="e54fd-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="e54fd-115">En ese caso, se descartarán todos los espacios en blanco del árbol XML que no sean significativos.</span><span class="sxs-lookup"><span data-stu-id="e54fd-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="e54fd-116">Si el método toma <xref:System.Xml.Linq.SaveOptions> como argumento, se puede especificar que el método no dé formato (sangría) al XML serializado.</span><span class="sxs-lookup"><span data-stu-id="e54fd-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="e54fd-117">En ese caso, se preservarán todos los espacios en blanco del árbol XML.</span><span class="sxs-lookup"><span data-stu-id="e54fd-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54fd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e54fd-118">See Also</span></span>  
 [<span data-ttu-id="e54fd-119">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e54fd-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
