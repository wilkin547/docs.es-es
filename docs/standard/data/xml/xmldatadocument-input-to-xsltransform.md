---
title: Entrada de XmlDataDocument en XslTransform
ms.date: 03/30/2017
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
ms.openlocfilehash: 46abc88f413ae5e0c5f78deba25e939b957a5beb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827573"
---
# <a name="xmldatadocument-input-to-xsltransform"></a>Entrada de XmlDataDocument en XslTransform
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Microsoft .NET Framework implementa Document Object Model (DOM) de XML para proporcionar acceso a datos de documentos XML, así como clases adicionales para leer, escribir y navegar por documentos XML. <xref:System.Xml.XmlDataDocument>, que se encuentra en el espacio de nombres <xref:System.Xml>, proporciona acceso relacional a datos con su capacidad de sincronización con los datos relacionales en <xref:System.Data.DataSet>. Se puede ver y manipular simultáneamente el XML estructurado a través de la representación relacional del <xref:System.Data.DataSet> o manipular el XML semiestructurado a través de la representación DOM de <xref:System.Xml.XmlDataDocument>. Por lo tanto, <xref:System.Xml.XmlDataDocument> cruza el límite de los universos relacional y XML.  
  
 Si los datos están almacenados en una estructura relacional y desea que sean la entrada para una transformación XSLT, puede cargarlos en un <xref:System.Data.DataSet> y asociarlo con <xref:System.Xml.XmlDataDocument>. <xref:System.Xml.XPath.XPathNavigator>, la entrada a <xref:System.Xml.Xsl.XslTransform>, se implementa en <xref:System.Xml.XmlDataDocument> a través de la interfaz <xref:System.Xml.XPath.IXPathNavigable>. Se pueden realizar transformaciones de XSLT en datos relacionales si se cargan en un <xref:System.Data.DataSet> y se sincronizan con <xref:System.Xml.XmlDataDocument>.  
  
 Para más información sobre cómo aplicar una transformación a datos relacionales, vea [Aplicar una transformación XSL a un DataSet](../../../framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDataDocument>
- [Sincronización de DataSet y XmlDataDocument](../../../framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
- [XPathNavigator en transformaciones](xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md)
