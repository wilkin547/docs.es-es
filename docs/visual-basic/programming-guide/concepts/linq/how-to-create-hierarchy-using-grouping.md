---
title: 'Cómo: crear la jerarquía con la agrupación (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 4eb3ca6b-1aed-43de-b8b9-41c769c993f8
ms.openlocfilehash: 9df85a52d63c4d7dbffb99a47378d3a1efc10cca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639329"
---
# <a name="how-to-create-hierarchy-using-grouping-visual-basic"></a><span data-ttu-id="6e221-102">Cómo: crear la jerarquía con la agrupación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e221-102">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>
<span data-ttu-id="6e221-103">Este ejemplo muestra cómo agrupar datos y después generar XML basado en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="6e221-103">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e221-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e221-104">Example</span></span>  
 <span data-ttu-id="6e221-105">Este ejemplo agrupa primero los datos por categorías y, a continuación, genera un nuevo archivo XML en el que la jerarquía XML refleja la agrupación.</span><span class="sxs-lookup"><span data-stu-id="6e221-105">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="6e221-106">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6e221-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim doc As XElement = XElement.Load("Data.xml")  
Dim newData As XElement = _  
    <Root>  
        <%= _  
            From data In doc.<Data> _  
            Group By category = data.<Category>(0).Value _  
            Into groupedData = Group _  
            Select <Group ID=<%= category %>>  
                       <%= _  
                           From g In groupedData _  
                           Select _  
                           <Data>  
                               <%= g.<Quantity>(0) %>  
                               <%= g.<Price>(0) %>  
                           </Data> _  
                       %>  
                   </Group> _  
        %>  
    </Root>  
Console.WriteLine(newData)  
```  
  
 <span data-ttu-id="6e221-107">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6e221-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Group ID="A">  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>24.50</Price>  
    </Data>  
    <Data>  
      <Quantity>5</Quantity>  
      <Price>4.95</Price>  
    </Data>  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>66.00</Price>  
    </Data>  
    <Data>  
      <Quantity>15</Quantity>  
      <Price>29.00</Price>  
    </Data>  
  </Group>  
  <Group ID="B">  
    <Data>  
      <Quantity>1</Quantity>  
      <Price>89.99</Price>  
    </Data>  
    <Data>  
      <Quantity>10</Quantity>  
      <Price>.99</Price>  
    </Data>  
    <Data>  
      <Quantity>8</Quantity>  
      <Price>6.99</Price>  
    </Data>  
  </Group>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e221-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e221-108">See Also</span></span>  
 [<span data-ttu-id="6e221-109">Técnicas avanzadas de consulta (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e221-109">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
