---
title: Resultados de XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 93cbf7807630a605e17e7f513055c052aad0d08e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159642"
---
# <a name="outputs-from-an-xsltransform"></a>Resultados de XslTransform
Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>. En la tabla siguiente se describe lo que sucede cuando un tipo de resultado se declara mediante el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> junto con una instrucción `<xsl:output>`:  
  
|\<xsl:output method = > attribute|Formato del resultado|  
|-----------------------------------------|-------------------|  
|method="xml"|XML|  
|method="html"|HTML|  
|method="text"|Text|  
  
> [!NOTE]
> Nota: La instrucción `<xsl:output>` se ignora cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.  
  
 Los siguientes atributos son compatibles cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream> o <xref:System.IO.TextWriter>:  
  
- encoding*  
  
- omit-xml-declaration  
  
- independiente  
  
- doctype-public  
  
- doctype-system  
  
- cdata-section-elements  
  
- indent  
  
    > [!NOTE]
    > \*El atributo encoding se omite cuando el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> envía su salida a <xref:System.IO.TextWriter>. Se usa en su lugar la propiedad encoding de <xref:System.IO.TextWriter>.
  
 El atributo siguiente se omite si el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream>:  
  
- versión: la versión es siempre 1.0.  
  
- tipo de medio: el tipo de medio  
  
## <a name="escaping-special-characters"></a>Caracteres de escape especiales  
 La etiqueta `<xsl:text disable-output-escaping>` se utiliza para indicar si los caracteres especiales tienen que ser caracteres de escape en formato XML (por ejemplo, mediante `<&lt>` en lugar del símbolo `"<"`) o izquierda en el estado actual. El atributo `disable-output-escaping` se omite cuando se transforma en un objeto <xref:System.Xml.XmlReader> o<xref:System.Xml.XmlWriter> y no afecta a caracteres especiales.  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
