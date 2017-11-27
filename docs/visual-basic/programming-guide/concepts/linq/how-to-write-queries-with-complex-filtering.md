---
title: "Cómo: escribir consultas con filtrado complejo (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15ed0dcf87ad05b1da984aca494d28c1b19eb685
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="dd242-102">Cómo: escribir consultas con filtrado complejo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd242-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="dd242-103">Es posible que desee escribir consultas LINQ to XML con filtros complejos.</span><span class="sxs-lookup"><span data-stu-id="dd242-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="dd242-104">Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos.</span><span class="sxs-lookup"><span data-stu-id="dd242-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="dd242-105">En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.</span><span class="sxs-lookup"><span data-stu-id="dd242-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd242-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd242-106">Example</span></span>  
 <span data-ttu-id="dd242-107">En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY".</span><span class="sxs-lookup"><span data-stu-id="dd242-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="dd242-108">Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `True` si la colección tiene elementos en ella.</span><span class="sxs-lookup"><span data-stu-id="dd242-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="dd242-109">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="dd242-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="dd242-110">Para obtener más información sobre la `Any` (operador), consulte [operaciones cuantificadoras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="dd242-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 <span data-ttu-id="dd242-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="dd242-111">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="dd242-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd242-112">Example</span></span>  
 <span data-ttu-id="dd242-113">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dd242-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="dd242-114">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="dd242-114">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="dd242-115">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="dd242-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="dd242-116">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="dd242-116">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd242-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd242-117">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="dd242-118">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd242-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="dd242-119">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="dd242-119">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="dd242-120">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="dd242-120">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)  
 [<span data-ttu-id="dd242-121">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="dd242-121">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="dd242-122">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd242-122">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
 [<span data-ttu-id="dd242-123">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd242-123">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
