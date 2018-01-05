---
title: Uso de System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 956cc0ba37c06b39ed32500209e1af47d4035c84
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="systemxml-usage"></a>Uso de System.Xml
Esta sección trata sobre el uso de varios tipos que residen en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que pueden usarse para representar datos XML.  
  
 **X DO NOT** usar <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar los datos XML. Favorecer el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o subtipos de <xref:System.Xml.Linq.XNode> en su lugar. `XmlNode`y `XmlDocument` no están diseñados para exponer en las API públicas.  
  
 **✓ HACER** usar `XmlReader`, `IXPathNavigable`, o subtipos de `XNode` como entrada o salida de los miembros que aceptan o devuelven XML.  
  
 Use estas abstracciones en lugar de `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, ya que esto desacopla los métodos de implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** subclase `XmlDocument` si desea crear un tipo que representa una vista XML de un origen de datos o el modelo de objeto subyacente.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
