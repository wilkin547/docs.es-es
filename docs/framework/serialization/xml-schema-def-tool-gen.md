---
title: "C&#243;mo: Utilizar la herramienta de definici&#243;n de esquema XML para generar clases y documentos de esquema XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "generar clases XML con la herramienta de definición de esquema XML"
  - "generar documento de esquema XML con la herramienta de definición de esquema XML"
  - "definición de esquema XML (herramienta), uso para generar clases que cumplen con un esquema concreto"
  - "definición de esquema XML (herramienta), uso para generar un documento de esquema XML"
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Utilizar la herramienta de definici&#243;n de esquema XML para generar clases y documentos de esquema XML
La herramienta XML Schema Definition \(Xsd.exe\) le permite generar un esquema XML que describe una clase o generar la clase definida por un esquema XML.Los procedimientos siguientes muestran cómo realizar estas operaciones.  
  
### Para generar clases que cumplen con un esquema concreto  
  
1.  Abra un símbolo del sistema.  
  
2.  Pasar el esquema XML como un argumento a la herramienta XML Schema Definition, que crea un conjunto de clases con las que precisamente coinciden el Esquema XML, por ejemplo:  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     La herramienta solo puede procesar esquemas que hagan referencia a la especificación de World Wide Web Consortium XML del 16 de marzo de 2001.En otras palabras, el espacio de nombres del esquema XML debe ser "http:\/\/www.w3.org\/2001\/XMLSchema" como se muestra en el siguiente ejemplo.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  Modifique las clases con métodos, propiedades o campos, como sea necesario.Para obtener información acerca de modificar una clase con atributos vea [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md) y [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Es a menudo útil para examinar el esquema de la secuencia XML que se genera cuando se serializan las instancias de una clase \(o clases\).Por ejemplo, podría publicar su esquema para que otros lo utilicen o podría compararlo con un esquema con el que está intentando lograr la conformidad.  
  
#### Para generar un documento de esquema XML de un conjunto de clases  
  
1.  Compile la clase o clases en un archivo DLL.  
  
2.  Abra un símbolo del sistema.  
  
3.  Pasar el archivo DLL como un argumento a Xsd.exe, por ejemplo:  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     Se escribirá el esquema \(o esquemas\), comenzando con "schema0.xsd" del nombre.  
  
## Vea también  
 [Herramienta de definición de esquema XML y serialización XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)