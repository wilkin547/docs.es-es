---
title: "Compilación de esquema XmlSchemaCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a>Compilación de esquema XmlSchemaCollection
El **XmlSchemaCollection** es una caché o una biblioteca donde se pueden almacenar y validar esquemas de lenguaje (XSD) de definición de datos XML reducidos (XDR) y el esquema XML. **XmlSchemaCollection** mejora el rendimiento al almacenar en caché esquemas en memoria en lugar de obtener acceso a ellos desde un archivo o dirección URL.  
  
> [!NOTE]
>  Aunque la **XmlSchemaCollection** clase almacena tanto esquemas XDR como XML, cualquier método y propiedad que acepte o devuelva un **XmlSchema** objeto sólo admitirá esquemas XML.  
  
> [!IMPORTANT]
>  La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>. Para obtener más información sobre la <xref:System.Xml.Schema.XmlSchemaSet> , vea clase [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Agregar esquemas a la colección  
 Los esquemas se cargan a la colección utilizando la **agregar** método **XmlSchemaCollection**, momento en el que el esquema está asociado a un URI de espacio de nombres. Para los esquemas XML, el URI de espacio de nombres es, por lo general, el espacio de nombres de destino para el esquema. Para los esquemas XDR, es el espacio de nombres especificado cuando el esquema se agregó a la colección.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Comprobar un esquema en la colección  
 También puede comprobar si un esquema se encuentra en la colección utilizando la **Contains** método. El **Contains** método puede toma una **XmlSchema** objeto (sólo para esquemas XML) o una cadena que representa el URI de espacio de nombres asociado al esquema (para esquemas XML y XDR).  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Recuperar un esquema de la colección  
 Puede recuperar un esquema de la colección mediante la **elemento** propiedad. El **elemento** propiedad toma una cadena que representa el espacio de nombres URI asociado con el esquema, por lo general su destino espacio de nombres y devuelve un **XmlSchema** objeto. El **elemento** propiedad solo se aplica a los esquemas XML. El valor devuelto siempre es una referencia nula para los esquemas XDR porque carecen de un modelo de objetos disponible.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Validar documentos XML mediante XmlSchemaCollection  
 Puede validar un documento de instancia XML con un **XmlSchemaCollection** mediante la creación de la **XmlSchemaCollection** objeto, agrega los esquemas a la colección y establecer el **esquemas**  propiedad en el **XmlValidatingReader** asignar creado **XmlSchemaCollection** a la **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Mejorar el rendimiento  
 Se recomienda, si va a validar más de un documento con respecto al mismo esquema, que usa el **XmlSchemaCollection** porque proporciona un mejor rendimiento al almacenar en caché esquemas en memoria.  
  
 En el ejemplo de código siguiente se crea el **XmlSchemaCollection** objeto, se agregan esquemas a la colección y se establece la **esquemas** propiedad.  
  
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
 [Validación de XDR con XmlSchemaCollection](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [XML de validación de esquema (XSD) con XmlSchemaCollection](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
