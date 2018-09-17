---
title: 'Cómo: Buscar todos los nodos de un espacio de nombres (C#)'
ms.date: 07/20/2015
ms.assetid: 3a38b913-a53e-4d0e-a19d-8782bffd3364
ms.openlocfilehash: 0675795da7c190e6d105ac61027c28f161961099
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45613961"
---
# <a name="how-to-find-all-nodes-in-a-namespace-c"></a><span data-ttu-id="287a6-102">Cómo: Buscar todos los nodos de un espacio de nombres (C#)</span><span class="sxs-lookup"><span data-stu-id="287a6-102">How to: Find All Nodes in a Namespace (C#)</span></span>
<span data-ttu-id="287a6-103">Puede filtrar en el espacio de nombres de cada elemento o atributo para buscar todos los nodos de ese espacio de nombres particular.</span><span class="sxs-lookup"><span data-stu-id="287a6-103">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="287a6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="287a6-104">Example</span></span>  
 <span data-ttu-id="287a6-105">En el ejemplo siguiente se crea un árbol XML con dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="287a6-105">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="287a6-106">A continuación, recorre en iteración los árboles y muestra los nombres de todos los elementos y atributos de esos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="287a6-106">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>  
  
```csharp  
string markup = @"<aw:Root xmlns:aw='http://www.adventure-works.com' xmlns:fc='www.fourthcoffee.com'>  
  <fc:Child1>abc</fc:Child1>  
  <fc:Child2>def</fc:Child2>  
  <aw:Child3>ghi</aw:Child3>  
  <fc:Child4>  
    <fc:GrandChild1>jkl</fc:GrandChild1>  
    <aw:GrandChild2>mno</aw:GrandChild2>  
  </fc:Child4>  
</aw:Root>";  
XElement xmlTree = XElement.Parse(markup);  
Console.WriteLine("Nodes in the http://www.adventure-works.com namespace");  
IEnumerable<XElement> awElements =  
    from el in xmlTree.Descendants()  
    where el.Name.Namespace == "http://www.adventure-works.com"  
    select el;  
foreach (XElement el in awElements)  
    Console.WriteLine(el.Name.ToString());  
```  
  
 <span data-ttu-id="287a6-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="287a6-107">This code produces the following output:</span></span>  
  
```  
Nodes in the http://www.adventure-works.com namespace  
{http://www.adventure-works.com}Child3  
{http://www.adventure-works.com}GrandChild2  
```  
  
## <a name="example"></a><span data-ttu-id="287a6-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="287a6-108">Example</span></span>  
 <span data-ttu-id="287a6-109">El archivo XML al que tiene acceso la siguiente consulta contiene pedidos de compra en dos espacios de nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="287a6-109">The XML file accessed by the following query contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="287a6-110">La consulta crea un nuevo árbol con solo los elementos de uno de los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="287a6-110">The query creates a new tree with just the elements in one of the namespaces.</span></span>  
  
 <span data-ttu-id="287a6-111">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedidos de compra consolidados](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="287a6-111">This example uses the following XML document: [Sample XML File: Consolidated Purchase Orders](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("ConsolidatedPurchaseOrders.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement newTree = new XElement("Root",  
    from el in cpo.Root.Elements()  
    where el.Name.Namespace == aw  
    select el  
);  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="287a6-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="287a6-112">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="287a6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="287a6-113">See Also</span></span>

- [<span data-ttu-id="287a6-114">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="287a6-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
