---
title: XPathNavigator en transformaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
ms.openlocfilehash: b28a2d4991e2e4b14027460c0f3c97145862da2a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818380"
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="68fe0-102">XPathNavigator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="68fe0-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="68fe0-103">La clase <xref:System.Xml.XPath.XPathNavigator> proporciona acceso aleatorio de solo lectura a los datos y está diseñada para ser utilizada como una entrada para XSLT (Extensible Stylesheet Language for Transformations).</span><span class="sxs-lookup"><span data-stu-id="68fe0-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="68fe0-104">Se implementa en <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, y <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="68fe0-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="68fe0-105"><xref:System.Xml.XPath.XPathNavigator> se basa en el modelo de datos de World Wide Web Consortium (W3C) tal y como se describe en la sección 5 de la recomendación del lenguage de rutas XML (XPath).</span><span class="sxs-lookup"><span data-stu-id="68fe0-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="68fe0-106"><xref:System.Xml.XPath.XPathNavigator> define un modelo de cursor sobre cualquier almacén y proporciona rápidas consultas XPath de solo lectura sobre cualquier almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="68fe0-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="68fe0-107"><xref:System.Xml.XPath.XPathNavigator> también es la clase utilizada para iterar por fragmentos de árboles de resultados.</span><span class="sxs-lookup"><span data-stu-id="68fe0-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="68fe0-108">La API le permite obtener información del nodo actual del almacén y moverse entre los nodos conectados.</span><span class="sxs-lookup"><span data-stu-id="68fe0-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="68fe0-109"><xref:System.Xml.XPath.XPathNavigator> es el modelo de estilo de cursor que realiza exploraciones transversales de un almacén mediante un conjunto de métodos **Move**.</span><span class="sxs-lookup"><span data-stu-id="68fe0-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="68fe0-110"><xref:System.Xml.XPath.XPathNavigator> siempre se sitúa en un nodo.</span><span class="sxs-lookup"><span data-stu-id="68fe0-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="68fe0-111">Los métodos **Move** que presentan errores dejan <xref:System.Xml.XPath.XPathNavigator> sin modificar.</span><span class="sxs-lookup"><span data-stu-id="68fe0-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="68fe0-112"><xref:System.Xml.XPath.XPathNavigator> también es la clase utilizada para iterar por fragmentos de árboles de resultados.</span><span class="sxs-lookup"><span data-stu-id="68fe0-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="68fe0-113">En el código de ejemplo siguiente se crea un fragmento de árbol de resultados dentro de una hoja de estilos mediante una llamada a la función con el parámetro `fragment` que contiene XML.</span><span class="sxs-lookup"><span data-stu-id="68fe0-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="68fe0-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="68fe0-114">test.xsl</span></span>  
  
```xml  
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
  
## <a name="testxml"></a><span data-ttu-id="68fe0-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="68fe0-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="68fe0-116">En el siguiente ejemplo de código se utiliza la hoja de estilos **test.xsl** y los datos de entrada **test.xml**.</span><span class="sxs-lookup"><span data-stu-id="68fe0-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="68fe0-117">Salida</span><span class="sxs-lookup"><span data-stu-id="68fe0-117">Output</span></span>  
 <span data-ttu-id="68fe0-118">El resultado de la transformación se encuentra en el archivo **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="68fe0-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="68fe0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="68fe0-119">See also</span></span>

- [<span data-ttu-id="68fe0-120">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="68fe0-120">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
