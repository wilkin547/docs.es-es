---
title: Procedimiento para buscar un elemento con un atributo específico (C#)
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 0362ded5984ff797a1ced93076679b7b975b998c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709949"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="e9334-102">Procedimiento para buscar un elemento con un atributo específico (C#)</span><span class="sxs-lookup"><span data-stu-id="e9334-102">How to: Find an Element with a Specific Attribute (C#)</span></span>
<span data-ttu-id="e9334-103">En este tema se muestra cómo buscar un elemento que tiene un atributo con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="e9334-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9334-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9334-104">Example</span></span>  
 <span data-ttu-id="e9334-105">El ejemplo muestra cómo buscar el elemento `Address` que tiene un atributo `Type` con un valor de "Billing".</span><span class="sxs-lookup"><span data-stu-id="e9334-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="e9334-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="e9334-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e9334-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e9334-107">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="e9334-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9334-108">Example</span></span>  
 <span data-ttu-id="e9334-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e9334-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e9334-110">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e9334-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e9334-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e9334-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e9334-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e9334-112">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9334-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9334-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <span data-ttu-id="e9334-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="e9334-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- <span data-ttu-id="e9334-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])</span><span class="sxs-lookup"><span data-stu-id="e9334-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)</span></span>
