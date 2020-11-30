---
title: Compatibilidad de tipos en las clases System.Xml
ms.date: 03/30/2017
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
ms.openlocfilehash: 6fe55c64bc9bd17d5416eebf77060f2be27b81bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675664"
---
# <a name="type-support-in-the-systemxml-classes"></a>Compatibilidad de tipos en las clases System.Xml

En la versión 2.0 de .NET Framework, se han mejorado las clases XML principales para incluir características de compatibilidad de tipos. Las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> tienen características de compatibilidad de tipos, incluyendo la capacidad de realizar conversiones entre tipos de esquemas XML y tipos de Common Language Runtime (CLR).  
  
 En la versión 2.0 de .NET Framework, se han mejorado las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> para incluir características de compatibilidad de tipos.  
  
- Cada una de las clases <xref:System.Xml.XmlReader> y <xref:System.Xml.XPath.XPathNavigator> incluye una propiedad **SchemaInfo** que devuelve la información de esquema en un nodo.  
  
- **ReadContentAs** y **ReadElementContentAs** y los métodos de la clase <xref:System.Xml.XmlReader> leen un valor de texto y lo convierten en un valor CLR en una sola llamada de método.  
  
- El método <xref:System.Xml.XmlWriter.WriteValue%2A> de la clase <xref:System.Xml.XmlWriter> convierte un tipo CLR en un tipo de esquema XML cuando escribe XML.  
  
- Las propiedades **ValueAs** y <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> devuelven un valor de nodo y lo convierten en un valor CLR en una sola llamada de método.  
  
> [!NOTE]
> En la versión 1.0 de .NET Framework, se necesitaba la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.  
  
## <a name="in-this-section"></a>En esta sección  

 [Asignación de tipos de datos XML a tipos CLR](mapping-xml-data-types-to-clr-types.md)  
 Describe las asignaciones predeterminadas de tipos de datos XML en tipos CLR.  
  
 [Notas de implementación de la compatibilidad con tipos XML](xml-type-support-implementation-notes.md)  
 Explica algunos de los detalles de la implementación de la compatibilidad de tipos.  
  
 [Conversión de tipos de datos XML](conversion-of-xml-data-types.md)  
 Describe cómo utilizar la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Acceso a datos XML fuertemente tipados utilizando XPathNavigator](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
