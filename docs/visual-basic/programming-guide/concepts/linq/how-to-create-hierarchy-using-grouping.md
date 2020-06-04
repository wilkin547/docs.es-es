---
title: Procedimiento para crear una jerarquía mediante la agrupación
ms.date: 07/20/2015
ms.assetid: 4eb3ca6b-1aed-43de-b8b9-41c769c993f8
ms.openlocfilehash: 551a1b8909eb36fea17c93563895296f65794cac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414587"
---
# <a name="how-to-create-hierarchy-using-grouping-visual-basic"></a>Cómo: crear una jerarquía mediante la agrupación (Visual Basic)
Este ejemplo muestra cómo agrupar datos y después generar XML basado en la agrupación.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo agrupa primero los datos por categorías y, a continuación, genera un nuevo archivo XML en el que la jerarquía XML refleja la agrupación.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
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
  
## <a name="see-also"></a>Vea también

- [Técnicas de consulta avanzadas (LINQ to XML) (Visual Basic)](advanced-query-techniques-linq-to-xml.md)
