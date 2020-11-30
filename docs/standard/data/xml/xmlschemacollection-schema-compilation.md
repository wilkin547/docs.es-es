---
title: Compilación de esquema XmlSchemaCollection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: bb17cd4802f97bb012ae8214b3c4095ed516d367
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721923"
---
# <a name="xmlschemacollection-schema-compilation"></a>Compilación de esquema XmlSchemaCollection

**XmlSchemaCollection** es una caché o una biblioteca en la que se pueden almacenar y validar esquemas de esquema reducido de datos XML (XDR) y de lenguaje de definición de esquema XML (XSD). **XmlSchemaCollection** mejora el rendimiento al almacenar en memoria caché los esquemas, en lugar obtener acceso a ellos desde un archivo o dirección URL.  
  
> [!NOTE]
> Aunque la clase **XmlSchemaCollection** almacena tanto esquemas XDR como XML, cualquier método y propiedad que acepte o devuelva un objeto **XmlSchema** solo admitirá esquemas XML.  
  
> [!IMPORTANT]
> La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>. Para más información sobre la clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [XmlSchemaSet para compilación de esquemas](xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Agregar esquemas a la colección  

 Los esquemas se cargan en la colección mediante el método **Add** de **XmlSchemaCollection**. En ese momento, el esquema se asocia con un identificador URI de espacio de nombres. Para los esquemas XML, el URI de espacio de nombres es, por lo general, el espacio de nombres de destino para el esquema. Para los esquemas XDR, es el espacio de nombres especificado cuando el esquema se agregó a la colección.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Comprobar un esquema en la colección  

 Puede comprobar si un esquema se encuentra en la colección con el método **Contains**, que acepta un objeto **XmlSchema** (solo para esquemas XML) o una cadena que representa el identificador URI del espacio de nombres asociado al esquema (para esquemas XML y XDR).  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Recuperar un esquema de la colección  

 Puede recuperar un esquema de la colección mediante la propiedad **Item**, que acepta una cadena que representa el identificador URI de espacio de nombres asociado al esquema (por lo general, su espacio de nombres de destino) y devuelve un objeto **XmlSchema**. La propiedad **Item** se aplica solo a esquemas XML. El valor devuelto siempre es una referencia nula para los esquemas XDR porque carecen de un modelo de objetos disponible.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Validar documentos XML mediante XmlSchemaCollection  

 Puede validar un documento XML de instancia con **XmlSchemaCollection** si crea el objeto **XmlSchemaCollection**, agrega los esquemas a la colección y establece el valor de la propiedad **Schemas** en el **XmlValidatingReader** de modo que se le asigne el objeto **XmlSchemaCollection** creado a **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Mejorar el rendimiento  

 Si va a validar más de un documento con respecto al mismo esquema, es recomendable utilizar **XmlSchemaCollection**, ya que proporciona un mayor rendimiento al almacenar en memoria caché los esquemas.  
  
 En el ejemplo de código siguiente se crea el objeto **XmlSchemaCollection**, se agregan esquemas a la colección y se establece el valor de la propiedad **Schemas**.  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a>Vea también

- [Validación de XDR con XmlSchemaCollection](xdr-validation-with-xmlschemacollection.md)
- [Validación de esquemas XML (XSD) con XmlSchemaCollection](xml-schema-xsd-validation-with-xmlschemacollection.md)
