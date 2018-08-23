---
title: Serialización de SOAP y XML
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: ca3b31c1d60770a6b9db5e92275d9840036ee0b0
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "42753913"
---
# <a name="xml-and-soap-serialization"></a>Serialización de SOAP y XML

La serialización XML convierte (serializa) las propiedades y campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML (XSD). La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.

Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma. Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets. A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.

La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP. SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.

Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>. Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.

## <a name="in-this-section"></a>En esta sección

[Introducción a la serialización XML](introducing-xml-serialization.md)  
Proporciona una definición general de serialización, particularmente la serialización XML.

[Cómo: Serializar un objeto](how-to-serialize-an-object.md)  
Proporciona las instrucciones paso a paso para serializar un objeto.

[Cómo: Deserializar un objeto](how-to-deserialize-an-object.md)  
Proporciona las instrucciones paso a paso para deserializar un objeto

[Ejemplos de serialización XML](examples-of-xml-serialization.md)  
Proporciona ejemplos que muestran los fundamentos de serialización XML.

[Herramienta de definición de esquema XML y serialización XML](the-xml-schema-definition-tool-and-xml-serialization.md)  
Describe cómo utilizar la herramienta XML Schema Definition para crear clases que se adhieren a un esquema del lenguaje de definición de esquemas XML (XSD) determinado o que generan un esquema XML de un archivo .dll.

[Controlar la serialización XML mediante atributos](controlling-xml-serialization-using-attributes.md)  
Describe cómo controlar la serialización utilizando los atributos.

[Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md)  
Hace una lista de los atributos que se utilizan para controlar la serialización XML.

[Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
Presenta un escenario avanzado que muestra cómo generar varias secuencias XML invalidando la serialización.

[Cómo: Controlar la serialización de clases derivadas](how-to-control-serialization-of-derived-classes.md)  
Ofrece un ejemplo que muestra cómo controlar la serialización de clases derivadas.

[Cómo: Calificar el elemento XML y los nombres del atributo XML](how-to-qualify-xml-element-and-xml-attribute-names.md)  
Describe cómo definir y controlar la manera en la que los espacios de nombres XML se utilizan en la secuencia XML.

[Serialización XML con servicios web XML](xml-serialization-with-xml-web-services.md)  
Explica cómo la serialización XML se utiliza en servicios Web XML.

[Cómo: Serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
Describe cómo utilizar el <xref:System.Xml.Serialization.XmlSerializer> clase para crear secuencias XML SOAP codificadas que se ajustan a la sección 5 del documento de World Wide Web Consortium (W3C) [protocolo de acceso de objeto Simple (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).

[Cómo: Invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md)  
Describe el proceso para invalidar serialización XML de objetos como mensajes SOAP.

[Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md)  
Hace una lista de los atributos que se utilizan para controlar la serialización codificada SOAP.

[Elemento \<system.xml.serialization>](system-xml-serialization-element.md)  
El elemento de configuración de nivel superior para controlar la serialización XML.

[Elemento \<dateTimeSerialization>](datetimeserialization-element.md)  
Controla el modo de la serialización de los objetos <xref:System.DateTime>.

[Elemento \<schemaImporterExtensions>](schemaimporterextensions-element.md)  
Contiene tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.

[\<Agregar > elemento para \<schemaImporterExtensions >](add-element-for-schemaimporterextensions.md)  
Agrega tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.

## <a name="related-sections"></a>Secciones relacionadas

[Tecnologías de desarrollo avanzadas](https://msdn.microsoft.com/library/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
Proporciona vínculos para más información sobre tareas y técnicas de desarrollo sofisticadas de .NET Framework.

[Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)  
Proporciona los temas que describen y explican cómo programar los servicios Web XML utilizando ASP.NET.

## <a name="see-also"></a>Vea también

[Serialización binaria](binary-serialization.md)  