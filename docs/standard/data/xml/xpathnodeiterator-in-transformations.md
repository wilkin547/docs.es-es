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
# <a name="xpathnodeiterator-in-transformations"></a><span data-ttu-id="fca24-102">XPathNodeIterator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="fca24-102">XPathNodeIterator in Transformations</span></span>
<span data-ttu-id="fca24-103"><xref:System.Xml.XPath.XPathNodeIterator> proporciona métodos para iterar por un conjunto de nodos creados como resultado de una consulta XPath o un fragmento del árbol de resultados convertido en un conjunto de nodos mediante el uso del método node-set.</span><span class="sxs-lookup"><span data-stu-id="fca24-103">The <xref:System.Xml.XPath.XPathNodeIterator> provides methods to iterate over a set of nodes created as the result of an XML Path Language (XPath) query or a result tree fragment converted to a node set by use of the node-set method.</span></span> <span data-ttu-id="fca24-104"><xref:System.Xml.XPath.XPathNodeIterator> permite iterar por los nodos de un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="fca24-104">The <xref:System.Xml.XPath.XPathNodeIterator> enables you to iterate over the nodes within that node set.</span></span> <span data-ttu-id="fca24-105">Una vez que se ha recuperado un conjunto de nodos, la clase <xref:System.Xml.XPath.XPathNodeIterator> proporciona un cursor de solo avance y de solo lectura para el conjunto de nodos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fca24-105">Once a node set is retrieved, the <xref:System.Xml.XPath.XPathNodeIterator> class provides a read-only, forward-only cursor to the selected set of nodes.</span></span> <span data-ttu-id="fca24-106">El conjunto de nodos se crea en orden de documento, de forma que al llamar a este método se desplaza al siguiente nodo en orden de documento.</span><span class="sxs-lookup"><span data-stu-id="fca24-106">The node set is created in document order, so calling this method moves to the next node in document order.</span></span> <span data-ttu-id="fca24-107"><xref:System.Xml.XPath.XPathNodeIterator> no construye un árbol de nodos de todos los nodos en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="fca24-107"><xref:System.Xml.XPath.XPathNodeIterator> does not build a node tree of all the nodes in the set.</span></span> <span data-ttu-id="fca24-108">En lugar de ello, proporciona una ventana de un único nodo en los datos y expone el nodo subyacente al que apunta a medida que se recorre el árbol.</span><span class="sxs-lookup"><span data-stu-id="fca24-108">Instead, it provides a single node window into the data, exposing the underlying node it points to as you move around in the tree.</span></span> <span data-ttu-id="fca24-109">Los métodos y las propiedades disponibles desde la clase <xref:System.Xml.XPath.XPathNodeIterator> permiten obtener información desde el nodo actual.</span><span class="sxs-lookup"><span data-stu-id="fca24-109">The methods and properties available from the <xref:System.Xml.XPath.XPathNodeIterator> class enable you to get information from the current node.</span></span> <span data-ttu-id="fca24-110">Para obtener una lista de los métodos y de las propiedades disponibles, vea <xref:System.Windows.Forms.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="fca24-110">For a list of the available methods and properties, see <xref:System.Windows.Forms.ToolBar>.</span></span>  
  
 <span data-ttu-id="fca24-111">Puesto que <xref:System.Xml.XPath.XPathNodeIterator> se mueve a través de un conjunto de nodos creado a partir de una consulta XPath y lo hace solo hacia adelante, hay que utilizar el método <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> para recorrerlo.</span><span class="sxs-lookup"><span data-stu-id="fca24-111">Since an <xref:System.Xml.XPath.XPathNodeIterator> moves over a set of nodes created from an XPath query and moves forward only, the way to move is by using the <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> method.</span></span> <span data-ttu-id="fca24-112">El tipo de valor devuelto por este método es `Boolean` y devuelve `true` si se desplaza hasta el siguiente nodo seleccionado, y `false` si no hay más nodos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fca24-112">The return type of this method is `Boolean`, returning `true` if it moves to the next selected node, and `false` if there are no more selected nodes.</span></span> <span data-ttu-id="fca24-113">Si devuelve `true`, en la lista siguiente se muestran las propiedades disponibles:</span><span class="sxs-lookup"><span data-stu-id="fca24-113">If it returns `true`, the following list shows the properties available:</span></span>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 <span data-ttu-id="fca24-114">Cuando se encuentre ante un conjunto de nodos por primera vez, debe realizar una llamada a <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> para colocar <xref:System.Xml.XPath.XPathNodeIterator> en el primer nodo del conjunto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fca24-114">When you are looking at a node set for the first time, a call to <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> must be made to position the <xref:System.Xml.XPath.XPathNodeIterator> on the first node of the selected set.</span></span> <span data-ttu-id="fca24-115">De esta forma se puede escribir un bucle while.</span><span class="sxs-lookup"><span data-stu-id="fca24-115">This allows a while loop to be written.</span></span>  
  
 <span data-ttu-id="fca24-116">El siguiente ejemplo muestra cómo pasar <xref:System.Xml.XPath.XPathNodeIterator> a <xref:System.Xml.Xsl.XslTransform> como parámetro en <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="fca24-116">The following code example shows how to pass an <xref:System.Xml.XPath.XPathNodeIterator> to an <xref:System.Xml.Xsl.XslTransform> as a parameter in the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span> <span data-ttu-id="fca24-117">La entrada en el código es **books.xml** y la hoja de estilos es **text.xsl**.</span><span class="sxs-lookup"><span data-stu-id="fca24-117">The input to the code is **books.xml**, and the style sheet is **text.xsl**.</span></span> <span data-ttu-id="fca24-118">El archivo **test.xml** es <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="fca24-118">The file **test.xml** is the <xref:System.Xml.XPath.XPathDocument>.</span></span>  
  
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
  
## <a name="booksxml"></a><span data-ttu-id="fca24-119">books.xml</span><span class="sxs-lookup"><span data-stu-id="fca24-119">books.xml</span></span>  
  
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
  
## <a name="testxsl"></a><span data-ttu-id="fca24-120">test.xsl</span><span class="sxs-lookup"><span data-stu-id="fca24-120">test.xsl</span></span>  
  
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
  
## <a name="testxml"></a><span data-ttu-id="fca24-121">test.xml</span><span class="sxs-lookup"><span data-stu-id="fca24-121">test.xml</span></span>  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a><span data-ttu-id="fca24-122">Salida (out.xml)</span><span class="sxs-lookup"><span data-stu-id="fca24-122">Output (out.xml)</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fca24-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fca24-123">See also</span></span>

- [<span data-ttu-id="fca24-124">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="fca24-124">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
