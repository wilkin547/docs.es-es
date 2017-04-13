---
title: "Transformaciones XSLT | Microsoft Docs"
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
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Transformaciones XSLT
El objetivo de XSLT \(Extensible Stylesheet Language Transformation\) es transformar el contenido de un documento XML de origen en otro documento con un formato o estructura diferentes.  Por ejemplo, se puede emplear para transformar el documento XML en HTML con el fin de usarlo en un sitio web o transformarlo en un documento que sólo contenga los campos necesarios para una aplicación.  Este proceso de transformación está especificado por la [recomendación de transformaciones XSL \(XSLT\) de W3C, versión 1.0](http://go.microsoft.com/fwlink/?LinkID=49919).  
  
 La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT en .NET Framework.  La clase <xref:System.Xml.Xsl.XslCompiledTransform> es compatible con la recomendación XSLT 1.0. del W3C mencionada anteriormente.  
  
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework versión 2.0.  La clase <xref:System.Xml.Xsl.XslCompiledTransform> es una nueva implementación del motor XSLT.  Incluye mejoras de rendimiento y nuevas características de seguridad.  La práctica recomendada es crear aplicaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## En esta sección  
 [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>.  
  
 [Compilador XSLT \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 Proporciona información sobre cómo utilizar el compilador XSLT.  
  
 [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslTransform>.  
  
 **Nota** La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.  
  
## Referencia  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## Secciones relacionadas  
 [Documentos y datos XML](../../../../docs/standard/data/xml/index.md)