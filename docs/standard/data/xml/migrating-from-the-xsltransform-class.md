---
title: Migración desde la clase XslTransform
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
ms.openlocfilehash: b441e23b13983a0fdb54b7785e249a04bf1407c8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830212"
---
# <a name="migrating-from-the-xsltransform-class"></a>Migración desde la clase XslTransform

En la versión de Visual Studio 2005 se ha rediseñado la arquitectura XSLT. La clase <xref:System.Xml.Xsl.XslTransform> se reemplazó por la clase <xref:System.Xml.Xsl.XslCompiledTransform>.

En las siguientes secciones se describen algunas de las principales diferencias existentes entre las clases <xref:System.Xml.Xsl.XslCompiledTransform> y <xref:System.Xml.Xsl.XslTransform>.

## <a name="performance"></a>Rendimiento

La clase <xref:System.Xml.Xsl.XslCompiledTransform> incluye muchas mejoras del rendimiento. El nuevo procesador XSLT compila la hoja de estilos XSLT en un formato intermedio común, que es similar a lo que hace Common Language Runtime (CLR) para otros lenguajes de programación. Una vez compilada la hoja de estilos, se puede almacenar en caché y volver a utilizar.

La clase <xref:System.Xml.Xsl.XslCompiledTransform> también incluye otras optimizaciones que hacen que sea mucho más rápida que la clase <xref:System.Xml.Xsl.XslTransform>.

