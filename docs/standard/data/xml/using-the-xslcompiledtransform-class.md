---
title: Uso de la clase XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: b9d14a79347610abcd2f770488acb53218ce3e46
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556777"
---
# <a name="using-the-xslcompiledtransform-class"></a>Uso de la clase XslCompiledTransform
La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT de Microsoft .NET Framework. Esta clase se utiliza para compilar hojas de estilos y ejecutar transformaciones XSLT.  
  
> [!NOTE]
> Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación. Esto se debe a que el archivo XSLT debe compilarse antes de cargarse. Para más información, vea la entrada de blog siguiente: [XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (¿Es más lento XslCompiledTransform que XslTransform?)  
  
## <a name="in-this-section"></a>En esta sección  
 [Entradas en la clase XslCompiledTransform](inputs-to-the-xslcompiledtransform-class.md)  
 Describe las opciones de entrada XSLT disponibles.  
  
 [Opciones de salida en la clase XslCompiledTransform](output-options-on-the-xslcompiledtransform-class.md)  
 Describe las opciones de salida XSLT disponibles.  
  
 [Resolución de recursos externos durante el procesamiento XSLT](resolving-external-resources-during-xslt-processing.md)  
 Describe el uso de la clase <xref:System.Xml.XmlResolver> para resolver recursos externos.  
  
 [Extensión de hojas de estilos SXLT](extending-xslt-style-sheets.md)  
 Describe cómo se admiten las extensiones XSLT.  
  
|||  
|-|-|  
|[Errores XSLT recuperables](recoverable-xslt-errors.md)|Enumera cada uno de los comportamientos discrecionales que permite la recomendación XSLT 1.0 del W3C y describe cómo la clase <xref:System.Xml.Xsl.XslCompiledTransform> controla estos comportamientos.|  
|[Cómo: Transformar un fragmento de nodo](how-to-transform-a-node-fragment.md)|Describe cómo transformar un fragmento de nodo.|  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md)  
 Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
