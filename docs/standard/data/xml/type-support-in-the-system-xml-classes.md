---
title: Compatibilidad de tipos en las clases System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a>Compatibilidad de tipos en las clases System.Xml
En la versión 2.0 de .NET Framework, se han mejorado las clases XML principales para incluir características de compatibilidad de tipos. Las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> tienen características de compatibilidad de tipos, incluyendo la capacidad de realizar conversiones entre tipos de esquemas XML y tipos de Common Language Runtime (CLR).  
  
 En la versión 2.0 de .NET Framework, se han mejorado las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> para incluir características de compatibilidad de tipos.  
  
-   El <xref:System.Xml.XmlReader> y <xref:System.Xml.XPath.XPathNavigator> clases cada incluyen un **SchemaInfo** propiedad que devuelve la información de esquema en un nodo.  
  
-   El **ReadContentAs** y **ReadElementContentAs** y métodos en la <xref:System.Xml.XmlReader> clase leer un valor de texto y convertirlo en un valor CLR en una única llamada al método.  
  
-   El método <xref:System.Xml.XmlWriter.WriteValue%2A> de la clase <xref:System.Xml.XmlWriter> convierte un tipo CLR en un tipo de esquema XML cuando escribe XML.  
  
-   El **ValueAs** y <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> propiedades en la <xref:System.Xml.XPath.XPathNavigator> clase devuelve un valor de nodo y lo convierten en un valor CLR en una única llamada al método.  
  
> [!NOTE]
>  En la versión 1.0 de .NET Framework, se necesitaba la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar tipos de datos XML a tipos CLR](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 Describe las asignaciones predeterminadas de tipos de datos XML en tipos CLR.  
  
 [Notas de implementación de compatibilidad de tipo XML](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 Explica algunos de los detalles de la implementación de la compatibilidad de tipos.  
  
 [Conversión de tipos de datos XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 Describe cómo utilizar la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Acceso a fuertemente tipados datos XML con XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
