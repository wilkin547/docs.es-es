---
title: Procedimiento para encadenar llamadas de métodos de eje (LINQ to XML) (C#)
description: En estos ejemplos de LINQ to XML de C# se muestran llamadas a dos ejes para buscar todos los elementos de un nombre especificado en una profundidad determinada del árbol.
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: f26efd2ca918fd36916eb4f01462af70066219a0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105388"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="7ee30-103">Procedimiento para encadenar llamadas de métodos de eje (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7ee30-103">How to chain axis method calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7ee30-104">Un patrón común que puede utilizar en el código consiste en llamar a un método Axis y, después, llamar a uno de los métodos de extensión Axes.</span><span class="sxs-lookup"><span data-stu-id="7ee30-104">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="7ee30-105">Hay dos métodos Axes con el nombre `Elements` que devuelven una colección de elementos: el método <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> y el método <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-105">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7ee30-106">Puede combinar estos dos ejes para encontrar todos los elementos de un nombre especificado en una profundidad determinada del árbol.</span><span class="sxs-lookup"><span data-stu-id="7ee30-106">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ee30-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ee30-107">Example</span></span>  
 <span data-ttu-id="7ee30-108">En este ejemplo se usa <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> para buscar todos los elementos `Name` en todos los elementos `Address` de todos los elementos `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="7ee30-108">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="7ee30-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7ee30-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="7ee30-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7ee30-110">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="7ee30-111">Esto funciona porque una de las implementaciones del eje `Elements` es un método de extensión en <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-111">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="7ee30-112"><xref:System.Xml.Linq.XElement> se deriva de <xref:System.Xml.Linq.XContainer>, de modo que puede llamar al método <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> según los resultados de una llamada al método <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-112"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ee30-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ee30-113">Example</span></span>  
 <span data-ttu-id="7ee30-114">A veces, desea recuperar todos los elementos de una profundidad determinada cuando es posible que intervengan (o no) antecesores.</span><span class="sxs-lookup"><span data-stu-id="7ee30-114">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="7ee30-115">Por ejemplo, en el siguiente documento, podría recuperar todos los elementos `ConfigParameter` que son secundarios del elemento `Customer`, pero no el elemento `ConfigParameter` que es un secundario del elemento `Root`.</span><span class="sxs-lookup"><span data-stu-id="7ee30-115">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="7ee30-116">Para ello, puede usar el eje <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7ee30-116">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="7ee30-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7ee30-117">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="7ee30-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ee30-118">Example</span></span>  
 <span data-ttu-id="7ee30-119">El siguiente ejemplo muestra la misma técnica para XML que se encuentre en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7ee30-119">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="7ee30-120">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7ee30-120">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7ee30-121">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7ee30-121">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="7ee30-122">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7ee30-122">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ee30-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ee30-123">See also</span></span>

- [<span data-ttu-id="7ee30-124">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7ee30-124">LINQ to XML Axes (C#)</span></span>](linq-to-xml-axes-overview.md)
