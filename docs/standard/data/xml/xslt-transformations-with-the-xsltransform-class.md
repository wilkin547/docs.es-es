---
title: Transformaciones XSLT con la clase XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
ms.openlocfilehash: 5f670fa5e83d1802496c0cc6972a7e3af7cae374
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709652"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a>Transformaciones XSLT con la clase XslTransform

> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.

El objetivo de XSLT es transformar el contenido de un documento XML de origen en otro documento que sea diferente en formato o estructura (por ejemplo, para transformar XML en HTML para su utilización en un sitio web o transformarlo en un documento que contenga solo los campos requeridos por una aplicación). Este proceso de transformación se especifica en la [recomendación de la versión 1.0 de XSLT](https://www.w3.org/TR/1999/REC-xslt-19991116) de W3C (World Wide Web Consortium). En .NET Framework, la clase <xref:System.Xml.Xsl.XslTransform>, que se encuentra en el espacio de nombres <xref:System.Xml.Xsl>, es el procesador XSLT que implementa la funcionalidad de esta especificación. Un reducido número de características de la recomendación de XSLT versión 1.0 del W3C no se han implementado y se enumeran en [Resultados de XslTransform](outputs-from-an-xsltransform.md). En la ilustración siguiente se muestra la arquitectura de transformación de .NET Framework.

## <a name="overview"></a>Información general del

![Diagrama que muestra la arquitectura de transformación de XSLT.](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

La recomendación de XSLT utiliza XPath para seleccionar componentes de un documento XML. XPath es un lenguaje de consulta utilizado para navegar por los nodos de un árbol de documentos. Como se muestra en el diagrama, la implementación .NET Framework de XPath se usa para seleccionar partes de XML almacenadas en varias clases, como <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> y <xref:System.Xml.XPath.XPathDocument>. <xref:System.Xml.XPath.XPathDocument> es un almacén de datos optimizado de XSLT, y cuando se utiliza con <xref:System.Xml.Xsl.XslTransform>, proporciona transformaciones XSLT de alto rendimiento.

En la tabla siguiente se enumeran las clases utilizadas comúnmente al trabajar con <xref:System.Xml.Xsl.XslTransform> y Xpath y su función.

|Clase o interfaz|Función|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|API que proporciona un modelo de estilo de cursor para navegar por un almacén, junto con la compatibilidad con las consultas XPath. No permite modificar el almacén subyacente. Para realizar modificaciones, utilice la clase <xref:System.Xml.XmlDocument>.|
|<xref:System.Xml.XPath.IXPathNavigable>|Es una interfaz que proporciona un método `CreateNavigator` a <xref:System.Xml.XPath.XPathNavigator> para el almacén.|
|<xref:System.Xml.XmlDocument>|Permite modificar este documento. Implementa <xref:System.Xml.XPath.IXPathNavigable>, que tiene en cuenta situaciones de modificación de documentos en las que son necesarias las transformaciones XSLT. Para obtener más información, vea [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md).|
|<xref:System.Xml.XmlDataDocument>|Se deriva de <xref:System.Xml.XmlDocument>. Une los universos relacional y XML mediante la utilización de un <xref:System.Data.DataSet> para optimizar el almacenamiento de datos estructurados dentro del documento XML según las asignaciones especificadas en el <xref:System.Data.DataSet>. Implementa <xref:System.Xml.XPath.IXPathNavigable>, que tiene en cuenta situaciones donde las transformaciones XSLT se pueden realizar sobre datos relacionales obtenidos en una base de datos. Para obtener más información, vea [Integración de XML con datos relacionales y ADO.NET](xml-integration-with-relational-data-and-adonet.md).|
|<xref:System.Xml.XPath.XPathDocument>|Esta clase se ha optimizado para el procesamiento de <xref:System.Xml.Xsl.XslTransform> y consultas Xpath, y proporciona una caché de solo lectura y de alto rendimiento. Implementa <xref:System.Xml.XPath.IXPathNavigable> y es el almacén preferido en las transformaciones XSLT.|
|<xref:System.Xml.XPath.XPathNodeIterator>|Permite la navegación en conjuntos de nodos de XPath. Todos los métodos de selección XPath en <xref:System.Xml.XPath.XPathNavigator> devuelven <xref:System.Xml.XPath.XPathNodeIterator>. Se pueden crear múltiples objetos <xref:System.Xml.XPath.XPathNodeIterator> en el mismo almacén y cada uno representa un conjunto de nodos seleccionado.|

## <a name="msxml-xslt-extensions"></a>Extensiones MSXML XSLT

Las funciones `msxsl:script` y `msxsl:node-set` son las únicas extensiones XSLT de Microsoft XML Core Services (MSXML) compatibles con la clase <xref:System.Xml.Xsl.XslTransform>.

## <a name="example"></a>Ejemplo

En el código de ejemplo siguiente se carga una hoja de estilos XSL, se lee un archivo denominado mydata.xml en <xref:System.Xml.XPath.XPathDocument> y se realiza la transformación de los datos en un archivo ficticio denominado myStyleSheet.xsl al enviar la salida con formato a la consola.

```vb
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

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XslTransform>
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
- [Implementación de comportamientos discrecionales en la clase XslTransform](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [XPathNavigator en transformaciones](xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDataDocument en XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md)
