---
title: Procedimiento para recuperar el valor superficial de un elemento
ms.date: 07/20/2015
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
ms.openlocfilehash: 24e6b128481f56941f0a61da9766f02813a46e97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397822"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a><span data-ttu-id="d0503-102">Cómo: recuperar el valor superficial de un elemento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0503-102">How to: Retrieve the Shallow Value of an Element (Visual Basic)</span></span>

<span data-ttu-id="d0503-103">Este tema muestra cómo obtener el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="d0503-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="d0503-104">El valor superficial es el valor del elemento específico solamente, en oposición al valor profundo, que incluye los valores de todos los elementos descendientes concatenados en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="d0503-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>

<span data-ttu-id="d0503-105">Cuando se recupera el valor de un elemento utilizando la conversión o la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, se recupera el valor profundo.</span><span class="sxs-lookup"><span data-stu-id="d0503-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="d0503-106">Para recuperar el valor superficial, se puede usar el método de extensión `ShallowValue`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d0503-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="d0503-107">La recuperación del valor superficial es útil cuando se desea seleccionar elementos en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="d0503-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>

<span data-ttu-id="d0503-108">En el ejemplo siguiente se declara un método de extensión que recupera el valor superficial de un elemento.</span><span class="sxs-lookup"><span data-stu-id="d0503-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="d0503-109">A continuación, se utiliza el método de extensión en una consulta para enumerar todos los elementos que contienen un valor calculado.</span><span class="sxs-lookup"><span data-stu-id="d0503-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>

## <a name="example"></a><span data-ttu-id="d0503-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0503-110">Example</span></span>

<span data-ttu-id="d0503-111">El siguiente archivo de texto, Report.xml, es el origen de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d0503-111">The following text file, Report.xml, is the source for this example.</span></span>

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

```vb
Module Module1
    <System.Runtime.CompilerServices.Extension()> _
    Public Function ShallowValue(ByVal xe As XElement)
        Return xe _
               .Nodes() _
               .OfType(Of XText)() _
               .Aggregate(New StringBuilder(), _
                              Function(s, c) s.Append(c), _
                              Function(s) s.ToString())
    End Function

    Sub Main()
        Dim root As XElement = XElement.Load("Report.xml")

        Dim query As IEnumerable(Of XElement) = _
            From el In root.Descendants() _
            Where (el.ShallowValue().StartsWith("=")) _
            Select el

        For Each q As XElement In query
            Console.WriteLine("{0}{1}{2}", _
                q.Name.ToString().PadRight(8), _
                q.Attribute("Name").ToString().PadRight(20), _
                q.ShallowValue())
        Next
    End Sub
End Module
```

<span data-ttu-id="d0503-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d0503-112">This example produces the following output:</span></span>

```console
Column  Name="CustomerId"   =Customer.CustomerId.Heading
Column  Name="Name"         =Customer.Name.Heading
Column  Name="CustomerId"   =Customer.CustomerId
Column  Name="Name"         =Customer.Name
```

## <a name="see-also"></a><span data-ttu-id="d0503-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0503-113">See also</span></span>

- [<span data-ttu-id="d0503-114">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0503-114">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
