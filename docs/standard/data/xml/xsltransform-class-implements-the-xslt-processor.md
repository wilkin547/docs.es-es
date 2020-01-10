---
title: La clase XslTransform implementa el procesador XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
ms.openlocfilehash: 73a432db9a3fcb6587184e27e6dfe9ba49010e92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709613"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a>La clase XslTransform implementa el procesador XSLT

> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.

La clase <xref:System.Xml.Xsl.XslTransform> es un procesador XSLT que implementa la recomendación de las transformaciones XSL (XSLT) versión 1.0. El método <xref:System.Xml.Xsl.XslTransform.Load%2A> localiza y lee hojas de estilos y el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> transforma el documento de origen determinado. Cualquier almacén que implemente la interfaz <xref:System.Xml.XPath.IXPathNavigable> puede utilizarse como documento de origen para la transformación <xref:System.Xml.Xsl.XslTransform>. .NET Framework implementa actualmente la interfaz <xref:System.Xml.XPath.IXPathNavigable> en <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> y <xref:System.Xml.XPath.XPathDocument>, de manera que todos estos pueden usarse como documento de origen de entrada para una transformación.

El objeto <xref:System.Xml.Xsl.XslTransform> en .NET Framework solamente admite la especificación XSLT 1.0, definida con el siguiente espacio de nombres:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

La hoja de estilos puede cargarse utilizando el método <xref:System.Xml.Xsl.XslTransform.Load%2A>, desde cualquiera de las clases siguientes:

- XPathNavigator

- XmlReader

- Una cadena que representa una dirección URL

Existe un método <xref:System.Xml.Xsl.XslTransform.Load%2A> distinto para cada una de las clases de entrada citadas anteriormente. Algunos métodos toman una combinación de una de estas clases y la clase <xref:System.Xml.XmlResolver> como argumentos. <xref:System.Xml.XmlResolver> localiza los recursos a los que hace referencia `<xsl:import>` o `<xsl:include>` y que se encuentran en la hoja de estilos. Los métodos siguientes toman una cadena <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator> como entrada.

```vb
Overloads Public Sub Load(String)
```

```csharp
public void Load(string);
```

```vb
Overloads Public Sub Load(String, XmlResolver)
```

```csharp
public void Load(string, XmlResolver);
```

```vb
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)
```

```csharp
public void Load(XmlReader, XmlResolver, Evidence);
```

```vb
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)
```

```csharp
public void Load(XPathNavigator, XmlResolver, Evidence);
```

La mayoría de los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que se han mostrado antes toman un <xref:System.Xml.XmlResolver> como parámetro. <xref:System.Xml.XmlResolver> se utiliza para cargar la hoja de estilos y cualquier hoja u hojas de estilos a las que se haga referencia en los elementos xsl:import y xsl:include.

La mayoría de los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> toman también Evidence como parámetro. El parámetro evidence es el <xref:System.Security.Policy.Evidence> que está asociado con la hoja de estilos. El nivel de seguridad de la hoja de estilos afecta al nivel de seguridad de cualquier recurso posterior al que haga referencia la hoja de estilos como, por ejemplo, los scripts que contenga, cualquier función `document()` que utilice y cualquier objeto de extensión utilizado por <xref:System.Xml.Xsl.XsltArgumentList>.

Si la hoja de estilos se ha cargado utilizando un método <xref:System.Xml.Xsl.XslTransform.Load%2A> que contiene un parámetro URL y no hay ninguna evidencia, la evidencia de la hoja de estilos se calcula combinando la dirección URL dada con su sitio y zona.

Si no se proporciona ningún identificador URI, la hoja de estilos se convierte en un parámetro de plena confianza. No cargue hojas de estilos desde orígenes que no sean de confianza ni agregue objetos de extensión que no sean de confianza en <xref:System.Xml.Xsl.XsltArgumentList>.

Para obtener más información sobre niveles de seguridad y evidencia y sobre cómo afectan a los scripts, vea [Hojas de estilos XSLT Scripting mediante \<msxsl: script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md). Para obtener información sobre los niveles de seguridad y evidencia y cómo afectan a los objetos de extensión, vea [XsltArgumentList para parámetros Stylesheet y objetos de extensión](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).

Para obtener más información sobre niveles de seguridad y evidencia y sobre cómo afectan a la función `document()`, vea [Resolver hojas de estilos XSLT y documentos externos](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).

