---
description: 'Más información acerca de: Documentos y datos XML'
title: Documentos y datos XML
ms.date: 03/30/2017
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
ms.openlocfilehash: c2f64c218f2f6051f27087a98616b17e57583f75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713668"
---
# <a name="xml-documents-and-data"></a>Documentos y datos XML

.NET Framework proporciona un conjunto de clases completo e integrado que permiten crear, de forma sencilla, aplicaciones preparadas para XML. Las clases de los espacios de nombres siguientes admiten análisis y escritura XML, edición de datos XML en memoria, validación de datos y transformación XSLT.

- <xref:System.Xml>

- <xref:System.Xml.XPath>

- <xref:System.Xml.Xsl>

- <xref:System.Xml.Schema>

- <xref:System.Xml.Linq>

Para obtener una lista completa, busque "System.Xml" en el [explorador de API de .NET](../../../../api/index.md?term=system.xml).

Las clases de estos espacios de nombres admiten las recomendaciones del World Wide Web Consortium (W3C). Por ejemplo:

- La clase <xref:System.Xml.XmlDocument?displayProperty=nameWithType> implementa las recomendaciones de la [parte principal del nivel 1 de Document Object Model (DOM)](https://www.w3.org/TR/REC-DOM-Level-1/) y de la [parte principal del nivel 2 de DOM](https://www.w3.org/TR/DOM-Level-2-Core/) del W3C.

- Las clases <xref:System.Xml.XmlReader?displayProperty=nameWithType> y <xref:System.Xml.XmlWriter?displayProperty=nameWithType> admiten las recomendaciones del W3C sobre [XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) y los [espacios de nombres de XML](https://www.w3.org/TR/REC-xml-names/).

- Los esquemas de la clase <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> admiten las recomendaciones del W3C sobre [Esquema XML, parte 1: estructuras](https://www.w3.org/TR/xmlschema-1/) y en [Esquema XML, parte 2: tipos de datos](https://www.w3.org/TR/xmlschema-2/).

- Las clases del espacio de nombres <xref:System.Xml.Xsl?displayProperty=nameWithType> admiten transformaciones XSLT compatibles con las recomendaciones del W3C sobre [XSLT versión 1.0](https://www.w3.org/TR/xslt).

Las clases XML de .NET Framework proporcionan estas ventajas:

- **Productividad.** Gracias a [LINQ to XML (C#)](../../linq/linq-xml-overview.md) y [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md) resulta más sencillo programar con XML y proporciona una experiencia de consulta similar a SQL.

- **Extensibilidad.** Las clases XML en .NET Framework se pueden extender mediante el uso de clases base abstractas y métodos virtuales. Por ejemplo, puede crear una clase derivada de la clase <xref:System.Xml.XmlUrlResolver> que almacene el flujo caché en el disco local.

- **Arquitectura conectable.** .NET Framework proporciona una arquitectura en la que los componentes se pueden usar unos con otros y se puede hacer streaming de los datos entre componentes. Por ejemplo, un almacén de datos, como un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>, se puede transformar con la clase <xref:System.Xml.Xsl.XslCompiledTransform> y, posteriormente, se pueden hacer streaming de los resultados a otro almacén o devolverse como flujo desde un servicio web.

- **Rendimiento.** Para obtener un mejor rendimiento de la aplicación, algunas de las clases XML de .NET Framework admiten un modelo basado en streaming con las características siguientes:

  - Almacenamiento en caché mínimo para el análisis de modelos de incorporación de cambios solo hacia delante (<xref:System.Xml.XmlReader>).

  - Validación solo hacia delante con (<xref:System.Xml.XmlReader>).

  - Navegación al estilo de cursores que reduce la creación de nodos a un único nodo virtual, a la vez que proporciona acceso aleatorio al documento (<xref:System.Xml.XPath.XPathNavigator>).

  Para obtener un mejor rendimiento cuando se requiera un procesamiento XSLT, puede usar la clase <xref:System.Xml.XPath.XPathDocument>, que es un almacén optimizado de solo lectura para consultas XPath diseñadas para funcionar, de forma eficiente, con la clase <xref:System.Xml.Xsl.XslCompiledTransform>.

- **Integración con ADO.NET.** Las clases XML y [ADO.NET](../../../framework/data/adonet/index.md) están estrechamente integradas para reunir datos relacionales y XML. La clase <xref:System.Data.DataSet> es una caché almacenada en memoria de datos devueltos desde una base de datos. La clase <xref:System.Data.DataSet> puede leer y escribir XML mediante las clases <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>, con el fin de almacenar su estructura de esquema relacional interna como esquemas XML (XSD) y para deducir la estructura de esquema de un documento XML.

## <a name="in-this-section"></a>En esta sección

En [Opciones de procesamiento XML](xml-processing-options.md) se describen las opciones para procesar datos XML.

En [Procesamiento de datos XML en memoria](processing-xml-data-in-memory.md) se describen los tres modelos para procesar datos XML en memoria: [LINQ to XML (C#)](../../linq/linq-xml-overview.md) y [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md), la clase <xref:System.Xml.XmlDocument> (basada en Document Object Model del W3C) y la clase <xref:System.Xml.XPath.XPathDocument> (basada en el modelo de datos XPath).

[Transformaciones XSLT](xslt-transformations.md)\
Describe cómo utilizar el procesador XSLT.

[Modelo de objetos de esquema XML (SOM)](xml-schema-object-model-som.md)\
Describe las clases que se usan para crear y tratar esquemas XML (XSD) mediante una clase <xref:System.Xml.Schema.XmlSchema> que carga y modifica un esquema.

[Integración de XML con datos relacionales y ADO.NET](xml-integration-with-relational-data-and-adonet.md)\
Describe cómo habilita .NET Framework el acceso sincrónico en tiempo real a las representaciones relacional y jerárquica de los datos mediante los objetos <xref:System.Data.DataSet> y <xref:System.Xml.XmlDataDocument>.

[Administración de espacios de nombres en un documento XML](managing-namespaces-in-an-xml-document.md)\
Describe cómo se usa la clase <xref:System.Xml.XmlNamespaceManager> para almacenar y mantener la información sobre espacios de nombres.

[Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md)\
Describe cómo se asignan los tipos de datos XML a los tipos CLR, cómo se convierten los tipos de datos XML y otras características de compatibilidad de tipos de las clases <xref:System.Xml>.

## <a name="related-sections"></a>Secciones relacionadas

[ADO.NET](../../../framework/data/adonet/index.md)\
Proporciona información sobre cómo acceder a los datos mediante ADO.NET.

[Seguridad](../../security/index.md)\
Ofrece información general sobre todo el sistema de seguridad de .NET Framework.
