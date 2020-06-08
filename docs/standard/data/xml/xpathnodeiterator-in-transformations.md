---
title: XPathNodeIterator en transformaciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
ms.openlocfilehash: 88b8f4acbb9fa92d71659ee006ee544275353954
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282758"
---
# <a name="xpathnodeiterator-in-transformations"></a>XPathNodeIterator en transformaciones
<xref:System.Xml.XPath.XPathNodeIterator> proporciona métodos para iterar por un conjunto de nodos creados como resultado de una consulta XPath o un fragmento del árbol de resultados convertido en un conjunto de nodos mediante el uso del método node-set. <xref:System.Xml.XPath.XPathNodeIterator> permite iterar por los nodos de un conjunto de nodos. Una vez que se ha recuperado un conjunto de nodos, la clase <xref:System.Xml.XPath.XPathNodeIterator> proporciona un cursor de solo avance y de solo lectura para el conjunto de nodos seleccionado. El conjunto de nodos se crea en orden de documento, de forma que al llamar a este método se desplaza al siguiente nodo en orden de documento. <xref:System.Xml.XPath.XPathNodeIterator> no construye un árbol de nodos de todos los nodos en el conjunto. En lugar de ello, proporciona una ventana de un único nodo en los datos y expone el nodo subyacente al que apunta a medida que se recorre el árbol. Los métodos y las propiedades disponibles desde la clase <xref:System.Xml.XPath.XPathNodeIterator> permiten obtener información desde el nodo actual. Para obtener una lista de los métodos y de las propiedades disponibles, vea <xref:System.Windows.Forms.ToolBar>.  
  
 Puesto que <xref:System.Xml.XPath.XPathNodeIterator> se mueve a través de un conjunto de nodos creado a partir de una consulta XPath y lo hace solo hacia adelante, hay que utilizar el método <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> para recorrerlo. El tipo de valor devuelto por este método es `Boolean` y devuelve `true` si se desplaza hasta el siguiente nodo seleccionado, y `false` si no hay más nodos seleccionados. Si devuelve `true`, en la lista siguiente se muestran las propiedades disponibles:  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 Cuando se encuentre ante un conjunto de nodos por primera vez, debe realizar una llamada a <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> para colocar <xref:System.Xml.XPath.XPathNodeIterator> en el primer nodo del conjunto seleccionado. De esta forma se puede escribir un bucle while.  
  
 El siguiente ejemplo muestra cómo pasar <xref:System.Xml.XPath.XPathNodeIterator> a <xref:System.Xml.Xsl.XslTransform> como parámetro en <xref:System.Xml.Xsl.XsltArgumentList>. La entrada en el código es **books.xml** y la hoja de estilos es **text.xsl**. El archivo **test.xml** es <xref:System.Xml.XPath.XPathDocument>.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
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
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## <a name="booksxml"></a>books.xml  
  
```xml  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## <a name="testxsl"></a>test.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a>test.xml  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a>Salida (out.xml)  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
