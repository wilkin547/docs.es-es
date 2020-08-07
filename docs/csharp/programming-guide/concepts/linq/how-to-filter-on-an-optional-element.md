---
title: Procedimiento para filtrar por un elemento opcional (C#)
description: Aprenda a filtrar por un elemento opcional, aunque no esté seguro de que existe en el documento XML.
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: a1cd93b70ea2c077437b58bd341f51f15f014871
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302872"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="b5cb1-103">Procedimiento para filtrar por un elemento opcional (C#)</span><span class="sxs-lookup"><span data-stu-id="b5cb1-103">How to filter on an optional element (C#)</span></span>
<span data-ttu-id="b5cb1-104">En ocasiones, deseará filtrar por un elemento dado a pesar de que no está seguro de si existe o no en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="b5cb1-104">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="b5cb1-105">La consulta debería ejecutarse de forma que si el elemento en particular no tiene ningún elemento secundario, no se produzca una excepción de referencia nula al filtrar por él.</span><span class="sxs-lookup"><span data-stu-id="b5cb1-105">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="b5cb1-106">En el ejemplo siguiente, el elemento `Child5` no tiene ningún elemento secundario `Type`, pero aún así, la consulta se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5cb1-106">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5cb1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5cb1-107">Example</span></span>  
 <span data-ttu-id="b5cb1-108">Este ejemplo utiliza el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5cb1-108">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="b5cb1-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b5cb1-109">This code produces the following output:</span></span>  
  
```output  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="b5cb1-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5cb1-110">Example</span></span>  
 <span data-ttu-id="b5cb1-111">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b5cb1-111">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b5cb1-112">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b5cb1-112">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="b5cb1-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b5cb1-113">This code produces the following output:</span></span>  
  
```output  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5cb1-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5cb1-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b5cb1-115">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="b5cb1-115">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b5cb1-116">Operaciones de proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="b5cb1-116">Projection Operations (C#)</span></span>](./projection-operations.md)
