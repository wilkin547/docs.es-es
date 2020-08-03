---
title: Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)
description: El método Attributes de C# recupera los atributos de un elemento. En este ejemplo de LINQ to XML se muestra cómo iterar por la colección de atributos de un elemento.
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 5994086db6133530e63eb1328a7b524d30a0797d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103377"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="2d6e1-104">Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d6e1-104">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2d6e1-105">En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d6e1-105">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="2d6e1-106">Este método recupera los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="2d6e1-106">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d6e1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d6e1-107">Example</span></span>  
 <span data-ttu-id="2d6e1-108">En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="2d6e1-108">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="2d6e1-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d6e1-109">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d6e1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6e1-110">See also</span></span>

- [<span data-ttu-id="2d6e1-111">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2d6e1-111">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
