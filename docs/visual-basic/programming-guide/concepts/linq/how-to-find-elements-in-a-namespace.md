---
title: Procedimiento para buscar elementos de un espacio de nombres (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: c7cb3b77-3424-4b54-9efa-4dc715948e41
ms.openlocfilehash: 3663516e6b6289fe3b1d0599ff3ed4b7dad6a80a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405201"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="c3620-102">Cómo: buscar elementos en un espacio de nombres (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3620-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c3620-103">Las expresiones XPath pueden buscar nodos en un espacio de nombres específico.</span><span class="sxs-lookup"><span data-stu-id="c3620-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="c3620-104">Las expresiones XPath usan prefijos de espacio de nombres para especificar espacios de nombre.</span><span class="sxs-lookup"><span data-stu-id="c3620-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="c3620-105">Para analizar una expresión XPath que contiene prefijos de espacio de nombre, debe pasar un objeto a los métodos XPath que implementan <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="c3620-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="c3620-106">En este ejemplo se usa <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="c3620-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="c3620-107">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="c3620-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="c3620-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3620-108">Example</span></span>  
 <span data-ttu-id="c3620-109">En el ejemplo siguiente se lee un árbol XML que contiene dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c3620-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="c3620-110">Usa un objeto <xref:System.Xml.XmlReader> para leer el documento XML.</span><span class="sxs-lookup"><span data-stu-id="c3620-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="c3620-111">Después obtiene un objeto <xref:System.Xml.XmlNameTable> de <xref:System.Xml.XmlReader> y un objeto <xref:System.Xml.XmlNamespaceManager> de <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="c3620-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="c3620-112">Utiliza <xref:System.Xml.XmlNamespaceManager> al seleccionar elementos.</span><span class="sxs-lookup"><span data-stu-id="c3620-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
```vb  
Dim reader As XmlReader = _  
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")  
Dim root As XElement = XElement.Load(reader)  
Dim nameTable As XmlNameTable = reader.NameTable  
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")  
  
Dim list1 As IEnumerable(Of XElement) = _  
        root.XPathSelectElements("./aw:*", namespaceManager)  
Dim list2 As IEnumerable(Of XElement) = _  
    From el In root.Elements() _  
    Where el.Name.Namespace = "http://www.adventure-works.com" _  
    Select el  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="c3620-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c3620-113">This example produces the following output:</span></span>  
  
```console
Results are identical  
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">  
    <aw:ShippingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:ShippingAddress>  
    <aw:BillingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:BillingAddress>  
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>  
    <aw:Item PartNum="LIT-01">  
      <aw:ProductID>Litware Networking Card</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>20.99</aw:Price>  
    </aw:Item>  
    <aw:Item PartNum="LIT-25">  
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>199.99</aw:Price>  
    </aw:Item>  
  </aw:PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3620-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3620-114">See also</span></span>

- [<span data-ttu-id="c3620-115">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3620-115">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
