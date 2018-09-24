---
title: Entrada de XmlDataDocument en XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7fb30104f36a565f4e6742c8f808c48e4ef39ec
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696773"
---
# <a name="xmldatadocument-input-to-xsltransform"></a>Entrada de XmlDataDocument en XslTransform
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de Microsoft implementa el Modelo de objetos de documento (DOM) de XML para proporcionar acceso a datos de documentos XML, así como clases adicionales para leer, escribir y navegar por documentos XML. <xref:System.Xml.XmlDataDocument>, que se encuentra en el espacio de nombres <xref:System.Xml>, proporciona acceso relacional a datos con su capacidad de sincronización con los datos relacionales en <xref:System.Data.DataSet>. Se puede ver y manipular simultáneamente el XML estructurado a través de la representación relacional del <xref:System.Data.DataSet> o manipular el XML semiestructurado a través de la representación DOM de <xref:System.Xml.XmlDataDocument>. Por lo tanto, <xref:System.Xml.XmlDataDocument> cruza el límite de los universos relacional y XML.  
  
 Si los datos están almacenados en una estructura relacional y desea que sean la entrada para una transformación XSLT, puede cargarlos en un <xref:System.Data.DataSet> y asociarlo con <xref:System.Xml.XmlDataDocument>. <xref:System.Xml.XPath.XPathNavigator>, la entrada a <xref:System.Xml.Xsl.XslTransform>, se implementa en <xref:System.Xml.XmlDataDocument> a través de la interfaz <xref:System.Xml.XPath.IXPathNavigable>. Se pueden realizar transformaciones de XSLT en datos relacionales si se cargan en un <xref:System.Data.DataSet> y se sincronizan con <xref:System.Xml.XmlDataDocument>.  
  
 Para más información sobre cómo aplicar una transformación a datos relacionales, vea [Aplicar una transformación XSL a un DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDataDocument>  
- [Sincronización de DataSet y XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
- [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
- [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
- [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
- [Entrada XPathDocument en XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
- [Entrada de XmlDocument en XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
