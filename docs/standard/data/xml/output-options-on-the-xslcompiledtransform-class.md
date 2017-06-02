---
title: "Opciones de salida en la clase XslCompiledTransform | Microsoft Docs"
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
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Opciones de salida en la clase XslCompiledTransform
En este tema se describen las opciones de salida XSLT disponibles.  Puede especificar opciones de salida en la hoja de estilos o en el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## Elemento xsl:output  
 El elemento `xsl:output` especifica opciones para la salida.  El tipo de salida que especifica el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> determina el comportamiento de las opciones `xsl:output`.  
  
 En la siguiente tabla se describe el comportamiento de cada uno de los atributos disponibles en el elemento `xsl:output` cuando el tipo de salida es una secuencia o un <xref:System.IO.TextWriter>.  
  
|Nombre del atributo|Comportamiento|  
|-------------------------|--------------------|  
|método|Se admite.|  
|version|ignorado.  La versión es siempre 1.0 para XML y 4.0 para HTML.|  
|encoding|Se omite cuando la salida se envía a <xref:System.IO.TextWriter>.  Se utiliza en su lugar la propiedad <xref:System.IO.TextWriter.Encoding%2A?displayProperty=fullName>.|  
|omit\-xml\-declaration|Se admite.|  
|independiente|Se admite.|  
|doctype\-public|Se admite.|  
|doctype\-system|Se admite.|  
|cdata\-section\-elements|Se admite.|  
|indent|Se admite.|  
|media\-type|Se admite.|  
  
#### Envío de la salida a XmlWriter  
 Si la hoja de estilos utiliza el elemento `xsl:output` y el tipo de salida es un objeto <xref:System.Xml.XmlWriter>, debería utilizar la propiedad <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> cuando cree el objeto <xref:System.Xml.XmlWriter>.  La propiedad <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> devuelve un objeto <xref:System.Xml.XmlWriterSettings> que contiene información derivada del elemento `xsl:output` de una hoja de estilos compilada.  Este objeto <xref:System.Xml.XmlWriterSettings> se puede pasar al método <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName> para crear un objeto <xref:System.Xml.XmlWriter> con los valores correctos.  
  
## Tipos de salida  
 En la siguiente lista se describen los tipos de salida disponibles en el comando <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
#### XmlWriter  
 La clase <xref:System.Xml.XmlWriter> escribe archivos o secuencias XML.  Puede especificar las características que se van a permitir en el objeto <xref:System.Xml.XmlWriter>, incluyendo las opciones de salida, utilizando la clase <xref:System.Xml.XmlWriterSettings>.  La clase <xref:System.Xml.XmlWriter> es una parte integral de la estructura <xref:System.Xml>.  Utilice este tipo de salida para canalizar los resultados de la salida en otro proceso XML.  
  
#### String  
 Utilice este tipo de salida para especificar el identificador URI del archivo de salida.  
  
#### Secuencia  
 Una secuencia es una abstracción de una secuencia de bytes como, por ejemplo, un archivo, un dispositivo de entrada\/salida, una canalización de comunicación entre procesos o un socket TCP\/IP.  La clase <xref:System.IO.Stream> y sus clases derivadas proporcionan una vista genérica de estos diferentes tipos de entrada y salida, aislando al programador de los detalles específicos del sistema operativo y los dispositivos subyacentes.  
  
 Utilice este tipo de salida para enviar datos a una <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> o a un flujo de salida \(`Response.OutputStream`\).  
  
#### TextWriter  
 <xref:System.IO.TextWriter> escribe caracteres secuenciales.  Se implementa en las clases <xref:System.IO.StringWriter> y <xref:System.IO.StreamWriter>, que escriben caracteres en cadenas o secuencias, respectivamente.  Utilice este tipo de salida cuando desee enviar la salida a una cadena.  
  
## Notas  
  
-   Cuando escriba etiquetas vacías, se escribe un espacio entre el último carácter del nombre del elemento y la barra diagonal inversa, por ejemplo, `<myElement />`.  Esto permite que los exploradores más antiguos muestren correctamente las páginas HTML generadas.  
  
## Vea también  
 [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)