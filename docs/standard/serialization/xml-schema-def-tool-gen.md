---
title: Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 4c6996e2279693cf96c826741869d72007cf81cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249557"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML
La herramienta XML Schema Definition (Xsd.exe) le permite generar un esquema XML que describe una clase o generar la clase definida por un esquema XML. Los procedimientos siguientes muestran cómo realizar estas operaciones.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Para generar clases que cumplen con un esquema concreto  
  
1. Abra un símbolo del sistema.  
  
2. Pasar el esquema XML como un argumento a la herramienta XML Schema Definition, que crea un conjunto de clases con las que precisamente coinciden el Esquema XML, por ejemplo:  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     La herramienta solo puede procesar esquemas que hagan referencia a la especificación de World Wide Web Consortium XML del 16 de marzo de 2001. En otras palabras, el espaciohttp://www.w3.org/2001/XMLSchemade nombres de esquema XML debe ser " " como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. Modifique las clases con métodos, propiedades o campos, como sea necesario. Para más información sobre cómo modificar una clase con atributos, vea [Controlar la serialización XML mediante atributos](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) y [Atributos que controlan la serialización SOAP codificada](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Es a menudo útil para examinar el esquema de la secuencia XML que se genera cuando se serializan las instancias de una clase (o clases). Por ejemplo, podría publicar su esquema para que otros lo utilicen o podría compararlo con un esquema con el que está intentando lograr la conformidad.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Para generar un documento de esquema XML de un conjunto de clases  
  
1. Compile la clase o clases en un archivo DLL.  
  
2. Abra un símbolo del sistema.  
  
3. Pasar el archivo DLL como un argumento a Xsd.exe, por ejemplo:  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     Se escribirá el esquema (o esquemas), comenzando con "schema0.xsd" del nombre.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataSet>
- [Herramienta de definición de esquema XML y serialización XML](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [Introducir la serialización XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedimiento para serializar un objeto](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Procedimiento para deserializar un objeto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
