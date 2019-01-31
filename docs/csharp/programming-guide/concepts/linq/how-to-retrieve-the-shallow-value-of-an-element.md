---
title: Procedimiento para recuperar el valor superficial de un elemento (C#)
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 593fe1c22664f1e4e8322cb8816e58f4721c5bf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672849"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="1ef9d-102">Procedimiento para recuperar el valor superficial de un elemento (C#)</span><span class="sxs-lookup"><span data-stu-id="1ef9d-102">How to: Retrieve the Shallow Value of an Element (C#)</span></span>
<span data-ttu-id="1ef9d-103">Este tema muestra cómo obtener el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="1ef9d-104">El valor superficial es el valor del elemento específico solamente, en oposición al valor profundo, que incluye los valores de todos los elementos descendientes concatenados en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="1ef9d-105">Cuando se recupera el valor de un elemento utilizando la conversión o la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, se recupera el valor profundo.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="1ef9d-106">Para recuperar el valor superficial, se puede usar el método de extensión `ShallowValue`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="1ef9d-107">La recuperación del valor superficial es útil cuando se desea seleccionar elementos en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="1ef9d-108">En el ejemplo siguiente se declara un método de extensión que recupera el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="1ef9d-109">A continuación, se utiliza el método de extensión en una consulta para enumerar todos los elementos que contienen un valor calculado.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef9d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ef9d-110">Example</span></span>  
 <span data-ttu-id="1ef9d-111">El siguiente archivo de texto, Report.xml, es el origen de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
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
  
 <span data-ttu-id="1ef9d-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1ef9d-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ef9d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef9d-113">See also</span></span>

- <span data-ttu-id="1ef9d-114">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="1ef9d-114">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)</span></span>
