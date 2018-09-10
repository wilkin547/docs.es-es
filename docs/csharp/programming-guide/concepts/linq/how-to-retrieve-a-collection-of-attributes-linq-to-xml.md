---
title: 'Cómo: Recuperar una colección de atributos (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: e872d0fefa5ea3c25208bf5deab42b59b5b7d5b0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526938"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="e9947-102">Cómo: Recuperar una colección de atributos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e9947-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e9947-103">En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9947-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="e9947-104">Este método recupera los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="e9947-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9947-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9947-105">Example</span></span>  
 <span data-ttu-id="e9947-106">En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="e9947-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="e9947-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e9947-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9947-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9947-108">See Also</span></span>

- <span data-ttu-id="e9947-109">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="e9947-109">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)</span></span>
