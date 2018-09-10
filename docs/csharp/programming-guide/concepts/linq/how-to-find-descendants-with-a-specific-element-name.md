---
title: 'Cómo: Buscar descendientes con un nombre de elemento específico (C#)'
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: 6c5e035b4ee0168a0c41a34754314e18d089b1ef
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861424"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="691cc-102">Cómo: Buscar descendientes con un nombre de elemento específico (C#)</span><span class="sxs-lookup"><span data-stu-id="691cc-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="691cc-103">A veces, desea encontrar todos los descendientes con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="691cc-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="691cc-104">Podría escribir código para procesar una iteración en todos los descendientes, pero es más fácil usar el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="691cc-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="691cc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="691cc-105">Example</span></span>  
 <span data-ttu-id="691cc-106">El ejemplo siguiente muestra cómo encontrar descendientes según el nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="691cc-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="691cc-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="691cc-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="691cc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="691cc-108">Example</span></span>  
 <span data-ttu-id="691cc-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="691cc-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="691cc-110">Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="691cc-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="691cc-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="691cc-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="691cc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="691cc-112">See Also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
- [<span data-ttu-id="691cc-113">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="691cc-113">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
