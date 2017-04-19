---
title: "Información general de la clase XAttribute (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1ce5f4be6006908b35057854f89432471fd9f06b
ms.lasthandoff: 03/13/2017

---
# <a name="xattribute-class-overview-visual-basic"></a>Información general de la clase XAttribute (Visual Basic)
Los atributos son pares de nombre y valor asociados a un elemento. La <xref:System.Xml.Linq.XAttribute>clase representa atributos XML.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="overview"></a>Información general  
 Trabajar con atributos en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es similar a trabajar con elementos. Sus constructores son similares. Los métodos que usa para recuperar colecciones de ellos también son similares. Un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] parece muy similar a la expresión de consulta para una colección de atributos de un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] expresión para una colección de elementos de consulta.  
  
 Se conserva el orden en el que se agregaron los atributos a un elemento. Es decir, cuando procese una iteración en los atributos, los verá en el mismo orden en el que se agregaron.  
  
## <a name="the-xattribute-constructor"></a>El constructor XAttribute  
 El siguiente constructor de la <xref:System.Xml.Linq.XAttribute>clase es el que usará normalmente:</xref:System.Xml.Linq.XAttribute>  
  
|Constructor|Descripción|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Crea un <xref:System.Xml.Linq.XAttribute>objeto.</xref:System.Xml.Linq.XAttribute> El argumento `name` especifica el nombre del atributo; `content` especifica el contenido del atributo.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Crear un elemento con un atributo  
 El código siguiente muestra un elemento que contiene un atributo que se utilizan literales XML en Visual Basic:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Construcción funcional de los atributos  
 Puede construir <xref:System.Xml.Linq.XAttribute>en línea con la construcción de los objetos <xref:System.Xml.Linq.XElement>objetos, como sigue:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute>  
  
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
 Existen algunas diferencias entre los atributos y los elementos. <xref:System.Xml.Linq.XAttribute>objetos no son nodos en el árbol XML.</xref:System.Xml.Linq.XAttribute> Son pares de nombre y valor asociados a un elemento XML. A diferencia de Document Object Model (DOM), esto refleja de manera más precisa la estructura del código XML. Aunque <xref:System.Xml.Linq.XAttribute>objetos no son realmente nodos en el árbol XML, trabajar con <xref:System.Xml.Linq.XAttribute>es muy similar a trabajar con objetos <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute>  
  
 Esta distinción solo resulta de importancia para los desarrolladores que escriban código que trabaje con árboles XML en el nivel de nodo. A muchos desarrolladores no les afecta esta distinción.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
