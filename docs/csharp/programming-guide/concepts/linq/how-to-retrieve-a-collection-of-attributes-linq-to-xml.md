---
title: Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: b37600f02cd012e688d161a079c3c8647545cb2c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592664"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="37dff-102">Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="37dff-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="37dff-103">En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="37dff-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="37dff-104">Este método recupera los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="37dff-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37dff-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37dff-105">Example</span></span>  
 <span data-ttu-id="37dff-106">En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="37dff-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="37dff-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="37dff-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="37dff-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="37dff-108">See also</span></span>

- <span data-ttu-id="37dff-109">[LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="37dff-109">[LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md)</span></span>