Una hoja de estilos se puede suministrar con varios parámetros de entrada. Asimismo puede llamar también a funciones en objetos de extensión. Tanto los parámetros como los objetos de extensión se suministran a la hoja de estilos mediante la clase <xref:System.Xml.Xsl.XsltArgumentList>. Para obtener más información sobre <xref:System.Xml.Xsl.XsltArgumentList>, consulte <xref:System.Xml.Xsl.XsltArgumentList>.

## <a name="recommended-secure-use-of-xsltransform-class"></a>Uso seguro recomendado de la clase XslTransform

Los privilegios de seguridad de la hoja de estilos dependen de la evidencia proporcionada. En la siguiente tabla se resume la ubicación de la hoja de estilos y se ofrece una explicación del tipo de evidencia que hay que dar.

- La hoja de estilos XSLT no tiene referencias externas o proviene de un código base en el que confía.

  - Proporcione la evidencia desde el ensamblado:

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- La hoja de estilos XSLT proviene de un código fuente exterior. Se conoce el origen del código fuente y existe un identificador URI que se puede comprobar.

  - Cree la evidencia utilizando el identificador URI.

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- La hoja de estilos XSLT proviene de un código fuente exterior. Se desconoce el origen del código fuente.

  - Establezca la evidencia en `null`. No se procesan los bloques de scripts, no se admite la función `document()` de XSLT y no están permitidos los objetos de extensión privilegiada.

    Además, también puede establecer el parámetro `resolver` en una referencia `null`, lo que garantiza que los elementos `xsl:import` y `xsl:include` no se procesan.

- La hoja de estilos XSLT proviene de un código fuente exterior. Se desconoce el origen del código fuente, pero es necesaria la compatibilidad con los scripts.

  - Solicite la evidencia al llamador.

## <a name="transformation-of-xml-data"></a>Transformación de datos XML

Una vez cargada la hoja de estilos, la transformación comienza con la llamada a uno de los métodos <xref:System.Xml.Xsl.XslTransform.Transform%2A> y con el suministro de un documento de origen de entrada. El método <xref:System.Xml.Xsl.XslTransform.Transform%2A> se sobrecarga para proporcionar diferentes salidas de transformación. La transformación puede producir los siguientes formatos de salida:

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- Dirección URL de cadena de archivo

Este último formato, la dirección URL de cadena, proporciona una situación utilizada comúnmente en la transformación de un documento de entrada que se encuentra en una dirección URL y escribe el documento en la dirección URL de salida. Este método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es útil para cargar un documento XML desde un archivo, realizar la transformación XSLT y escribir la salida en un archivo. De esta forma se evita tener que crear y cargar el documento de origen de entrada y después escribirlo en una secuencia de archivo. En el ejemplo de código siguiente se muestra este uso del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> con la dirección URL de cadena como entrada y como salida:

```vb
Dim xsltransform As XslTransform = New XslTransform()
xsltransform.Load("favorite.xsl")
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)
```

```csharp
XslTransform xsltransform = new XslTransform();
xsltransform.Load("favorite.xsl");
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);
```

## <a name="transforming-a-section-of-an-xml-document"></a>Transformar una sección de un documento XML

Las transformaciones se aplican al documento en su totalidad. En otras palabras, si se pasa un nodo distinto del nodo raíz del documento, esto no evita que el proceso de transformación pueda obtener acceso a todos los nodos del documento cargado. Para transformar un fragmento del árbol de resultados, habrá que crear un <xref:System.Xml.XmlDocument> que contenga el fragmento de árbol de resultados y pasar ese <xref:System.Xml.XmlDocument> al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>. En el ejemplo siguiente se realiza una transformación en un fragmento de árbol de resultados.

```vb
Dim xslt As New XslTransform()
xslt.Load("print_root.xsl")
Dim doc As New XmlDocument()
doc.Load("library.xml")
' Create a new document containing just the result tree fragment.
Dim testNode As XmlNode = doc.DocumentElement.FirstChild
Dim tmpDoc As New XmlDocument()
tmpDoc.LoadXml(testNode.OuterXml)
' Pass the document containing the result tree fragment
' to the Transform method.
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)
```

