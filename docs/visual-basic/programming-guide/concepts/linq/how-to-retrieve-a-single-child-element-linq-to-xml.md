---
title: Procedimiento para recuperar un único elemento secundario (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
ms.openlocfilehash: ab28ddd960374b22f44ac0c8fc7bddfe0608b8c5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397848"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="77abb-102">Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77abb-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="77abb-103">En este tema se explica cómo recuperar un único elemento secundario, dado el nombre del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="77abb-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="77abb-104">Si conoce el nombre del elemento secundario y que solo hay un elemento que tiene ese nombre, puede resultar cómodo recuperar solamente un elemento, en lugar de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="77abb-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="77abb-105">El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve el primer <xref:System.Xml.Linq.XElement> secundario con el <xref:System.Xml.Linq.XName> especificado.</span><span class="sxs-lookup"><span data-stu-id="77abb-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="77abb-106">Si desea recuperar un único elemento secundario de Visual Basic, un enfoque común consiste en utilizar la propiedad XML y después recuperar el primer elemento mediante una notación de indizador de matriz.</span><span class="sxs-lookup"><span data-stu-id="77abb-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77abb-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77abb-107">Example</span></span>  
 <span data-ttu-id="77abb-108">En el siguiente ejemplo se muestra el uso del método <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="77abb-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="77abb-109">Este ejemplo toma un árbol XML con el nombre `po` y busca el primer elemento con el nombre `Comment`.</span><span class="sxs-lookup"><span data-stu-id="77abb-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="77abb-110">El ejemplo de Visual Basic muestra el uso de la notación del indizador de matriz para recuperar un elemento único.</span><span class="sxs-lookup"><span data-stu-id="77abb-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="77abb-111">En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="77abb-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="77abb-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="77abb-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="77abb-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77abb-113">Example</span></span>  
 <span data-ttu-id="77abb-114">El siguiente ejemplo muestra el mismo código sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="77abb-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="77abb-115">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="77abb-115">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="77abb-116">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="77abb-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="77abb-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="77abb-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77abb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="77abb-118">See also</span></span>

- [<span data-ttu-id="77abb-119">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77abb-119">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
