---
title: Uso de la clase XslCompiledTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a00ae5a2f54aee3d6ac16d0870f9171fe42ca289
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="using-the-xslcompiledtransform-class"></a>Uso de la clase XslCompiledTransform
La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT de Microsoft .NET Framework. Esta clase se utiliza para compilar hojas de estilos y ejecutar transformaciones XSLT.  
  
> [!NOTE]
>  Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación. Esto se debe a que el archivo XSLT debe compilarse antes de cargarse. Para obtener más información, vea el siguiente blog: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/) (¿XslCompiledTransform es más lento que XslTransform?).  
  
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
|[Transformación de un fragmento de nodo](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Describe cómo transformar un fragmento de nodo.|  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
