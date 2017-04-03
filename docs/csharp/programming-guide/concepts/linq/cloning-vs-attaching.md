---
title: "Diferencias entre clonación y adjunción (C#) | Microsoft Docs"
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
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 784c3b92ce10878b244ae5d965f5033a6ee6f9ae
ms.lasthandoff: 03/13/2017

---
# <a name="cloning-vs-attaching-c"></a>Diferencias entre clonación y adjunción (C#)
Al agregar objetos <xref:System.Xml.Linq.XNode> (incluido <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute> a un nuevo árbol, si el nuevo contenido no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML. Si el nuevo contenido ya tiene un elemento primario y forma parte de otro árbol XML, se clona el nuevo contenido. Es nuevo contenido clonado se adjunta al árbol XML.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código demuestra qué ocurre si agrega un elemento que tiene elemento primario a un árbol y qué ocurre si agrega un elemento que no tenga elemento primario a un árbol.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Vea también  
 [Crear árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
