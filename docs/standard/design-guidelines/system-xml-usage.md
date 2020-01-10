---
title: Uso de System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709041"
---
# <a name="systemxml-usage"></a>Uso de System.Xml
En esta sección se habla sobre el uso de varios tipos que residen en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que se pueden usar para representar datos XML.  
  
 **X DO NOT** usar <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar los datos XML. Favorecer el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>o subtipos de <xref:System.Xml.Linq.XNode> en su lugar. `XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.  
  
 **✓ DO** usar `XmlReader`, `IXPathNavigable`, o subtipos de `XNode` como entrada o salida de los miembros que aceptan o devuelven XML.  
  
 Utilice estas abstracciones en lugar de `XmlDocument`, `XmlNode`o <xref:System.Xml.XPath.XPathDocument>, porque esto desacopla los métodos de las implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode`, `XmlReader`o <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** subclase `XmlDocument` si desea crear un tipo que representa una vista XML de un origen de datos o el modelo de objeto subyacente.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
