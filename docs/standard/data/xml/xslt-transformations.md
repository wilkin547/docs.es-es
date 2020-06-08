---
title: Transformaciones XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
ms.openlocfilehash: 92d0af1519260d458d3954beaef38e698142367a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288308"
---
# <a name="xslt-transformations"></a>Transformaciones XSLT
El objetivo de XSLT (Extensible Stylesheet Language Transformation) es transformar el contenido de un documento XML de origen en otro documento con un formato o estructura diferentes. Por ejemplo, se puede emplear para transformar el documento XML en HTML con el fin de usarlo en un sitio web o transformarlo en un documento que sólo contenga los campos necesarios para una aplicación. Las especificaciones de este proceso de transformación se encuentran en la [recomendación W3C XSL Transformations (XSLT) Version 1.0](https://www.w3.org/TR/xslt-10/).  
  
 La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT en .NET. La clase <xref:System.Xml.Xsl.XslCompiledTransform> es compatible con la [recomendación XSLT 1.0. del W3C](https://www.w3.org/TR/xslt-10/).  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework versión 2.0. La clase <xref:System.Xml.Xsl.XslCompiledTransform> es una nueva implementación del motor XSLT. Incluye mejoras de rendimiento y nuevas características de seguridad. La práctica recomendada es crear aplicaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md)  
 Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md)  
 Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>.  
  
 [Compilador XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md)  
 Proporciona información sobre cómo utilizar el compilador XSLT.  
  
 [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)  
 Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Documentos y datos XML](index.md)