> [!NOTE]
> Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación. Esto se debe a que el archivo XSLT debe compilarse antes de cargarse. Para más información, vea la entrada de blog siguiente: [XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (¿Es más lento XslCompiledTransform que XslTransform?)

## <a name="security"></a>Seguridad

De forma predeterminada, la clase <xref:System.Xml.Xsl.XslCompiledTransform> deshabilita la compatibilidad para la función XSLT `document()` y los scripts incrustados. Para habilitar estas características, se puede crear un objeto <xref:System.Xml.Xsl.XsltSettings> con las características habilitadas y pasarlo al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>. El siguiente ejemplo muestra cómo habilitar los scripts y cómo realizar una transformación XSLT.

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

Para obtener más información, vea [Consideraciones de seguridad de XSLT](xslt-security-considerations.md).

## <a name="new-features"></a>Características nuevas

### <a name="temporary-files"></a>Archivos temporales

En ocasiones, durante el procesamiento XSLT se generan archivos temporales. Si una hoja de estilos contiene bloques de scripts, o si se ha compilado con la opción de depuración, se crearán archivos temporales en la carpeta %TEMP%. Es posible que en algunos casos no se eliminen algunos archivos temporales por cuestión de tiempo. Por ejemplo, si los archivos están siendo utilizados actualmente por AppDomain o por el depurador, el finalizador del objeto <xref:System.CodeDom.Compiler.TempFileCollection> no será capaz de eliminarlos.

La propiedad <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> se puede utilizar para realizar una limpieza adicional, con el fin de asegurarse de que se eliminan todos los archivos temporales del cliente.

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a>Compatibilidad con el elemento xsl:output y con XmlWriter

La clase <xref:System.Xml.Xsl.XslTransform> ignora la configuración de `xsl:output` cuando la salida de una transformación se envía a un objeto <xref:System.Xml.XmlWriter>. La clase <xref:System.Xml.Xsl.XslCompiledTransform> tiene una propiedad <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> que devuelve un objeto <xref:System.Xml.XmlWriterSettings> que contiene la información de salida resultado del elemento `xsl:output` perteneciente a la hoja de estilos. El objeto <xref:System.Xml.XmlWriterSettings> se utiliza para crear un objeto <xref:System.Xml.XmlWriter> con la configuración correcta, el cual se puede pasar al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. El siguiente código escrito en C# ilustra este tipo de funcionamiento:

```csharp
// Create the XslTransform object and load the style sheet.
XslCompiledTransform xslt = new XslCompiledTransform();
xslt.Load(stylesheet);

// Load the file to transform.
XPathDocument doc = new XPathDocument(filename);

// Create the writer.
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);

// Transform the file and send the output to the console.
xslt.Transform(doc, writer);
writer.Close();
```

### <a name="debug-option"></a>Opción de depuración

La clase <xref:System.Xml.Xsl.XslCompiledTransform> puede generar información de depuración, lo que le permite depurar la hoja de estilos con el depurador de Microsoft Visual Studio. Vea <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29> para obtener más información.

## <a name="behavioral-differences"></a>Diferencias de funcionamiento

### <a name="transforming-to-an-xmlreader"></a>Transformar en un XmlReader

La clase <xref:System.Xml.Xsl.XslTransform> dispone de numerosas sobrecargas de Transform, las cuales devuelven los resultados de la transformación como un objeto <xref:System.Xml.XmlReader>. Se pueden utilizar dichas sobrecargas para cargar los resultados de la transformación en una representación en memoria (como un <xref:System.Xml.XmlDocument> o un <xref:System.Xml.XPath.XPathDocument>) sin incurrir en una sobrecarga del proceso de serialización o deserialización del árbol XML resultante. El siguiente código escrito en C# nuestra cómo cargar los resultados de la transformación en un objeto <xref:System.Xml.XmlDocument>.

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

La clase <xref:System.Xml.Xsl.XslCompiledTransform> no admite la posibilidad de realizar una transformación en un objeto <xref:System.Xml.XmlReader>. Sin embargo, puede hacer algo muy parecido si utiliza el método <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> para cargar el árbol XML resultante directamente desde un <xref:System.Xml.XmlWriter>. El siguiente código escrito en C# muestra cómo llevar a cabo la misma tarea utilizando <xref:System.Xml.Xsl.XslCompiledTransform>.

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a>Comportamiento discrecional

La recomendación de la versión 1.0 de las transformaciones XLT (XSLT) del W3C incluye áreas en las que el proveedor de las implementaciones puede decidir cómo controlar una situación. Estas áreas se consideran comportamientos discrecionales. Existen numerosas áreas en las que <xref:System.Xml.Xsl.XslCompiledTransform> se comporta de manera distinta a la clase <xref:System.Xml.Xsl.XslTransform>. Para más información, vea [Errores XSLT recuperables](recoverable-xslt-errors.md).

### <a name="extension-objects-and-script-functions"></a>Objetos de extensión y funciones de scripts

<xref:System.Xml.Xsl.XslCompiledTransform> introduce dos nuevas restricciones relativas al uso de funciones de script:

- Desde las expresiones XPath solo es posible llamar a métodos públicos.

- Las sobrecargas se pueden distinguir unas de otras en función del número de argumentos. Si existe más de una sobrecarga con el mismo número de argumentos, se producirá una excepción.

En <xref:System.Xml.Xsl.XslCompiledTransform> se produce un enlace (búsqueda de nombre de método) con las funciones del script en el tiempo de compilación y es posible que las hojas de estilos que habían funcionado con XslTransform generen una excepción si se cargan con <xref:System.Xml.Xsl.XslCompiledTransform>.

<xref:System.Xml.Xsl.XslCompiledTransform> admiten la posibilidad de contener elementos secundarios `msxsl:using` y `msxsl:assembly` dentro del elemento `msxsl:script`. Los elementos `msxsl:using` y `msxsl:assembly` permiten declarar espacios de nombres y ensamblados adicionales que se utilizarán en el bloque del script. Vea [Bloques de scripts con msxsl:script](script-blocks-using-msxsl-script.md) para obtener más información.

<xref:System.Xml.Xsl.XslCompiledTransform> no permite el uso de objetos de extensión que tengan múltiples sobrecargas con el mismo número de argumentos.

### <a name="msxml-functions"></a>Funciones MSXML

Se ha agregado a la clase <xref:System.Xml.Xsl.XslCompiledTransform> compatibilidad con funciones MSXML adicionales. En la siguiente lista se describe toda la funcionalidad nueva o mejorada:

- msxsl:node-set: <xref:System.Xml.Xsl.XslTransform> requiere que el argumento de la función [node-set Function](/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) sea un fragmento del árbol resultante. La clase <xref:System.Xml.Xsl.XslCompiledTransform> no tiene este requisito.

- msxsl:version: está función se admite en <xref:System.Xml.Xsl.XslCompiledTransform>.

- Funciones de extensión de XPath: las funciones [ms:string-compare](/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc](/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri](/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name](/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number](/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date](/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) y [ms:format-time](/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)) ya son compatibles.

- Funciones de extensión de XPath relacionadas con esquemas: estas funciones no se admiten de forma nativa en <xref:System.Xml.Xsl.XslCompiledTransform>. No obstante, es posible implementarlas como funciones de extensión.

## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](xslt-transformations.md)
- [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md)
