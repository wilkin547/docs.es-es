---
title: 'Cómo: Buscar el elemento raíz (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 72c3aed5-9522-4454-a876-2070aad13f2e
ms.openlocfilehash: 0e381c074a935a0cda5bd74bc456b8d7d9a495a8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344610"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="80e35-102">Cómo: buscar el elemento raíz (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80e35-102">How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="80e35-103">Este tema muestra cómo obtener el elemento raíz con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80e35-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="80e35-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="80e35-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="80e35-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80e35-105">Example</span></span>  
 <span data-ttu-id="80e35-106">Este ejemplo busca el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="80e35-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="80e35-107">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="80e35-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim el1 As XElement = po.Root  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1.Name)  
```  
  
 <span data-ttu-id="80e35-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="80e35-108">This example produces the following output:</span></span>  
  
```console  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="80e35-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="80e35-109">See also</span></span>

- [<span data-ttu-id="80e35-110">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80e35-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
