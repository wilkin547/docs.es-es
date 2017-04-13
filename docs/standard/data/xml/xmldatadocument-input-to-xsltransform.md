---
title: "Entrada de XmlDataDocument en XslTransform | Microsoft Docs"
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
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Entrada de XmlDataDocument en XslTransform
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations \(XSLT\) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Para obtener más información, vea [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de Microsoft implementa el Modelo de objetos de documento \(DOM\) de XML para proporcionar acceso a datos de documentos XML, así como clases adicionales para leer, escribir y navegar por documentos XML.<xref:System.Xml.XmlDataDocument>, que se encuentra en el espacio de nombres <xref:System.Xml>, proporciona acceso relacional a datos con su capacidad de sincronización con los datos relacionales en <xref:System.Data.DataSet>. Se puede ver y manipular simultáneamente el XML estructurado a través de la representación relacional del <xref:System.Data.DataSet> o manipular el XML semiestructurado a través de la representación DOM de <xref:System.Xml.XmlDataDocument>. Por lo tanto, <xref:System.Xml.XmlDataDocument> cruza el límite de los universos relacional y XML.  
  
 Si los datos están almacenados en una estructura relacional y desea que sean la entrada para una transformación XSLT, puede cargarlos en un <xref:System.Data.DataSet> y asociarlo con <xref:System.Xml.XmlDataDocument>.<xref:System.Xml.XPath.XPathNavigator>, la entrada a <xref:System.Xml.Xsl.XslTransform>, se implementa en <xref:System.Xml.XmlDataDocument> a través de la interfaz <xref:System.Xml.XPath.IXPathNavigable>. Se pueden realizar transformaciones de XSLT en datos relacionales si se cargan en un <xref:System.Data.DataSet> y se sincronizan con <xref:System.Xml.XmlDataDocument>.  
  
 Para más información sobre cómo aplicar una transformación a datos relacionales, consulte [Aplicar una transformación XSLT a un DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## Vea también  
 <xref:System.Xml.XmlDataDocument>   
 [Sincronización de DataSet y XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)   
 [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)   
 [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)   
 [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)   
 [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)   
 [Entrada XPathDocument Input para XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)   
 [Entrada de XmlDocument en XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)