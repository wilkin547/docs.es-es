---
title: 'Cómo: Cambiar el espacio de nombres de todo un árbol XML (C#)'
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: cbb7c3d332eea83d6df71812cc18633df6fbb6d0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676686"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a>Cómo: Cambiar el espacio de nombres de todo un árbol XML (C#)
En ocasiones, tendrá que cambiar, mediante programación, el espacio de nombres de un elemento o de un atributo. Esto resulta sencillo con LINQ to XML. Es posible modificar la propiedad <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>. No es posible modificar la propiedad <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>, pero es posible copiar con facilidad los atributos en un <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, eliminar los atributos existentes y, a continuación, agregar los atributos nuevos que se encuentran en el espacio de nombres deseado.  
  
 Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se crean dos árboles XML que no están en ningún espacio de nombres. A continuación, se cambia el espacio de nombres de cada árbol y se combinan ambos árboles en uno sólo.  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también

- [Modificar árboles XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
