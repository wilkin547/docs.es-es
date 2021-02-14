---
description: 'Más información acerca de: Uso de System.Xml'
title: Uso de System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 51886c07f0b68bb329c258daa93e809d94839341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641855"
---
# <a name="systemxml-usage"></a>Uso de System.Xml

En esta sección se habla sobre el uso de varios tipos que residen en espacios de nombres <xref:System.Xml?displayProperty=nameWithType> que se pueden usar para representar datos XML.

 ❌ NO utilice <xref:System.Xml.XmlNode> ni <xref:System.Xml.XmlDocument> para representar datos XML. Favorezca el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>o subtipos de <xref:System.Xml.Linq.XNode> en su lugar. `XmlNode` y `XmlDocument` no se han diseñado para exponerse en las API públicas.

 ✔️ DEBE usar `XmlReader`, `IXPathNavigable`o subtipos de `XNode` como entrada o salida de miembros que aceptan o devuelven XML.

 Utilice estas abstracciones en lugar de `XmlDocument`, `XmlNode` o <xref:System.Xml.XPath.XPathDocument>, porque esto desacopla los métodos de las implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode`, `XmlReader` o <xref:System.Xml.XPath.XPathNavigator>.

 ❌ NO cree subclases `XmlDocument` si desea crear un tipo que represente una vista XML de un origen de datos o un modelo de objetos subyacente.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de uso](usage-guidelines.md)
