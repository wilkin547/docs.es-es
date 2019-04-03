---
title: Transformaciones XSLT con la clase XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db10dda3cbb328cd143afa48e300588ccc7667a6
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463077"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="e055c-102">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="e055c-102">XSLT Transformations with the XslTransform Class</span></span>

> [!NOTE]
> <span data-ttu-id="e055c-103">La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e055c-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="e055c-104">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="e055c-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="e055c-105">Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e055c-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="e055c-106">El objetivo de XSLT es transformar el contenido de un documento XML de origen en otro documento que sea diferente en formato o estructura (por ejemplo, para transformar XML en HTML para su utilización en un sitio web o transformarlo en un documento que contenga solo los campos requeridos por una aplicación).</span><span class="sxs-lookup"><span data-stu-id="e055c-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="e055c-107">Este proceso de transformación se especifica en la [recomendación de la versión 1.0 de XSLT](https://www.w3.org/TR/1999/REC-xslt-19991116) de W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="e055c-107">This transformation process is specified by the World Wide Web Consortium (W3C)[XSLT version 1.0 recommendation](https://www.w3.org/TR/1999/REC-xslt-19991116).</span></span> <span data-ttu-id="e055c-108">En [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], la clase <xref:System.Xml.Xsl.XslTransform>, que se encuentra en el espacio de nombres <xref:System.Xml.Xsl>, es el procesador XSLT que implementa la funcionalidad de esta especificación.</span><span class="sxs-lookup"><span data-stu-id="e055c-108">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="e055c-109">Un reducido número de características de la recomendación de XSLT versión 1.0 del W3C no se han implementado y se enumeran en [Resultados de XslTransform](outputs-from-an-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="e055c-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="e055c-110">En la ilustración siguiente se muestra la arquitectura de transformación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e055c-110">The following figure shows the transformation architecture of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>

## <a name="overview"></a><span data-ttu-id="e055c-111">Información general</span><span class="sxs-lookup"><span data-stu-id="e055c-111">Overview</span></span>

![Diagrama que muestra la arquitectura de transformación de XSLT.](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

<span data-ttu-id="e055c-113">La recomendación de XSLT utiliza XPath para seleccionar componentes de un documento XML. XPath es un lenguaje de consulta utilizado para navegar por los nodos de un árbol de documentos.</span><span class="sxs-lookup"><span data-stu-id="e055c-113">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="e055c-114">Tal como se muestra en el diagrama, la implementación [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de XPath se utiliza para seleccionar partes de XML almacenadas en varias clases, como <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument>, y <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="e055c-114">As shown in the diagram, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="e055c-115"><xref:System.Xml.XPath.XPathDocument> es un almacén de datos optimizado de XSLT, y cuando se utiliza con <xref:System.Xml.Xsl.XslTransform>, proporciona transformaciones XSLT de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e055c-115">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>

<span data-ttu-id="e055c-116">En la tabla siguiente se enumeran las clases utilizadas comúnmente al trabajar con <xref:System.Xml.Xsl.XslTransform> y Xpath y su función.</span><span class="sxs-lookup"><span data-stu-id="e055c-116">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>

|<span data-ttu-id="e055c-117">Clase o interfaz</span><span class="sxs-lookup"><span data-stu-id="e055c-117">Class or Interface</span></span>|<span data-ttu-id="e055c-118">Función</span><span class="sxs-lookup"><span data-stu-id="e055c-118">Function</span></span>|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="e055c-119">API que proporciona un modelo de estilo de cursor para navegar por un almacén, junto con la compatibilidad con las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="e055c-119">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="e055c-120">No permite modificar el almacén subyacente.</span><span class="sxs-lookup"><span data-stu-id="e055c-120">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="e055c-121">Para realizar modificaciones, utilice la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e055c-121">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="e055c-122">Es una interfaz que proporciona un método `CreateNavigator` a <xref:System.Xml.XPath.XPathNavigator> para el almacén.</span><span class="sxs-lookup"><span data-stu-id="e055c-122">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="e055c-123">Permite modificar este documento.</span><span class="sxs-lookup"><span data-stu-id="e055c-123">It enables editing of this document.</span></span> <span data-ttu-id="e055c-124">Implementa <xref:System.Xml.XPath.IXPathNavigable>, que tiene en cuenta situaciones de modificación de documentos en las que son necesarias las transformaciones XSLT.</span><span class="sxs-lookup"><span data-stu-id="e055c-124">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="e055c-125">Para obtener más información, vea [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="e055c-125">For more information, see [XmlDocument Input to XslTransform](xmldocument-input-to-xsltransform.md).</span></span>|
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="e055c-126">Se deriva de <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e055c-126">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="e055c-127">Une los universos relacional y XML mediante la utilización de un <xref:System.Data.DataSet> para optimizar el almacenamiento de datos estructurados dentro del documento XML según las asignaciones especificadas en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e055c-127">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="e055c-128">Implementa <xref:System.Xml.XPath.IXPathNavigable>, que tiene en cuenta situaciones donde las transformaciones XSLT se pueden realizar sobre datos relacionales obtenidos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e055c-128">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="e055c-129">Para obtener más información, vea [Integración de XML con datos relacionales y ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span><span class="sxs-lookup"><span data-stu-id="e055c-129">For more information, see [XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span></span>|
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="e055c-130">Esta clase se ha optimizado para el procesamiento de <xref:System.Xml.Xsl.XslTransform> y consultas Xpath, y proporciona una caché de solo lectura y de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e055c-130">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="e055c-131">Implementa <xref:System.Xml.XPath.IXPathNavigable> y es el almacén preferido en las transformaciones XSLT.</span><span class="sxs-lookup"><span data-stu-id="e055c-131">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="e055c-132">Permite la navegación en conjuntos de nodos de XPath.</span><span class="sxs-lookup"><span data-stu-id="e055c-132">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="e055c-133">Todos los métodos de selección XPath en <xref:System.Xml.XPath.XPathNavigator> devuelven <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="e055c-133">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="e055c-134">Se pueden crear múltiples objetos <xref:System.Xml.XPath.XPathNodeIterator> en el mismo almacén y cada uno representa un conjunto de nodos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e055c-134">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|

## <a name="msxml-xslt-extensions"></a><span data-ttu-id="e055c-135">Extensiones MSXML XSLT</span><span class="sxs-lookup"><span data-stu-id="e055c-135">MSXML XSLT Extensions</span></span>

<span data-ttu-id="e055c-136">Las funciones `msxsl:script` y `msxsl:node-set` son las únicas extensiones XSLT de Microsoft XML Core Services (MSXML) compatibles con la clase <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="e055c-136">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

## <a name="example"></a><span data-ttu-id="e055c-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e055c-137">Example</span></span>

<span data-ttu-id="e055c-138">En el código de ejemplo siguiente se carga una hoja de estilos XSL, se lee un archivo denominado mydata.xml en <xref:System.Xml.XPath.XPathDocument> y se realiza la transformación de los datos en un archivo ficticio denominado myStyleSheet.xsl al enviar la salida con formato a la consola.</span><span class="sxs-lookup"><span data-stu-id="e055c-138">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.XPath
Imports System.Xml.Xsl

Public Class Sample
    Private filename As [String] = "mydata.xml"
    Private stylesheet As [String] = "myStyleSheet.xsl"

    Public Shared Sub Main()
        Dim xslt As New XslTransform()
        xslt.Load(stylesheet)
        Dim xpathdocument As New XPathDocument(filename)
        Dim writer As New XmlTextWriter(Console.Out)
        writer.Formatting = Formatting.Indented

        xslt.Transform(xpathdocument, Nothing, writer, Nothing)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.XPath;
using System.Xml.Xsl;

public class Sample 
{
    private const String filename = "mydata.xml";
    private const String stylesheet = "myStyleSheet.xsl";

    public static void Main()
    {
        XslTransform xslt = new XslTransform();
        xslt.Load(stylesheet);
        XPathDocument xpathdocument = new XPathDocument(filename);
        XmlTextWriter writer = new XmlTextWriter(Console.Out);
        writer.Formatting = Formatting.Indented;

        xslt.Transform(xpathdocument, null, writer, null);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e055c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e055c-139">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="e055c-140">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="e055c-140">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="e055c-141">Implementación de comportamientos discrecionales en la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="e055c-141">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [<span data-ttu-id="e055c-142">XPathNavigator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="e055c-142">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="e055c-143">XPathNodeIterator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="e055c-143">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="e055c-144">Entrada XPathDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="e055c-144">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="e055c-145">Entrada de XmlDataDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="e055c-145">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="e055c-146">Entrada de XmlDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="e055c-146">XmlDocument Input to XslTransform</span></span>](xmldocument-input-to-xsltransform.md)
