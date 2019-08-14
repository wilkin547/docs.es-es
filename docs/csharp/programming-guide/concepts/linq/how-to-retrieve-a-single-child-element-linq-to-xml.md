---
title: Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: 16b9c54365bf32c87cc38ba5a2982623786d5cbf
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709927"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="75e43-102">Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="75e43-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="75e43-103">En este tema se explica cómo recuperar un único elemento secundario, dado el nombre del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="75e43-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="75e43-104">Si conoce el nombre del elemento secundario y que solo hay un elemento que tiene ese nombre, puede resultar cómodo recuperar solamente un elemento, en lugar de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="75e43-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="75e43-105">El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve el primer <xref:System.Xml.Linq.XElement> secundario con el <xref:System.Xml.Linq.XName> especificado.</span><span class="sxs-lookup"><span data-stu-id="75e43-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="75e43-106">Si desea recuperar un único elemento secundario de Visual Basic, un enfoque común consiste en utilizar la propiedad XML y después recuperar el primer elemento mediante una notación de indizador de matriz.</span><span class="sxs-lookup"><span data-stu-id="75e43-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75e43-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75e43-107">Example</span></span>  
 <span data-ttu-id="75e43-108">En el siguiente ejemplo se muestra el uso del método <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="75e43-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="75e43-109">Este ejemplo toma un árbol XML con el nombre `po` y busca el primer elemento con el nombre `Comment`.</span><span class="sxs-lookup"><span data-stu-id="75e43-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="75e43-110">El ejemplo de Visual Basic muestra el uso de la notación del indizador de matriz para recuperar un elemento único.</span><span class="sxs-lookup"><span data-stu-id="75e43-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="75e43-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="75e43-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="75e43-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="75e43-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="75e43-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75e43-113">Example</span></span>  
 <span data-ttu-id="75e43-114">El siguiente ejemplo muestra el mismo código sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="75e43-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="75e43-115">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="75e43-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="75e43-116">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="75e43-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="75e43-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="75e43-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75e43-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="75e43-118">See also</span></span>

- <span data-ttu-id="75e43-119">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="75e43-119">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)</span></span>
