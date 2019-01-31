---
title: Uso de la clase XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce9a06c14141bb658eb665e643d8da27e18dd94f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590384"
---
# <a name="using-the-xslcompiledtransform-class"></a>Uso de la clase XslCompiledTransform
La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT de Microsoft .NET Framework. Esta clase se utiliza para compilar hojas de estilos y ejecutar transformaciones XSLT.  
  
> [!NOTE]
>  Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación. Esto se debe a que el archivo XSLT debe compilarse antes de cargarse. Para más información, vea la entrada de blog siguiente: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/) (¿Es más lento XslCompiledTransform que XslTransform?)  
  
## <a name="in-this-section"></a>En esta sección  
 [Entradas en la clase XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Describe las opciones de entrada XSLT disponibles.  
  
 [Opciones de salida en la clase XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Describe las opciones de salida XSLT disponibles.  
  
 [Resolución de recursos externos durante el procesamiento XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Describe el uso de la clase <xref:System.Xml.XmlResolver> para resolver recursos externos.  
  
 [Extensión de hojas de estilos SXLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Describe cómo se admiten las extensiones XSLT.  
  
|||  
|-|-|  
|[Errores XSLT recuperables](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Enumera cada uno de los comportamientos discrecionales que permite la recomendación XSLT 1.0 del W3C y describe cómo la clase <xref:System.Xml.Xsl.XslCompiledTransform> controla estos comportamientos.|  
|[Cómo: Transformar un fragmento de nodo](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Describe cómo transformar un fragmento de nodo.|  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
