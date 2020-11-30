---
title: Opciones de salida en la clase XslCompiledTransform
ms.date: 03/30/2017
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
ms.openlocfilehash: 5835cfee69730d5dd2322422aeed6e0d72995eec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731142"
---
# <a name="output-options-on-the-xslcompiledtransform-class"></a>Opciones de salida en la clase XslCompiledTransform

En este tema se describen las opciones de salida XSLT disponibles. Puede especificar opciones de salida en la hoja de estilos o en el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="xsloutput-element"></a>Elemento xsl:output  

 El elemento `xsl:output` especifica opciones para la salida. El tipo de salida que especifica el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> determina el comportamiento de las opciones `xsl:output`.  
  
 En la siguiente tabla se describe el comportamiento de cada uno de los atributos disponibles en el elemento `xsl:output` cuando el tipo de salida es una secuencia o un <xref:System.IO.TextWriter>.  
  
|Nombre del atributo|Comportamiento|  
|--------------------|--------------|  
|método|Se admite.|  
|version|ignorado. La versión es siempre 1.0 para XML y 4.0 para HTML.|  
|encoding|Se omite cuando la salida se envía a <xref:System.IO.TextWriter>. Se utiliza en su lugar la propiedad <xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType>.|  
|omit-xml-declaration|Se admite.|  
|independiente|Se admite.|  
|doctype-public|Se admite.|  
|doctype-system|Se admite.|  
|cdata-section-elements|Se admite.|  
|indent|Se admite.|  
|media-type|Se admite.|  
  
#### <a name="sending-output-to-an-xmlwriter"></a>Envío de la salida a XmlWriter  

 Si la hoja de estilos utiliza el elemento `xsl:output` y el tipo de salida es un objeto <xref:System.Xml.XmlWriter>, debería utilizar la propiedad <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> cuando cree el objeto <xref:System.Xml.XmlWriter>. La propiedad <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Xml.XmlWriterSettings> que contiene información derivada del elemento `xsl:output` de una hoja de estilos compilada. Este objeto <xref:System.Xml.XmlWriterSettings> se puede pasar al método <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> para crear un objeto <xref:System.Xml.XmlWriter> con los valores correctos.  
  
## <a name="output-types"></a>Tipos de salida  

 En la siguiente lista se describen los tipos de salida disponibles en el comando <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
#### <a name="xmlwriter"></a>XmlWriter  

 La clase <xref:System.Xml.XmlWriter> escribe archivos o secuencias XML. Puede especificar las características que se van a permitir en el objeto <xref:System.Xml.XmlWriter>, incluyendo las opciones de salida, utilizando la clase <xref:System.Xml.XmlWriterSettings>. La clase <xref:System.Xml.XmlWriter> es una parte integral de la estructura <xref:System.Xml>. Utilice este tipo de salida para canalizar los resultados de la salida en otro proceso XML.  
  
#### <a name="string"></a>String  

 Utilice este tipo de salida para especificar el identificador URI del archivo de salida.  
  
#### <a name="stream"></a>Secuencia  

 Una secuencia es una abstracción de una secuencia de bytes como, por ejemplo, un archivo, un dispositivo de entrada/salida, una canalización de comunicación entre procesos o un socket TCP/IP. La clase <xref:System.IO.Stream> y sus clases derivadas proporcionan una vista genérica de estos diferentes tipos de entrada y salida, aislando al programador de los detalles específicos del sistema operativo y los dispositivos subyacentes.  
  
 Utilice este tipo de salida para enviar datos a una <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> o a un flujo de salida (`Response.OutputStream`).  
  
#### <a name="textwriter"></a>TextWriter  

 <xref:System.IO.TextWriter> escribe caracteres secuenciales. Se implementa en las clases <xref:System.IO.StringWriter> y <xref:System.IO.StreamWriter>, que escriben caracteres en cadenas o secuencias, respectivamente. Utilice este tipo de salida cuando desee enviar la salida a una cadena.  
  
## <a name="notes"></a>Notas  
  
- Cuando escriba etiquetas vacías, se escribe un espacio entre el último carácter del nombre del elemento y la barra diagonal inversa, por ejemplo, `<myElement />`. Esto permite que los exploradores más antiguos muestren correctamente las páginas HTML generadas.  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](xslt-transformations.md)
