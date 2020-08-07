---
title: Procedimiento para buscar un único descendiente con el método Descendants (C#)
description: Aprenda a buscar un único descendiente con el método de eje Descendants. Este método es útil para buscar un descendiente determinado con un nombre específico.
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 993e2b45f93509cf526d0c8c5de488b50de3efef
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303340"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="60e51-104">Procedimiento para buscar un único descendiente con el método Descendants (C#)</span><span class="sxs-lookup"><span data-stu-id="60e51-104">How to find a single descendant using the descendants method (C#)</span></span>
<span data-ttu-id="60e51-105">Puede utilizar el método de eje <xref:System.Xml.Linq.XContainer.Descendants%2A> para escribir rápidamente código para buscar un solo elemento cuyo nombre es único.</span><span class="sxs-lookup"><span data-stu-id="60e51-105">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="60e51-106">Esta técnica es especialmente útil si desea buscar un descendiente particular con un nombre específico.</span><span class="sxs-lookup"><span data-stu-id="60e51-106">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="60e51-107">Puede escribir el código para desplazarse al elemento deseado, pero a menudo resulta más rápido escribir el código usando el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e51-107">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e51-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60e51-108">Example</span></span>  
 <span data-ttu-id="60e51-109">Este ejemplo utiliza el operador de consulta estándar <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e51-109">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="60e51-110">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="60e51-110">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="60e51-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60e51-111">Example</span></span>  
 <span data-ttu-id="60e51-112">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="60e51-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="60e51-113">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="60e51-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="60e51-114">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="60e51-114">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
