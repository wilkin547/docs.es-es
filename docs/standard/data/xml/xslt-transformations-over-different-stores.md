---
title: "Transformaciones XSLT en distintos almacenes | Microsoft Docs"
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
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Transformaciones XSLT en distintos almacenes
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  Puede llevar a cabo Extensible Stylesheet Language for Transformations \(XSLT\) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  Para obtener más información, vea [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Las clases de XML y ADO.NET en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionan un modelo de programación unificado para tener acceso a datos.  Los datos se representan como datos XML, compuestos por texto delimitado por etiquetas, y datos relacionales, que son tablas formadas por filas y columnas.  El XML en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] lee los datos XML de cualquier flujo de datos en árboles de nodos del Modelo de objetos del documento \(DOM\), donde se puede tener acceso a los datos mediante programación, mientras que ADO.NET proporciona los medios para tener acceso y manipular los datos relacionales de un objeto <xref:System.Data.DataSet>.  
  
 El DOM de XML proporciona acceso a los datos de documentos XML y clases adicionales para leer, escribir y navegar por documentos XML.  Estas clases son compatibles en el espacio de nombres <xref:System.Xml>, que también unifica el DOM de XML con los servicios de acceso a los datos proporcionados por ADO.NET.  <xref:System.Xml.XmlDataDocument> proporciona acceso relacional a los datos.  <xref:System.Xml.XmlDataDocument> asigna código XML a los datos relacionales en un <xref:System.Data.DataSet> de ADO.NET.  Cualquier aplicación basada en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] puede utilizar las clases del espacio de nombres <xref:System.Xml> para tener acceso y manipular documentos XML y datos relacionales en <xref:System.Xml.XmlDataDocument>.  Esta implementación permite el uso de arquitecturas en varias capas para recopilar y distribuir datos.  Para obtener más información, consulta [Integración de XML con datos relacionales y ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## Vea también  
 [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)