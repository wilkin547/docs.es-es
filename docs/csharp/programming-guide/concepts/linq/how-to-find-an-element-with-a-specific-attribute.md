---
title: Procedimiento para buscar un elemento con un atributo específico (C#)
description: Aprenda a buscar un elemento que tenga un atributo con un valor específico. Vea ejemplos de código y examine recursos adicionales.
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 44875ca2104e7a8f83e83da983af49ef85c89f0a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303288"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="6ba3f-104">Procedimiento para buscar un elemento con un atributo específico (C#)</span><span class="sxs-lookup"><span data-stu-id="6ba3f-104">How to find an element with a specific attribute (C#)</span></span>
<span data-ttu-id="6ba3f-105">En este tema se muestra cómo buscar un elemento que tiene un atributo con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-105">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ba3f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ba3f-106">Example</span></span>  
 <span data-ttu-id="6ba3f-107">El ejemplo muestra cómo buscar el elemento `Address` que tiene un atributo `Type` con un valor de "Billing".</span><span class="sxs-lookup"><span data-stu-id="6ba3f-107">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="6ba3f-108">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="6ba3f-108">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="6ba3f-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6ba3f-109">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="6ba3f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ba3f-110">Example</span></span>  
 <span data-ttu-id="6ba3f-111">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-111">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="6ba3f-112">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6ba3f-112">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6ba3f-113">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6ba3f-113">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="6ba3f-114">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6ba3f-114">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ba3f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ba3f-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="6ba3f-116">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="6ba3f-116">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="6ba3f-117">Operaciones de proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="6ba3f-117">Projection Operations (C#)</span></span>](./projection-operations.md)
