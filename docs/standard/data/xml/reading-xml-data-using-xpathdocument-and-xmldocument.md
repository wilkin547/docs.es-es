---
title: Lectura de datos XML con XPathDocument y XmlDocument
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
ms.openlocfilehash: 87ae96944f9a9f2bbcefb54c343f429c75c3022d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710393"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a>Lectura de datos XML con XPathDocument y XmlDocument
Existen dos formas de leer un documento XML en el espacio de nombres <xref:System.Xml.XPath?displayProperty=nameWithType>. La primera consiste en leer un documento XML utilizando la clase de solo lectura <xref:System.Xml.XPath.XPathDocument>, y la segunda en leer un documento XML utilizando la clase <xref:System.Xml.XmlDocument> editable en el espacio de nombres <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a>Lectura de documentos XML con la clase XPathDocument  
 La clase <xref:System.Xml.XPath.XPathDocument> proporciona una representación en memoria rápida y de solo lectura de un documento XML utilizando el modelo de datos XPath. Las instancias de la clase <xref:System.Xml.XPath.XPathDocument> se crean utilizando uno de sus seis constructores. Estos constructores permiten leer un documento XML utilizando el objeto <xref:System.IO.Stream>, <xref:System.IO.TextReader> o <xref:System.Xml.XmlReader>, así como la ruta `string` a un archivo XML.  
  
 En el siguiente ejemplo se ilustra el uso del constructor <xref:System.Xml.XPath.XPathDocument> de la clase `string` para leer un documento XML.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a>Lectura de documentos XML con la clase XmlDocument  
 La clase <xref:System.Xml.XmlDocument> es una representación en memoria editable de un documento XML que implementa la parte principal del nivel 1 del modelo de objetos de documento (DOM) y el nivel 2 de la parte principal del DOM del WC3. Las instancias de la clase <xref:System.Xml.XmlDocument> se crean utilizando uno de sus tres constructores. Puede crear un objeto <xref:System.Xml.XmlDocument> nuevo y vacío llamando al constructor de la clase <xref:System.Xml.XmlDocument> sin ningún parámetro. Después de llamar al constructor, utilice el método <xref:System.Xml.XmlDocument.Load%2A> para cargar datos XML en el nuevo objeto <xref:System.Xml.XmlDocument> desde un objeto <xref:System.IO.Stream>, <xref:System.IO.TextReader> o <xref:System.Xml.XmlReader>, así como la ruta `string` a un archivo XML.  
  
 En el siguiente ejemplo se ilustra el uso del constructor de clase <xref:System.Xml.XmlDocument> sin ningún parámetro y el método <xref:System.Xml.XmlDocument.Load%2A> para leer un documento XML.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a>Determinación de la codificación de un documento XML  
 Se puede utilizar un objeto <xref:System.Xml.XmlReader> para leer un documento XML y para crear los objetos <xref:System.Xml.XPath.XPathDocument> y <xref:System.Xml.XmlDocument>, tal y como se ha mostrado en las secciones anteriores. Sin embargo, un objeto <xref:System.Xml.XmlReader> puede leer datos que no estén codificados y, como resultado, no proporciona ninguna información de codificación.  
  
 La clase <xref:System.Xml.XmlTextReader> hereda de la clase <xref:System.Xml.XmlReader>, proporciona información de codificación utilizando su propiedad <xref:System.Xml.XmlTextReader.Encoding%2A> y se puede utilizar para crear un objeto <xref:System.Xml.XPath.XPathDocument> o un objeto <xref:System.Xml.XmlDocument>.  
  
 Para obtener más información sobre la información de codificación que proporciona la clase <xref:System.Xml.XmlTextReader>, vea la propiedad <xref:System.Xml.XmlTextReader.Encoding%2A> en la documentación de referencia de la clase <xref:System.Xml.XmlTextReader>.  
  
## <a name="creating-xpathnavigator-objects"></a>Creación de objetos XPathNavigator  
 Después de haber leído un documento XML en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>, puede crear un objeto <xref:System.Xml.XPath.XPathNavigator> para seleccionar, evaluar y navegar por los datos XML subyacentes, y en algunos casos, editarlos.  
  
 Las clases <xref:System.Xml.XPath.XPathDocument> y <xref:System.Xml.XmlDocument>, además de la clase <xref:System.Xml.XmlNode>, implementan la interfaz <xref:System.Xml.XPath.IXPathNavigable> del espacio de nombres <xref:System.Xml.XPath?displayProperty=nameWithType>. Como resultado, las tres clases proporcionan un método <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> que devuelve un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a>Edición de documentos XML con la clase XPathNavigator  
 Además de seleccionar, evaluar y navegar por los datos XML, la clase <xref:System.Xml.XPath.XPathNavigator> se puede utilizar para editar un documento XML en algunos casos, basándose en el objeto que lo ha creado.  
  
 La clase <xref:System.Xml.XPath.XPathDocument> es de solo lectura mientras que la clase <xref:System.Xml.XmlDocument> se pueda editar y, como resultado, los objetos <xref:System.Xml.XPath.XPathNavigator> creados a partir de un objeto <xref:System.Xml.XPath.XPathDocument> no se pueden utilizar para modificar un documento XML, mientras que los objetos <xref:System.Xml.XmlDocument> sí pueden. Debería utilizarse la clase <xref:System.Xml.XPath.XPathDocument> para leer solo un documento XML. En aquellos casos en los que necesite editar un documento XML o necesite acceso a la funcionalidad adicional que proporciona la clase <xref:System.Xml.XmlDocument> como, por ejemplo, el control de eventos, se debería utilizar la clase <xref:System.Xml.XmlDocument>.  
  
 La propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> especifica si un objeto <xref:System.Xml.XPath.XPathNavigator> puede editar datos XML.  
  
 En la tabla siguiente se describe el valor de la propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> de cada clase.  
  
|Implementación de <xref:System.Xml.XPath.IXPathNavigable>|Valor de <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Acceso a datos XML con XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [Edición de datos XML con XPathNavigator](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
- [Validación de esquemas con XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
