---
title: Opciones de procesamiento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
ms.openlocfilehash: 544c3467f46f5bebf79cb95906faeca7926c3824
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291427"
---
# <a name="xml-processing-options"></a>Opciones de procesamiento XML
Consulte las tablas siguientes para obtener una lista de tecnologías de Microsoft que puede usar para procesar los datos XML.  
  
## <a name="net-framework-options"></a>Opciones de .NET Framework  
  
|**Opción**|**Tipo de procesamiento**|**Descripción**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) <br/> [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br />(Espacio de nombres <xref:System.Xml.Linq>)|En memoria|- Basado en la tecnología Language Integrated Query (LINQ) de .NET Framework.<br />- Proporciona una experiencia de consulta similar a SQL para objetos, datos relacionales y datos XML.<br />- Proporciona funcionalidades intuitivas de creación y transformación de documentos.<br />- Use esta opción si va a escribir código nuevo.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Basado en streaming|- Proporciona un modo rápido, solo hacia delante y sin almacenamiento en caché de acceso a los datos XML.<br />- Puede crear objetos mediante el método <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> y especificar el conjunto de características para habilitar en el objeto mediante la clase <xref:System.Xml.XmlReaderSettings>.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Basado en streaming|- Proporciona un modo rápido, solo hacia delante y sin almacenamiento en caché para generar los datos XML.<br />- Puede crear objetos mediante el método <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> y especificar el conjunto de características para habilitar en el objeto mediante la clase <xref:System.Xml.XmlWriterSettings>.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|En memoria|- Implementa el [nivel 1 principal del Modelo de objetos de documento (DOM) del W3C](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) y las recomendaciones [principales del nivel 2 del DOM](https://www.w3.org/TR/DOM-Level-2-Core/).<br />- Puede crear, insertar, quitar y modificar los nodos mediante métodos y propiedades basándose en modelos DOM familiares.<br />- Use esta opción si va a modificar el código existente que usa el DOM del W3C.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|En memoria|- Ofrece varias opciones de edición y navegación mediante un modelo de cursores.<br />- Los documentos XML pueden estar contenidos en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.<br />- Proporciona un excelente rendimiento para el procesamiento de solo lectura de XML.<br />- Use esta opción si va a modificar el código existente con consultas XPath o transformaciones XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|En memoria|- Proporciona opciones para transformar los datos XML mediante transformaciones XSL.<br />- El [compilador XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md) permite hacer referencia a las transformaciones precompiladas de la aplicación.|  
  
## <a name="win32-and-com-based-options"></a>Opciones basadas en Win32 y en COM  
  
|**Opción**|**Descripción**|  
|----------------|---------------------|  
|[XmlLite](https://docs.microsoft.com/previous-versions/windows/desktop/ms752872(v=vs.85))|- Analizador XML rápido, seguro, sin almacenamiento en caché y de solo avance que permite compilar aplicaciones XML de alto rendimiento.<br />- Funciona con cualquier lenguaje capaz de usar bibliotecas de vínculos dinámicos (DLL), aunque se recomienda usar C++.|  
|[MSXML](https://docs.microsoft.com/previous-versions/windows/desktop/ms763742(v=vs.85))|- Tecnología basada en COM usada para procesar XML y que se incluye con el sistema operativo Windows.<br />- Ofrece una implementación nativa de DOM, que es compatible con XPath y XSLT.<br />- Contiene el analizador basado en eventos SAX2.|  
  
## <a name="see-also"></a>Vea también

- [Procesamiento de datos XML con el modelo DOM](process-xml-data-using-the-dom-model.md)
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Compilador XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md)
