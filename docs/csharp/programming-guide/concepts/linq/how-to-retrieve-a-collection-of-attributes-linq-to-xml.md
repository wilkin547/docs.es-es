---
title: Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: d535f56507812855f08b31417124b4408dfea017
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599821"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)
En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>. Este método recupera los atributos de un elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.  
  
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
  
 Este código genera el siguiente resultado:  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])
