---
title: "XPathNavigator en transformaciones | Microsoft Docs"
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
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XPathNavigator en transformaciones
La clase <xref:System.Xml.XPath.XPathNavigator> proporciona acceso aleatorio de solo lectura a los datos y está diseñada para ser utilizada como una entrada para XSLT \(Extensible Stylesheet Language for Transformations\).  Se implementa en <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, y <xref:System.Xml.XmlDocument>.  <xref:System.Xml.XPath.XPathNavigator> se basa en el modelo de datos de World Wide Web Consortium \(W3C\) tal y como se describe en la sección 5 de la recomendación del lenguage de rutas XML \(XPath\).  
  
 <xref:System.Xml.XPath.XPathNavigator> define un modelo de cursor sobre cualquier almacén y proporciona rápidas consultas XPath de solo lectura sobre cualquier almacén de datos.  <xref:System.Xml.XPath.XPathNavigator> también es la clase utilizada para iterar por fragmentos de árboles de resultados.  
  
 La API le permite obtener información del nodo actual del almacén y moverse entre los nodos conectados.  <xref:System.Xml.XPath.XPathNavigator> es el modelo de estilo de cursor que realiza exploraciones transversales de un almacén mediante un conjunto de métodos **Move**.  <xref:System.Xml.XPath.XPathNavigator> siempre se sitúa en un nodo.  Los métodos **Move** que presentan errores dejan <xref:System.Xml.XPath.XPathNavigator> sin modificar.  
  
 <xref:System.Xml.XPath.XPathNavigator> también es la clase utilizada para iterar por fragmentos de árboles de resultados.  En el código de ejemplo siguiente se crea un fragmento de árbol de resultados dentro de una hoja de estilos mediante una llamada a la función con el parámetro `fragment` que contiene XML.  
  
## test.xsl  
  
```  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
  
```  
  
## test.xml  
  
```  
<root>Some text</root>  
```  
  
 En el siguiente ejemplo de código se utiliza la hoja de estilos **test.xsl** y los datos de entrada **test.xml**.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
    End Sub 'Main  
End Class 'sample  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## Salida  
 El resultado de la transformación se encuentra en el archivo **out.xml**:  
  
```  
<?xml version="1.0" encoding="utf-8"?>Joe  
  
```  
  
## Vea también  
 [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)