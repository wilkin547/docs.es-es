---
title: Procedimiento Buscar todos los nodos en un Namespace (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b735d7da-5727-48a3-ab57-a16378adc32e
ms.openlocfilehash: c04447df1d4a3e29558a3bad172715d2bdee340b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813853"
---
# <a name="how-to-find-all-nodes-in-a-namespace-visual-basic"></a><span data-ttu-id="14bb2-102">Procedimiento Buscar todos los nodos en un Namespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14bb2-102">How to: Find All Nodes in a Namespace (Visual Basic)</span></span>
<span data-ttu-id="14bb2-103">Puede filtrar en el espacio de nombres de cada elemento o atributo para buscar todos los nodos de ese espacio de nombres particular.</span><span class="sxs-lookup"><span data-stu-id="14bb2-103">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14bb2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14bb2-104">Example</span></span>  
 <span data-ttu-id="14bb2-105">En el ejemplo siguiente se crea un árbol XML con dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="14bb2-105">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="14bb2-106">A continuación, recorre en iteración los árboles y muestra los nombres de todos los elementos y atributos de esos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="14bb2-106">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
    Sub Main()  
        Dim xmlTree As XElement = _  
            <aw:Root>  
                <fc:Child1>abc</fc:Child1>  
                <fc:Child2>def</fc:Child2>  
                <aw:Child3>ghi</aw:Child3>  
                <fc:Child4>  
                    <fc:GrandChild1>jkl</fc:GrandChild1>  
                    <aw:GrandChild2>mno</aw:GrandChild2>  
                </fc:Child4>  
            </aw:Root>  
        Console.WriteLine("Nodes in the http://www.adventure-works.com namespace")  
        Dim awElements As IEnumerable(Of XElement) = _  
            From el In xmlTree.Descendants() _  
            Where (el.Name.Namespace = GetXmlNamespace(aw)) _  
            Select el  
        For Each el As XElement In awElements  
            Console.WriteLine(el.Name.ToString())  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="14bb2-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="14bb2-107">This code produces the following output:</span></span>  
  
```  
Nodes in the http://www.adventure-works.com namespace  
{http://www.adventure-works.com}Child3  
{http://www.adventure-works.com}GrandChild2  
```  
  
## <a name="example"></a><span data-ttu-id="14bb2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14bb2-108">Example</span></span>  
 <span data-ttu-id="14bb2-109">El archivo XML al que tiene acceso la siguiente consulta contiene pedidos de compra en dos espacios de nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="14bb2-109">The XML file accessed by the following query contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="14bb2-110">La consulta crea un nuevo árbol con solo los elementos de uno de los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="14bb2-110">The query creates a new tree with just the elements in one of the namespaces.</span></span>  
  
 <span data-ttu-id="14bb2-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedidos de compra consolidados](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="14bb2-111">This example uses the following XML document: [Sample XML File: Consolidated Purchase Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cpo As XDocument = XDocument.Load("ConsolidatedPurchaseOrders.xml")  
        Dim newTree As XElement = _  
            <Root>  
                <%= From el In cpo.Root.Elements() _  
                    Where el.Name.Namespace = GetXmlNamespace(aw) _  
                    Select el %>  
            </Root>  
        Console.WriteLine(newTree)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="14bb2-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="14bb2-112">This code produces the following output:</span></span>  
  
```xml  
<Root>  
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
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14bb2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="14bb2-113">See also</span></span>

- [<span data-ttu-id="14bb2-114">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14bb2-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
