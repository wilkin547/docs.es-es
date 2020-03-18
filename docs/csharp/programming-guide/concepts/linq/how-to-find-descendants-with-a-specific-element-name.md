---
title: Procedimiento para buscar descendientes con un nombre de elemento específico (C#)
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: b3200a2fdf75dbf52079a2b3d27aa1a88d313406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141081"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="0e830-102">Procedimiento para buscar descendientes con un nombre de elemento específico (C#)</span><span class="sxs-lookup"><span data-stu-id="0e830-102">How to find descendants with a specific element name (C#)</span></span>
<span data-ttu-id="0e830-103">A veces, desea encontrar todos los descendientes con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="0e830-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="0e830-104">Podría escribir código para procesar una iteración en todos los descendientes, pero es más fácil usar el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="0e830-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e830-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e830-105">Example</span></span>  
 <span data-ttu-id="0e830-106">El ejemplo siguiente muestra cómo encontrar descendientes según el nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="0e830-106">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="0e830-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0e830-107">This code produces the following output:</span></span>  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="0e830-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e830-108">Example</span></span>  
 <span data-ttu-id="0e830-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0e830-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0e830-110">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0e830-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="0e830-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0e830-111">This code produces the following output:</span></span>  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e830-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e830-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
