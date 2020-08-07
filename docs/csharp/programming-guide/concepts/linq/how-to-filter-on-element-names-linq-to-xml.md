---
title: Procedimiento para filtrar por nombres de elemento (LINQ to XML) (C#)
description: Aprenda a filtrar por el nombre del elemento cuando se llama a un método que devuelve IEnumerable de XElement.
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: be660a69b8d860ad907661ce17002379b8842121
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301754"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="da1a3-103">Procedimiento para filtrar por nombres de elemento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="da1a3-103">How to filter on element names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="da1a3-104">Al llamar a uno de los métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, puede filtrar por nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="da1a3-104">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da1a3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da1a3-105">Example</span></span>  
 <span data-ttu-id="da1a3-106">Este ejemplo recupera una colección de descendientes que se filtra para incluir solo los descendientes con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="da1a3-106">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="da1a3-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="da1a3-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="da1a3-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="da1a3-108">This code produces the following output:</span></span>  
  
```output  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="da1a3-109">Los otros métodos que devuelven <xref:System.Collections.Generic.IEnumerable%601> de colecciones <xref:System.Xml.Linq.XElement> siguen el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="da1a3-109">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="da1a3-110">Sus firmas son similares a <xref:System.Xml.Linq.XContainer.Elements%2A> y <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="da1a3-110">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="da1a3-111">A continuación, se incluye una lista completa de los métodos que tienen firmas similares:</span><span class="sxs-lookup"><span data-stu-id="da1a3-111">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="da1a3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da1a3-112">Example</span></span>  
 <span data-ttu-id="da1a3-113">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="da1a3-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="da1a3-114">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da1a3-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="da1a3-115">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="da1a3-115">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="da1a3-116">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="da1a3-116">This code produces the following output:</span></span>  
  
```output  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="da1a3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="da1a3-117">See also</span></span>

- [<span data-ttu-id="da1a3-118">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="da1a3-118">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