```csharp
XslTransform xslt = new XslTransform();
xslt.Load("print_root.xsl");
XmlDocument doc = new XmlDocument();
doc.Load("library.xml");
// Create a new document containing just the result tree fragment.
XmlNode testNode = doc.DocumentElement.FirstChild;
XmlDocument tmpDoc = new XmlDocument();
tmpDoc.LoadXml(testNode.OuterXml);
// Pass the document containing the result tree fragment
// to the Transform method.
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");
xslt.Transform(tmpDoc, null, Console.Out, null);
```

En el ejemplo se usan los archivos Library. XML y print_root. xsl como entrada y se genera lo siguiente en la consola:

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

library.xml

```xml
<library>
  <book genre='novel' ISBN='1-861001-57-5'>
     <title>Pride And Prejudice</title>
  </book>
  <book genre='novel' ISBN='1-81920-21-2'>
     <title>Hook</title>
  </book>
</library>
```

print_root.xsl

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a>Migración de XSLT de la versión 1.0 a la versión 1.1 de .NET Framework

La tabla siguiente muestra los métodos obsoletos de la versión 1.0 de .NET Framework y los nuevos métodos de la versión 1.1 de .NET Framework para el método <xref:System.Xml.Xsl.XslTransform.Load%2A>. Los nuevos métodos permiten limitar los permisos de la hoja de estilos especificando la evidencia.

|Métodos Load obsoletos de la versión 1.0 de .NET Framework|Métodos Load de reemplazo de la versión 1.1 de .NET Framework|
|------------------------------------------------------|---------------------------------------------------------|
|Load(entrada XPathNavigator);<br /><br /> Load(entrada XPathNavigator, resolución XmlResolver);|Load(hoja de estilos XPathNavigator, resolución XmlResolver, evidencia Evidence);|
|Load(hoja de estilos IXPathNavigable);<br /><br /> Load(hoja de estilos IXPathNavigable, resolución XmlResolver);|Load(hoja de estilos IXPathNavigable, resolución XmlResolver, evidencia Evidence);|
|Load(hoja de estilos XmlReader);<br /><br /> Load(hoja de estilos XmlReader, resolución XmlResolver);|Load(hoja de estilos XmlReader, resolución XmlResolver, evidencia Evidence);|

La tabla siguiente muestra los métodos obsoletos y nuevos <xref:System.Xml.Xsl.XslTransform.Transform%2A>. Los nuevos métodos toman un objeto <xref:System.Xml.XmlResolver>.

|Métodos Transform obsoletos de la versión 1.0 de .NET Framework|Métodos Transform de reemplazo de la versión 1.1 de .NET Framework|
|-----------------------------------------------------------|--------------------------------------------------------------|
|XmlReader Transform(entrada XPathNavigator, argumentos XsltArgumentList)|XmlReader Transform(entrada XPathNavigator, argumentos XsltArgumentList, resolución XmlResolver)|
|XmlReader Transform(entrada IXPathNavigable, argumentos XsltArgumentList)|XmlReader Transform(entrada IXPathNavigable, argumentos XsltArgumentList, resolución XmlResolver)|
|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida XmlWriter)|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida XmlWriter, resolución XmlResolver)|
|Void Transform(entrada IXPathNavigable, argumentos XsltArgumentList, salida XmlWriter)|Void Transform(entrada IXpathNavigable, argumentos XsltArgumentList, salida XmlWriter, resolución XmlResolver)|
|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida TextWriter)|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida TextWriter, resolución XmlResolver)|
|Void Transform(entrada IXPathNavigable, argumentos XsltArgumentList, salida TextWriter)|Void Transform(entrada IXPathNavigable, argumentos XsltArgumentList, salida TextWriter, resolución XmlResolver)|
|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida Stream)|Void Transform(entrada XPathNavigator, argumentos XsltArgumentList, salida Stream, resolución XmlResolver)|
|Void Transform(entrada IXPathNavigable, argumentos XsltArgumentList, salida Stream)|Void Transform(entrada IXPathNavigable, argumentos XsltArgumentList, salida Stream, resolución XmlResolver)|
|Void Transform(entrada String, salida String);|Void Transform(entrada String, salida String, resolución XmlResolver);|

La propiedad <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> está obsoleta en .NET Framework versión 1.1. En lugar de esta propiedad, utilice las nuevas sobrecargas <xref:System.Xml.Xsl.XslTransform.Transform%2A> que toman un objeto <xref:System.Xml.XmlResolver>.

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XslTransform>
- [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDataDocument en XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
