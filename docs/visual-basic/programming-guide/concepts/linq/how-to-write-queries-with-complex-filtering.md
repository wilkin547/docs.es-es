---
title: Procedimiento para escribir consultas con filtrado complejo
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: 18ed4379b7ec9c8007cc3c189fc45571b5161911
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397627"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="7f442-102">Cómo: escribir consultas con filtrado complejo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f442-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="7f442-103">Es posible que desee escribir consultas LINQ to XML con filtros complejos.</span><span class="sxs-lookup"><span data-stu-id="7f442-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="7f442-104">Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos.</span><span class="sxs-lookup"><span data-stu-id="7f442-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="7f442-105">En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.</span><span class="sxs-lookup"><span data-stu-id="7f442-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f442-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f442-106">Example</span></span>  
 <span data-ttu-id="7f442-107">En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY".</span><span class="sxs-lookup"><span data-stu-id="7f442-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="7f442-108">Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `True` si la colección tiene elementos en ella.</span><span class="sxs-lookup"><span data-stu-id="7f442-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="7f442-109">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7f442-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7f442-110">Para obtener más información sobre el `Any` operador, vea [operaciones cuantificadoras (Visual Basic)](quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7f442-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](quantifier-operations.md).</span></span>  
  
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
  
 <span data-ttu-id="7f442-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7f442-111">This code produces the following output:</span></span>  
  
```console  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="7f442-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f442-112">Example</span></span>  
 <span data-ttu-id="7f442-113">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7f442-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="7f442-114">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7f442-114">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7f442-115">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7f442-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="7f442-116">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7f442-116">This code produces the following output:</span></span>  
  
```console  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f442-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f442-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="7f442-118">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f442-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
- [<span data-ttu-id="7f442-119">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="7f442-119">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="7f442-120">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="7f442-120">XML Attribute Axis Property</span></span>](../../../language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="7f442-121">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="7f442-121">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="7f442-122">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f442-122">Projection Operations (Visual Basic)</span></span>](projection-operations.md)
- [<span data-ttu-id="7f442-123">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f442-123">Quantifier Operations (Visual Basic)</span></span>](quantifier-operations.md)
