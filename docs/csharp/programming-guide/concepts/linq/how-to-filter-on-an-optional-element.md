---
title: Procedimiento para filtrar por un elemento opcional (C#)
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: 9b2ee9bf0cbed5504b96937fb37cf98728a15335
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710117"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="b5c12-102">Procedimiento para filtrar por un elemento opcional (C#)</span><span class="sxs-lookup"><span data-stu-id="b5c12-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="b5c12-103">En ocasiones, deseará filtrar por un elemento dado a pesar de que no está seguro de si existe o no en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="b5c12-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="b5c12-104">La consulta debería ejecutarse de forma que si el elemento en particular no tiene ningún elemento secundario, no se produzca una excepción de referencia nula al filtrar por él.</span><span class="sxs-lookup"><span data-stu-id="b5c12-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="b5c12-105">En el ejemplo siguiente, el elemento `Child5` no tiene ningún elemento secundario `Type`, pero aún así, la consulta se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5c12-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5c12-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5c12-106">Example</span></span>  
 <span data-ttu-id="b5c12-107">Este ejemplo utiliza el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5c12-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
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
  
 <span data-ttu-id="b5c12-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b5c12-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="b5c12-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5c12-109">Example</span></span>  
 <span data-ttu-id="b5c12-110">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b5c12-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b5c12-111">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b5c12-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b5c12-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b5c12-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5c12-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5c12-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- <span data-ttu-id="b5c12-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="b5c12-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- <span data-ttu-id="b5c12-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])</span><span class="sxs-lookup"><span data-stu-id="b5c12-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)</span></span>
