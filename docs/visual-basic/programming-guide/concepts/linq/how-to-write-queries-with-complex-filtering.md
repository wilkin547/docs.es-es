---
title: Filtrar Escribir consultas con filtrado complejo (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: ac58394619b83e2b862e87926f0b6a722fdc3c7e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820924"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="2d873-102">Filtrar Escribir consultas con filtrado complejo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d873-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="2d873-103">Es posible que desee escribir consultas LINQ to XML con filtros complejos.</span><span class="sxs-lookup"><span data-stu-id="2d873-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="2d873-104">Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos.</span><span class="sxs-lookup"><span data-stu-id="2d873-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="2d873-105">En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.</span><span class="sxs-lookup"><span data-stu-id="2d873-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d873-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d873-106">Example</span></span>  
 <span data-ttu-id="2d873-107">En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY".</span><span class="sxs-lookup"><span data-stu-id="2d873-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="2d873-108">Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `True` si la colección tiene elementos en ella.</span><span class="sxs-lookup"><span data-stu-id="2d873-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="2d873-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2d873-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2d873-110">Para obtener más información sobre la `Any` operador, consulte [operaciones cuantificadoras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="2d873-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
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
  
 <span data-ttu-id="2d873-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d873-111">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="2d873-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d873-112">Example</span></span>  
 <span data-ttu-id="2d873-113">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2d873-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2d873-114">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2d873-114">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="2d873-115">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2d873-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="2d873-116">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d873-116">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d873-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d873-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="2d873-118">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d873-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="2d873-119">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="2d873-119">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="2d873-120">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="2d873-120">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="2d873-121">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="2d873-121">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="2d873-122">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d873-122">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="2d873-123">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d873-123">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
