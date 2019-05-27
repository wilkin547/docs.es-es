---
title: Transformaciones XSLT en distintos almacenes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e9b8c41602ed180b491ca55816fadf28d6cecd3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586502"
---
# <a name="xslt-transformations-over-different-stores"></a>Transformaciones XSLT en distintos almacenes
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Las clases de XML y ADO.NET de .NET Framework proporcionan un modelo de programación unificado para acceder a datos. Los datos se representan como datos XML, compuestos por texto delimitado por etiquetas, y datos relacionales, que son tablas formadas por filas y columnas. El XML de .NET Framework lee los datos XML de cualquier flujo de datos en árboles de nodos de Document Object Model (DOM) de XML, donde se puede acceder a los datos mediante programación, mientras que ADO.NET proporciona los medios para acceder a los datos relacionales de un objeto <xref:System.Data.DataSet> y manipularlos.  
  
 El DOM de XML proporciona acceso a los datos de documentos XML y clases adicionales para leer, escribir y navegar por documentos XML. Estas clases son compatibles en el espacio de nombres <xref:System.Xml>, que también unifica el DOM de XML con los servicios de acceso a los datos proporcionados por ADO.NET. <xref:System.Xml.XmlDataDocument> proporciona acceso relacional a los datos. <xref:System.Xml.XmlDataDocument> asigna código XML a los datos relacionales en un <xref:System.Data.DataSet> de ADO.NET. Cualquier aplicación basada en .NET Framework puede usar las clases del espacio de nombres <xref:System.Xml> para acceder a documentos XML y datos relacionales de <xref:System.Xml.XmlDataDocument> y manipularlos. Esta implementación permite el uso de arquitecturas en varias capas para recopilar y distribuir datos. Para obtener más información, vea [Integración de XML con datos relacionales y ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
