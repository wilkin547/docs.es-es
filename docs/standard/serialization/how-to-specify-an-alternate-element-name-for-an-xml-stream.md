---
title: Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML
description: Aprenda a crear una secuencia XML con un nombre de elemento alternativo, por ejemplo, para los servicios Web XML que requieran la misma información con ligeras diferencias.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: d7e482ee6e1e1a7318ab05766508537d4b87789e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289595"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a>Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML
  
Utilizando<xref:System.Xml.Serialization.XmlSerializer>, se puede generar más de una secuencia XML con el mismo conjunto de clases. Puede que desee proceder de esta forma ya que dos servicios Web XML diferentes requieren la misma información básica, con solo ligeras diferencias. Por ejemplo, imagine dos servicios Web XML que procesan órdenes para los libros y así ambos requieren los números de ISBN. Un servicio usa la etiqueta \<ISBN> mientras el segundo usa la etiqueta \<BookID>. Tiene una clase denominada `Book` que contiene un campo denominado `ISBN`. Cuando se serializa una instancia de la clase `Book`, utilizará, de forma predeterminada, el nombre de miembro (ISBN) como el nombre de elemento de etiqueta. Para el primer servicio Web XML, esto es como esperado. Pero para enviar la secuencia XML al segundo servicio Web XML, debe invalidar la serialización para que el nombre de elemento de la etiqueta sea `BookID`.  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a>Para crear una secuencia XML con un nombre de elemento alternativo  
  
1. Cree una instancia de la clase <xref:System.Xml.Serialization.XmlElementAttribute>.  
  
2. Establece el <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> de <xref:System.Xml.Serialization.XmlElementAttribute> a "BookID".  
  
3. Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributes>.  
  
4. Agregue el objeto `XmlElementAttribute` a la colección a la que ha accedido mediante la propiedad <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> de <xref:System.Xml.Serialization.XmlAttributes> .  
  
5. Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributeOverrides>.  
  
6. Agregue `XmlAttributes` a <xref:System.Xml.Serialization.XmlAttributeOverrides>, pasando el tipo del objeto para invalidarlo y el nombre de miembro invalidado.  
  
7. Cree una instancia de la clase `XmlSerializer` con `XmlAttributeOverrides`.  
  
8. Cree una instancia de la clase `Book` y serialice o deserialícela.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Public Function SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public void SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 La secuencia XML puede parecerse a lo siguiente.  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserialización de un objeto](how-to-deserialize-an-object.md)
