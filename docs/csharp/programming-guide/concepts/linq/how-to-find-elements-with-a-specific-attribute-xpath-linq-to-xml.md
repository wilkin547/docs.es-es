---
title: Procedimiento para buscar elementos con un atributo específico (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: e79cad3ad6fb0bf88e388b552f8e39327acfb4ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141041"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="e6fc1-102">Procedimiento para buscar elementos con un atributo específico (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e6fc1-102">How to find elements with a specific attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="e6fc1-103">En ocasiones, deseará buscar todos los elementos que tengan un atributo en particular.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="e6fc1-104">Pero no le preocupa cuáles es el contenido del atributo.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="e6fc1-105">En vez de ello, desea realizar la selección en función de si existe o no el atributo.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="e6fc1-106">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="e6fc1-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="e6fc1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6fc1-107">Example</span></span>  
 <span data-ttu-id="e6fc1-108">El siguiente código selecciona únicamente los elementos que tengan el atributo `Select`.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e6fc1-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e6fc1-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  