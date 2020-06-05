---
title: Procedimiento para filtrar por nombres de elemento (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
ms.openlocfilehash: ccb768030e10d73b839df71093a27ff11b918650
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394342"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="925cd-102">Cómo: filtrar por nombres de elemento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="925cd-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="925cd-103">Al llamar a uno de los métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, puede filtrar por nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="925cd-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="925cd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="925cd-104">Example</span></span>  
 <span data-ttu-id="925cd-105">Este ejemplo recupera una colección de descendientes que se filtra para incluir solo los descendientes con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="925cd-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="925cd-106">En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="925cd-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim items As IEnumerable(Of XElement) = _  
    From el In po...<ProductName> _  
    Select el  
For Each prdName As XElement In items  
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
Next  
```  
  
 <span data-ttu-id="925cd-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="925cd-107">This code produces the following output:</span></span>  
  
```console  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="925cd-108">Los otros métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de colecciones <xref:System.Xml.Linq.XElement> siguen el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="925cd-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="925cd-109">Sus firmas son similares a <xref:System.Xml.Linq.XContainer.Elements%2A> y <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="925cd-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="925cd-110">A continuación, se incluye una lista completa de los métodos que tienen firmas similares:</span><span class="sxs-lookup"><span data-stu-id="925cd-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="925cd-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="925cd-111">Example</span></span>  
 <span data-ttu-id="925cd-112">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="925cd-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="925cd-113">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="925cd-113">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="925cd-114">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="925cd-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="925cd-115">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="925cd-115">This code produces the following output:</span></span>  
  
```console  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="925cd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="925cd-116">See also</span></span>

- [<span data-ttu-id="925cd-117">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="925cd-117">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
