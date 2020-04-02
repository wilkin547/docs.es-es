---
title: Procedimiento para recuperar el valor de un atributo (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 212ad3bb3097e7e2c76da8f165011b181f329d4c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249199"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a>Procedimiento para recuperar el valor de un atributo (LINQ to XML) (C#)
Este tema muestra cómo obtener el valor de los atributos. Existen dos formas principales: puede convertir un elemento <xref:System.Xml.Linq.XAttribute> al tipo deseado; el operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado. Como alternativa, puede usar la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>. Sin embargo, la conversión suele ser el mejor método. Si convierte el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un atributo que podría existir o no. Para ver ejemplos de esta técnica, consulte [Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Ejemplo  
 Para recuperar el valor de un atributo, basta con convertir el objeto <xref:System.Xml.Linq.XAttribute> al tipo deseado.  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra cómo recuperar el valor de un atributo, en el que el atributo se encuentra en un espacio de nombres. Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
abcde  
```  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
