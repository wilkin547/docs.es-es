---
title: "Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 580315fda6ef6f1919f7f2aabc0cf3604a5c4337
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="f66cc-102">Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f66cc-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f66cc-103">En este tema se explica cómo recuperar un único elemento secundario, dado el nombre del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="f66cc-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="f66cc-104">Si conoce el nombre del elemento secundario y que solo hay un elemento que tiene ese nombre, puede resultar cómodo recuperar solamente un elemento, en lugar de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="f66cc-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="f66cc-105">El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve el primer <xref:System.Xml.Linq.XElement> secundario con el <xref:System.Xml.Linq.XName> especificado.</span><span class="sxs-lookup"><span data-stu-id="f66cc-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="f66cc-106">Si desea recuperar un único elemento secundario de Visual Basic, un enfoque común consiste en utilizar la propiedad XML y después recuperar el primer elemento mediante una notación de indizador de matriz.</span><span class="sxs-lookup"><span data-stu-id="f66cc-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f66cc-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f66cc-107">Example</span></span>  
 <span data-ttu-id="f66cc-108">En el siguiente ejemplo se muestra el uso del método <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="f66cc-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="f66cc-109">Este ejemplo toma un árbol XML con el nombre `po` y busca el primer elemento con el nombre `Comment`.</span><span class="sxs-lookup"><span data-stu-id="f66cc-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="f66cc-110">El ejemplo de Visual Basic muestra el uso de la notación del indizador de matriz para recuperar un elemento único.</span><span class="sxs-lookup"><span data-stu-id="f66cc-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="f66cc-111">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f66cc-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="f66cc-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f66cc-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="f66cc-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f66cc-113">Example</span></span>  
 <span data-ttu-id="f66cc-114">El siguiente ejemplo muestra el mismo código sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f66cc-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="f66cc-115">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="f66cc-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="f66cc-116">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f66cc-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="f66cc-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f66cc-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f66cc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f66cc-118">See Also</span></span>  
 [<span data-ttu-id="f66cc-119">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f66cc-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
