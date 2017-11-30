---
title: "Diferencias entre clonación y adjunción (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e58e9538c319c20f9e820ff1de1fb6f973a18bdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cloning-vs-attaching-c"></a><span data-ttu-id="c1b07-102">Diferencias entre clonación y adjunción (C#)</span><span class="sxs-lookup"><span data-stu-id="c1b07-102">Cloning vs. Attaching (C#)</span></span>
<span data-ttu-id="c1b07-103">Cuando se asocian objetos <xref:System.Xml.Linq.XNode> (incluyendo el objeto <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute> a un árbol nuevo, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML.</span><span class="sxs-lookup"><span data-stu-id="c1b07-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="c1b07-104">Si el nuevo contenido ya tiene un elemento primario y forma parte de otro árbol XML, se clona el nuevo contenido.</span><span class="sxs-lookup"><span data-stu-id="c1b07-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="c1b07-105">Es nuevo contenido clonado se adjunta al árbol XML.</span><span class="sxs-lookup"><span data-stu-id="c1b07-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1b07-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1b07-106">Example</span></span>  
 <span data-ttu-id="c1b07-107">El siguiente código demuestra qué ocurre si agrega un elemento que tiene elemento primario a un árbol y qué ocurre si agrega un elemento que no tenga elemento primario a un árbol.</span><span class="sxs-lookup"><span data-stu-id="c1b07-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="c1b07-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c1b07-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1b07-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1b07-109">See Also</span></span>  
 <span data-ttu-id="c1b07-110">[Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md) (Crear árboles XML (C#))</span><span class="sxs-lookup"><span data-stu-id="c1b07-110">[Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
