---
title: Procedimiento para filtrar por nombres de elemento (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 9c29183a7548a4551aca813b3d297f7e03484b36
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710110"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="422a3-102">Procedimiento para filtrar por nombres de elemento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="422a3-102">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="422a3-103">Al llamar a uno de los métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, puede filtrar por nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="422a3-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="422a3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="422a3-104">Example</span></span>  
 <span data-ttu-id="422a3-105">Este ejemplo recupera una colección de descendientes que se filtra para incluir solo los descendientes con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="422a3-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="422a3-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="422a3-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="422a3-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="422a3-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="422a3-108">Los otros métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de colecciones <xref:System.Xml.Linq.XElement> siguen el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="422a3-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="422a3-109">Sus firmas son similares a <xref:System.Xml.Linq.XContainer.Elements%2A> y <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="422a3-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="422a3-110">A continuación, se incluye una lista completa de los métodos que tienen firmas similares:</span><span class="sxs-lookup"><span data-stu-id="422a3-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="422a3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="422a3-111">Example</span></span>  
 <span data-ttu-id="422a3-112">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="422a3-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="422a3-113">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="422a3-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="422a3-114">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="422a3-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="422a3-115">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="422a3-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="422a3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="422a3-116">See also</span></span>

- <span data-ttu-id="422a3-117">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="422a3-117">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)</span></span>
