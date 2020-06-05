---
title: Procedimiento para buscar un elemento con un atributo específico
ms.date: 07/20/2015
ms.assetid: 59fb7c19-d42f-40eb-8cf8-f1d5b9658eb7
ms.openlocfilehash: ec5d3bf46d517e2cfb27c228674d9b86fefffa14
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405253"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-visual-basic"></a><span data-ttu-id="84c00-102">Cómo: buscar un elemento con un atributo específico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84c00-102">How to: Find an Element with a Specific Attribute (Visual Basic)</span></span>
<span data-ttu-id="84c00-103">En este tema se muestra cómo buscar un elemento que tiene un atributo con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="84c00-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84c00-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84c00-104">Example</span></span>  
 <span data-ttu-id="84c00-105">El ejemplo muestra cómo buscar el elemento `Address` que tiene un atributo `Type` con un valor de "Billing".</span><span class="sxs-lookup"><span data-stu-id="84c00-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="84c00-106">En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="84c00-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrder.xml")  
Dim address As IEnumerable(Of XElement) = _  
    From el In root.<Address> _  
    Where el.@Type = "Billing" _  
    Select el  
For Each el As XElement In address  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="84c00-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="84c00-107">This code produces the following output:</span></span>  
  
```xml  
          <Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
 <span data-ttu-id="84c00-108">Tenga en cuenta que en este ejemplo se usa la propiedad de [eje secundario XML](../../../language-reference/xml-axis/xml-child-axis-property.md), la [propiedad de eje de atributo XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md)y la [propiedad de valor XML](../../../language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="84c00-108">Note that this example uses the [XML Child axis property](../../../language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84c00-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84c00-109">Example</span></span>  
 <span data-ttu-id="84c00-110">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="84c00-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="84c00-111">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="84c00-111">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="84c00-112">En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order in a Namespace](sample-xml-file-typical-purchase-order-in-a-namespace.md) (Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres).</span><span class="sxs-lookup"><span data-stu-id="84c00-112">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim address As IEnumerable(Of XElement) = _  
            From el In root.<aw:Address> _  
            Where el.@aw:Type = "Billing" _  
            Select el  
        For Each el As XElement In address  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="84c00-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="84c00-113">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84c00-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84c00-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="84c00-115">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84c00-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
- [<span data-ttu-id="84c00-116">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84c00-116">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="84c00-117">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84c00-117">Projection Operations (Visual Basic)</span></span>](projection-operations.md)
