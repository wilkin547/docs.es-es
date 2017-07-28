---
title: "Buscar un único descendiente utilizando el método Descendants (C#)"
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
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 89e20ede65caf65e91a37cbee69c80146a1443f0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a>Buscar un único descendiente utilizando el método Descendants (C#)
Puede utilizar el método de eje <xref:System.Xml.Linq.XContainer.Descendants%2A> para escribir rápidamente código para buscar un solo elemento cuyo nombre es único. Esta técnica es especialmente útil si desea buscar un descendiente particular con un nombre específico. Puede escribir el código para desplazarse al elemento deseado, pero a menudo resulta más rápido escribir el código usando el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo utiliza el operador de consulta estándar <xref:System.Linq.Enumerable.First%2A>.  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Este código genera el siguiente resultado:  
  
```  
GC3 Value  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Este código genera el siguiente resultado:  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a>Vea también  
 [Consultas básicas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

