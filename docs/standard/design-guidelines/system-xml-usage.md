---
title: Uso de System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 46282afa6548c731b04c40d8de91a1fed997c57c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677575"
---
# <a name="systemxml-usage"></a>Uso de System.Xml

En esta sección se habla sobre el uso de varios tipos que residen en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que se pueden usar para representar datos XML.

 ❌ No use <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar datos XML. Favorece el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable> , <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> o subtipos de <xref:System.Xml.Linq.XNode> en su lugar. `XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.

 ✔️ utilizan `XmlReader` `IXPathNavigable` subtipos, o `XNode` como entrada o salida de miembros que aceptan o devuelven XML.

 Utilice estas abstracciones en lugar de `XmlDocument` , `XmlNode` o <xref:System.Xml.XPath.XPathDocument> , ya que esto desacopla los métodos de las implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode` , `XmlReader` o <xref:System.Xml.XPath.XPathNavigator> .

 ❌ No cree subclases `XmlDocument` si desea crear un tipo que represente una vista XML de un origen de datos o un modelo de objetos subyacente.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de uso](usage-guidelines.md)
