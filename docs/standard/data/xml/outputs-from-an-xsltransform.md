---
title: Resultados de XslTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 92bf2d7184ca2eb8b17c1d83130c66d1f33f0483
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="outputs-from-an-xsltransform"></a>Resultados de XslTransform
Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.  
  
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Vea [mediante la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>. En la tabla siguiente se describe lo que sucede cuando un tipo de resultado se declara mediante el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> junto con una instrucción `<xsl:output>`:  
  
|\<método xsl: output = > atributo|Formato del resultado|  
|-----------------------------------------|-------------------|  
|method="xml"|XML|  
|method="html"|HTML|  
|method="text"|Texto|  
  
> [!NOTE]
>  Nota: la instrucción `<xsl:output>` se ignora cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.  
  
 Los siguientes atributos son compatibles cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream> o <xref:System.IO.TextWriter>:  
  
-   encoding*  
  
-   omit-xml-declaration  
  
-   independiente  
  
-   doctype-public  
  
-   doctype-system  
  
-   cdata-section-elements  
  
-   indent  
  
    > [!NOTE]
    >  *el atributo encoding se omite cuando el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> envía su resultado a <xref:System.IO.TextWriter>. Se usa en su lugar la propiedad encoding de <xref:System.IO.TextWriter>.  
  
 El atributo siguiente se omite si el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream>:  
  
-   versión: la versión es siempre 1.0.  
  
-   tipo de medio: el tipo de medio  
  
## <a name="escaping-special-characters"></a>Caracteres de escape especiales  
 La etiqueta `<xsl:text disable-output-escaping>` se utiliza para indicar si los caracteres especiales tienen que ser caracteres de escape en formato XML (por ejemplo, mediante `<&lt>` en lugar del símbolo `"<"`) o izquierda en el estado actual. El atributo `disable-output-escaping` se omite cuando se transforma en un objeto <xref:System.Xml.XmlReader> o<xref:System.Xml.XmlWriter> y no afecta a caracteres especiales.  
  
## <a name="see-also"></a>Vea también  
 [Clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
