---
title: Procedimiento para buscar un elemento secundario (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 1b0a3af5a1679643d73649f9de6b1dc3c44cbb0d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357172"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="20051-102">Cómo: buscar un elemento secundario (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20051-102">How to: Find a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="20051-103">En este tema se compara el eje del elemento secundario XPath con el método [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="20051-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="20051-104">La expresión XPath es `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="20051-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20051-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20051-105">Example</span></span>  
 <span data-ttu-id="20051-106">Este ejemplo busca el elemento secundario `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="20051-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="20051-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="20051-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="20051-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="20051-108">This example produces the following output:</span></span>  
  
```console
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20051-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="20051-109">See also</span></span>

- [<span data-ttu-id="20051-110">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20051-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
