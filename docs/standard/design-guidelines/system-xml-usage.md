---
title: "Uso de System.Xml | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Uso de System.Xml
Esta sección se habla sobre el uso de varios tipos que se encuentran en <xref:System.Xml?displayProperty=fullName> espacios de nombres que pueden utilizarse para representar los datos XML.  
  
 **X no** use <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar los datos XML. Favorecer el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o subtipos de <xref:System.Xml.Linq.XNode> en su lugar.`XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.  
  
 **✓ hacer** use `XmlReader`, `IXPathNavigable`, o subtipos de `XNode` como entrada o salida de los miembros que aceptan o devuelven XML.  
  
 Utilice estas abstracciones en lugar de `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, ya que esto desacopla los métodos de las implementaciones concretas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode`, `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X no** subclase `XmlDocument` Si desea crear un tipo que representa una vista XML de un origen de datos o el modelo de objeto subyacente.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)