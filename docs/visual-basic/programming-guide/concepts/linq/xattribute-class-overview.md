---
title: Información general de la clase XAttribute
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 5b165044b4bea83e1a0789e3dd00367ed27b43e8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413211"
---
# <a name="xattribute-class-overview-visual-basic"></a>Información general de la clase XAttribute (Visual Basic)
Los atributos son pares de nombre y valor asociados a un elemento. La clase <xref:System.Xml.Linq.XAttribute> representa los atributos XML.  
  
## <a name="overview"></a>Información general  
 Trabajar con atributos en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es similar a trabajar con elementos. Sus constructores son similares. Los métodos que usa para recuperar colecciones de ellos también son similares. Una expresión de consulta LINQ de una colección de atributos se parece mucho a una expresión de consulta LINQ de una colección de elementos.  
  
 Se conserva el orden en el que se agregaron los atributos a un elemento. Es decir, cuando procese una iteración en los atributos, los verá en el mismo orden en el que se agregaron.  
  
## <a name="the-xattribute-constructor"></a>El constructor XAttribute  
 El siguiente constructor de la clase <xref:System.Xml.Linq.XAttribute> es el que usará normalmente:  
  
|Constructor|Description|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Crea un objeto <xref:System.Xml.Linq.XAttribute>. El argumento `name` especifica el nombre del atributo; `content` especifica el contenido del atributo.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Crear un elemento con un atributo  
 En el código siguiente se muestra un elemento que contiene un atributo utilizando literales XML en Visual Basic:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Construcción funcional de los atributos  
 Puede construir objetos <xref:System.Xml.Linq.XAttribute> de modo similar a la construcción de los objetos <xref:System.Xml.Linq.XElement>, tal como se indica a continuación:  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Los atributos no son nodos  
 Existen algunas diferencias entre los atributos y los elementos. Los objetos <xref:System.Xml.Linq.XAttribute> no son nodos en el árbol XML. Son pares de nombre y valor asociados a un elemento XML. A diferencia de Document Object Model (DOM), esto refleja de manera más precisa la estructura del código XML. Aunque los objetos <xref:System.Xml.Linq.XAttribute> no son realmente nodos en el árbol XML, trabajar con objetos <xref:System.Xml.Linq.XAttribute> es muy similar a trabajar con objetos <xref:System.Xml.Linq.XElement>.  
  
 Esta distinción solo resulta de importancia para los desarrolladores que escriban código que trabaje con árboles XML en el nivel de nodo. A muchos desarrolladores no les afecta esta distinción.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la programación de LINQ to XML (Visual Basic)](linq-to-xml-programming-overview.md)
