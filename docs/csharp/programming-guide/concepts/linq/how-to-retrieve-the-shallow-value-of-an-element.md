---
title: "Cómo: Recuperar el valor superficial de un elemento (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dcbe3faa457a4880a85f5827d0e5c4808b6a44b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="9d596-102">Cómo: Recuperar el valor superficial de un elemento (C#)</span><span class="sxs-lookup"><span data-stu-id="9d596-102">How to: Retrieve the Shallow Value of an Element (C#)</span></span>
<span data-ttu-id="9d596-103">Este tema muestra cómo obtener el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9d596-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="9d596-104">El valor superficial es el valor del elemento específico solamente, en oposición al valor profundo, que incluye los valores de todos los elementos descendientes concatenados en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="9d596-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="9d596-105">Cuando se recupera el valor de un elemento utilizando la conversión o la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, se recupera el valor profundo.</span><span class="sxs-lookup"><span data-stu-id="9d596-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="9d596-106">Para recuperar el valor superficial, se puede usar el método de extensión `ShallowValue`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d596-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="9d596-107">La recuperación del valor superficial es útil cuando se desea seleccionar elementos en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="9d596-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="9d596-108">En el ejemplo siguiente se declara un método de extensión que recupera el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9d596-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="9d596-109">A continuación, se utiliza el método de extensión en una consulta para enumerar todos los elementos que contienen un valor calculado.</span><span class="sxs-lookup"><span data-stu-id="9d596-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d596-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d596-110">Example</span></span>  
 <span data-ttu-id="9d596-111">El siguiente archivo de texto, Report.xml, es el origen de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9d596-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="9d596-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9d596-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d596-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d596-113">See Also</span></span>  
 <span data-ttu-id="9d596-114">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="9d596-114">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)</span></span>
