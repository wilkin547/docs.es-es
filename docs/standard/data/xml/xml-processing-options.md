---
title: Opciones de procesamiento XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>Opciones de procesamiento XML
Consulte las tablas siguientes para obtener una lista de tecnologías de Microsoft que puede usar para procesar los datos XML.  
  
## <a name="net-framework-options"></a>Opciones de .NET Framework  
  
|**Opción**|**Tipo de procesamiento**|**Descripción**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />(Espacio de nombres <xref:System.Xml.Linq>)|En memoria|-Se basa en la tecnología Integrated Query (LINQ).<br />: Proporciona la experiencia de consulta similar a SQL para objetos, datos relacionales y datos XML.<br />-Proporciona intuitivas funciones de creación y transformación de documentos.<br />: Use esta opción si va a escribir código nuevo.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Basado en streaming|: Proporciona un modo rápido, sin almacenamiento en caché de solo avance para acceder a los datos XML.<br />-Puede crear objetos mediante el uso de la <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> (método) y especificar el conjunto de características para habilitar en el objeto mediante la <xref:System.Xml.XmlReaderSettings> clase.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Basado en streaming|: Proporciona un modo rápido, sin almacenamiento en caché de solo avance para generar datos XML.<br />-Puede crear objetos mediante el uso de la <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> (método) y especificar el conjunto de características para habilitar en el objeto mediante la <xref:System.Xml.XmlWriterSettings> clase.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|En memoria|-Implementa el [nivel 1 principal del modelo de objetos de documento (DOM) de W3C](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) y [nivel 2 principal del DOM](http://www.w3.org/TR/DOM-Level-2-Core/) recomendaciones.<br />-Se puede crear, insertar, quitar y modificar nodos mediante el uso de métodos y propiedades basados en modelos DOM familiares.<br />: Use esta opción si va a modificar el código existente que usa el DOM del W3C.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|En memoria|-Ofrece varias opciones de edición y capacidades de navegación utilizando un modelo de cursor.<br />-Documentos XML pueden incluirse en un <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> objeto.<br />: Proporciona un excelente rendimiento para el procesamiento de solo lectura de XML.<br />: Use esta opción si va a modificar el código existente con consultas XPath o transformaciones XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|En memoria|: Proporciona opciones para transformar los datos XML mediante transformaciones XSL.<br />-El [compilador XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) permite que se hace referencia a compila previamente las transformaciones en la aplicación.|  
  
## <a name="win32-and-com-based-options"></a>Opciones basadas en Win32 y en COM  
  
|**Opción**|**Descripción**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-Una rápida y segura, sin almacenamiento en caché, es compilar alto rendimiento del analizador XML de solo avance que le ayuda a aplicaciones XML.<br />-Funciona con cualquier lenguaje que puede utilizar bibliotecas de vínculos dinámicos (DLL); se recomienda utilizar C++.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|COM basada en tecnología de procesamiento de XML que se incluye con el sistema operativo Windows.<br />: Proporciona una implementación nativa de DOM, compatible con XPath y XSLT.<br />-Contiene el analizador basado en eventos SAX2.|  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de datos XML con el modelo DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Compilador XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
