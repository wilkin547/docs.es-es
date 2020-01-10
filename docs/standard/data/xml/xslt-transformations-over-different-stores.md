---
title: Transformaciones XSLT en distintos almacenes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
ms.openlocfilehash: 490ac30a3e4f0c50cb5d011f1d583c6e5ce9e672
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709665"
---
# <a name="xslt-transformations-over-different-stores"></a>Transformaciones XSLT en distintos almacenes
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Las clases de XML y ADO.NET de .NET Framework proporcionan un modelo de programación unificado para acceder a datos. Los datos se representan como datos XML, compuestos por texto delimitado por etiquetas, y datos relacionales, que son tablas formadas por filas y columnas. El XML de .NET Framework lee los datos XML de cualquier flujo de datos en árboles de nodos de Document Object Model (DOM) de XML, donde se puede acceder a los datos mediante programación, mientras que ADO.NET proporciona los medios para acceder a los datos relacionales de un objeto <xref:System.Data.DataSet> y manipularlos.  
  
 El DOM de XML proporciona acceso a los datos de documentos XML y clases adicionales para leer, escribir y navegar por documentos XML. Estas clases son compatibles en el espacio de nombres <xref:System.Xml>, que también unifica el DOM de XML con los servicios de acceso a los datos proporcionados por ADO.NET. <xref:System.Xml.XmlDataDocument> proporciona acceso relacional a los datos. <xref:System.Xml.XmlDataDocument> asigna código XML a los datos relacionales en un <xref:System.Data.DataSet> de ADO.NET. Cualquier aplicación basada en .NET Framework puede usar las clases del espacio de nombres <xref:System.Xml> para acceder a documentos XML y datos relacionales de <xref:System.Xml.XmlDataDocument> y manipularlos. Esta implementación permite el uso de arquitecturas en varias capas para recopilar y distribuir datos. Para obtener más información, vea [Integración de XML con datos relacionales y ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
