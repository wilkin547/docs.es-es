---
title: Guardar y escribir un documento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
ms.openlocfilehash: 14497bb5b027209c4707eab9bcf1b60f85740dfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697563"
---
# <a name="saving-and-writing-a-document"></a>Guardar y escribir un documento

Cuando cargue y guarde un <xref:System.Xml.XmlDocument>, el documento guardado puede ser diferente al original de varias formas:  
  
- Si la propiedad <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> se establece en `true` antes de llamar al método <xref:System.Xml.XmlDocument.Save%2A>, en el resultado se conserva el espacio en blanco del documento; sin embargo, si la propiedad es `false`, <xref:System.Xml.XmlDocument>, se aplica sangría automáticamente al resultado.  
  
- Todos los espacios en blanco entre los atributos se reducen a un carácter de un solo espacio.  
  
- Se cambia el espacio en blanco entre los elementos. Se conserva el espacio blanco importante, pero no se conserva el poco importante. No obstante, cuando se guarda el documento, se usa el modo <xref:System.Xml.XmlTextWriter> **Sangría** de manera predeterminada para imprimir con claridad el resultado con el fin de que sea más legible.  
  
- De manera predeterminada, el carácter de la comilla que se utiliza delante y detrás de los valores de los atributos se cambia por la comilla doble. Puede utilizar la propiedad <xref:System.Xml.XmlTextReader.QuoteChar%2A> en <xref:System.Xml.XmlTextWriter>para establecer el carácter de la comilla como doble o simple.  
  
- De manera predeterminada, se expanden las entidades de caracteres numéricos como `{`.  
  
- No se conserva la marca de orden de bytes del documento de entrada. UCS-2 se guarda como UTF-8 a menos que cree explícitamente una declaración XML en la que se especifique otra codificación.  
  
- Si desea escribir <xref:System.Xml.XmlDocument> en un archivo o una secuencia, el resultado escrito es el mismo que el contenido del documento. Es decir, la declaración <xref:System.Xml.XmlDeclaration> solo se escribe si hay alguna en el documento y la codificación que se utiliza al escribir el documento es la misma que la del nodo de la declaración.  
  
## <a name="writing-an-xmldeclaration"></a>Escribir una declaración XmlDeclaration  

 Los miembros <xref:System.Xml.XmlDocument> y <xref:System.Xml.XmlDeclaration> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A> y <xref:System.Xml.XmlNode.WriteTo%2A>, además de los métodos <xref:System.Xml.XmlDocument> de <xref:System.Xml.XmlDocument.Save%2A> y <xref:System.Xml.XmlDocument.WriteContentTo%2A>, crean una declaración XML.  
  
 Para las propiedades <xref:System.Xml.XmlDocument> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, y los métodos <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A> y <xref:System.Xml.XmlDocument.WriteContentTo%2A>, la codificación escrita en la declaración XML se obtiene del nodo <xref:System.Xml.XmlDeclaration>. Si no existe ningún nodo <xref:System.Xml.XmlDeclaration>, <xref:System.Xml.XmlDeclaration> no se escribe. Si no hay codificación en el nodo <xref:System.Xml.XmlDeclaration>, la codificación no se escribe en la declaración XML.  
  
 Los métodos <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> y <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> siempre escriben una declaración <xref:System.Xml.XmlDeclaration>. Estos métodos toman la codificación del sistema de escritura que está escribiendo. Es decir, el valor de codificación en el sistema de escritura invalida la codificación en el documento y en la declaración <xref:System.Xml.XmlDeclaration>. Por ejemplo, el siguiente código no escribe una codificación en la declaración XML que se encuentra en el archivo de salida `out.xml`.  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 Para el método <xref:System.Xml.XmlDocument.Save%2A>, la declaración XML se escribe utilizando el método <xref:System.Xml.XmlWriter.WriteStartDocument%2A> en la clase <xref:System.Xml.XmlWriter>. Por lo tanto, al sobrescribir el método <xref:System.Xml.XmlWriter.WriteStartDocument%2A>, cambia la forma de escribir el principio del documento.  
  
 Para los miembros <xref:System.Xml.XmlDeclaration> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A> y <xref:System.Xml.XmlNode.InnerXml%2A>, si no se establece la propiedad <xref:System.Xml.XmlDeclaration.Encoding%2A>, no se escribe la codificación. De lo contrario, la codificación escrita en la declaración XML es la misma que la que se encuentra en la propiedad <xref:System.Xml.XmlDeclaration.Encoding%2A>.  
  
## <a name="writing-document-content-using-the-outerxml-property"></a>Escribir el contenido de un documento con la propiedad OuterXml  

 La propiedad <xref:System.Xml.XmlNode.OuterXml%2A> es una extensión de Microsoft de los estándares del Modelo de objetos de documento (DOM) XML del W3C (World Wide Web Consortium). La propiedad <xref:System.Xml.XmlNode.OuterXml%2A> se utiliza para obtener el marcado de todo el documento XML o tan solo el de un nodo y sus nodos secundarios. <xref:System.Xml.XmlNode.OuterXml%2A>devuelve el marcado que representa el nodo en concreto y todos sus nodos secundarios.  
  
 El siguiente ejemplo de código muestra cómo guardar un documento por completo como una cadena.  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 El siguiente ejemplo de código muestra cómo guardar únicamente el elemento de documento.  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 Por el contrario, puede utilizar la propiedad <xref:System.Xml.XmlNode.InnerText%2A> si desea el contenido de los nodos secundarios.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
