---
title: Entrada de XmlDataDocument en XslTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 813c240ca0115015158988e1226d25890cde6939
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xmldatadocument-input-to-xsltransform"></a>Entrada de XmlDataDocument en XslTransform
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Vea [mediante la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 
          [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de Microsoft implementa el Modelo de objetos de documento (DOM) de XML para proporcionar acceso a datos de documentos XML, así como clases adicionales para leer, escribir y navegar por documentos XML. El <xref:System.Xml.XmlDataDocument>, que se encuentra en la <xref:System.Xml> espacio de nombres, proporciona acceso relacional a datos con su capacidad para sincronizar con los datos relacionales en la <xref:System.Data.DataSet>. Se puede ver y manipular simultáneamente el XML estructurado a través de la representación relacional del <xref:System.Data.DataSet> o manipular el XML semiestructurado a través de la representación DOM de <xref:System.Xml.XmlDataDocument>. Por lo tanto, <xref:System.Xml.XmlDataDocument> cruza el límite de los universos relacional y XML.  
  
 Si los datos están almacenados en una estructura relacional y desea que sean la entrada para una transformación XSLT, puede cargarlos en un <xref:System.Data.DataSet> y asociarlo con <xref:System.Xml.XmlDataDocument>. <xref:System.Xml.XPath.XPathNavigator>, la entrada a <xref:System.Xml.Xsl.XslTransform>, se implementa en <xref:System.Xml.XmlDataDocument> a través de la interfaz <xref:System.Xml.XPath.IXPathNavigable>. Se pueden realizar transformaciones de XSLT en datos relacionales si se cargan en un <xref:System.Data.DataSet> y se sincronizan con <xref:System.Xml.XmlDataDocument>.  
  
 Para obtener más información sobre cómo aplicar una transformación a datos relacionales, vea [aplicar una transformación XSLT a un conjunto de datos](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.XmlDataDocument>  
 [Sincronización de DataSet y XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [Clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [Entrada XPathDocument Input para XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [Entrada de XmlDocument en XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
