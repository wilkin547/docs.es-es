---
title: Transformaciones XSLT en distintos almacenes
ms.date: 03/30/2017
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
ms.openlocfilehash: 15fcf7f3dcf3165b7b88ad01d63aa27873bf5d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685102"
---
# <a name="xslt-transformations-over-different-stores"></a>Transformaciones XSLT en distintos almacenes

> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Las clases de XML y ADO.NET de .NET Framework proporcionan un modelo de programación unificado para acceder a datos. Los datos se representan como datos XML, compuestos por texto delimitado por etiquetas, y datos relacionales, que son tablas formadas por filas y columnas. El XML de .NET Framework lee los datos XML de cualquier flujo de datos en árboles de nodos de Document Object Model (DOM) de XML, donde se puede acceder a los datos mediante programación, mientras que ADO.NET proporciona los medios para acceder a los datos relacionales de un objeto <xref:System.Data.DataSet> y manipularlos.  
  
 El DOM de XML proporciona acceso a los datos de documentos XML y clases adicionales para leer, escribir y navegar por documentos XML. Estas clases son compatibles en el espacio de nombres <xref:System.Xml>, que también unifica el DOM de XML con los servicios de acceso a los datos proporcionados por ADO.NET. <xref:System.Xml.XmlDataDocument> proporciona acceso relacional a los datos. <xref:System.Xml.XmlDataDocument> asigna código XML a los datos relacionales en un <xref:System.Data.DataSet> de ADO.NET. Cualquier aplicación basada en .NET Framework puede usar las clases del espacio de nombres <xref:System.Xml> para acceder a documentos XML y datos relacionales de <xref:System.Xml.XmlDataDocument> y manipularlos. Esta implementación permite el uso de arquitecturas en varias capas para recopilar y distribuir datos. Para obtener más información, vea [Integración de XML con datos relacionales y ADO.NET](xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
