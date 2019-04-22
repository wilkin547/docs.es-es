---
title: Procedimiento Cambiar el Namespace para todo un árbol XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 1837324b-5cb5-4fa8-95b9-3071efa0f913
ms.openlocfilehash: 5a5926583990e3abda49ceaee4786a2158275a3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825006"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-visual-basic"></a><span data-ttu-id="56f7a-102">Procedimiento Cambiar el Namespace para todo un árbol XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56f7a-102">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>
<span data-ttu-id="56f7a-103">En ocasiones, tendrá que cambiar, mediante programación, el espacio de nombres de un elemento o de un atributo.</span><span class="sxs-lookup"><span data-stu-id="56f7a-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="56f7a-104">Esto resulta sencillo con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="56f7a-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="56f7a-105">Es posible modificar la propiedad <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56f7a-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="56f7a-106">No es posible modificar la propiedad <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>, pero es posible copiar con facilidad los atributos en un <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, eliminar los atributos existentes y, a continuación, agregar los atributos nuevos que se encuentran en el espacio de nombres deseado.</span><span class="sxs-lookup"><span data-stu-id="56f7a-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="56f7a-107">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="56f7a-107">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f7a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56f7a-108">Example</span></span>  
 <span data-ttu-id="56f7a-109">En el código siguiente se crean dos árboles XML que no están en ningún espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="56f7a-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="56f7a-110">A continuación, se cambia el espacio de nombres de cada árbol y se combinan ambos árboles en uno sólo.</span><span class="sxs-lookup"><span data-stu-id="56f7a-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```vb  
Dim tree1 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim tree2 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim ad As XNamespace = "http://www.adatum.com"  
' change the namespace of every element and attribute in the first tree  
For Each el As XElement In tree1.DescendantsAndSelf  
    el.Name = aw.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' change the namespace of every element and attribute in the second tree  
For Each el As XElement In tree2.DescendantsAndSelf()  
    el.Name = ad.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' add attribute namespaces so that the tree will be serialized with  
' the aw and ad namespace prefixes  
tree1.Add( _  
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _  
)  
tree2.Add( _  
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _  
)  
' create a new composite tree  
Dim root As XElement = _  
    <Root>  
        <%= tree1 %>  
        <%= tree2 %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="56f7a-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="56f7a-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56f7a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f7a-112">See also</span></span>

- [<span data-ttu-id="56f7a-113">Modificar árboles XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56f7a-113">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
