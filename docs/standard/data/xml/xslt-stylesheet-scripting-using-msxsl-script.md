---
title: Escritura de scripts de hojas de estilos XSLT mediante <msxsl:script>
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 60e2541b-0cea-4b2e-a4fa-85f4c50f1bef
ms.openlocfilehash: 9bf57e0f74a353fb6512a24214e9479c1d813aab
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160214"
---
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a>Escritura de scripts de hojas de estilos XSLT mediante \<msxsl:script>
Esta clase <xref:System.Xml.Xsl.XslTransform> admite scripts incrustados mediante el elemento `script`.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Esta clase <xref:System.Xml.Xsl.XslTransform> admite scripts incrustados mediante el elemento `script`. Cuando se carga la hoja de estilos, las funciones definidas se compilan en el lenguaje intermedio de Microsoft (MSIL) ya que se incluyen en una definición de clase y no se produce pérdida alguna de rendimiento.  
  
 A continuación se define el elemento `<msxsl:script>`:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 donde `msxsl` es un prefijo enlazado al espacio de nombres `urn:schemas-microsoft-com:xslt`.  
  
 El atributo `language` no es obligatorio, pero si se especifica, su valor deberá ser uno de los siguientes: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic` o `CSharp`. Si no se especifica, el lenguaje predeterminado es JScript. `language-name` no distingue entre mayúsculas y minúsculas, entonces 'JavaScript' y 'javascript' son equivalentes.  
  
 El atributo `implements-prefix` es obligatorio. Este atributo se utiliza para declarar un espacio de nombres y asociarlo con el bloque del script. El valor de este atributo es el prefijo que representa el espacio de nombres. Este espacio de nombres puede definirse en cualquier parte de la hoja de estilos.  
  
 Puesto que el elemento `msxsl:script` pertenece al espacio de nombres `urn:schemas-microsoft-com:xslt`, la hoja de estilos debe incluir la declaración del espacio de nombres `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.  
  
 Si el llamador del script no tiene permiso de acceso a <xref:System.Security.Permissions.SecurityPermissionFlag>, el script de una hoja de estilos no se compilará y la llamada a <xref:System.Xml.Xsl.XslTransform.Load%2A> producirá errores.  
  
 Si el llamador tiene permiso `UnmanagedCode`, el script se compilará, pero las operaciones permitidas dependen de la evidencia suministrada en tiempo de carga.  
  
 Si utiliza uno de los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que toman <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator> para cargar la hoja de estilos, tendrá que utilizar la sobrecarga <xref:System.Xml.Xsl.XslTransform.Load%2A> que toma un parámetro <xref:System.Security.Policy.Evidence> como uno de sus argumentos. Para proporcionar evidencia, el llamador debe tener permiso <xref:System.Security.Permissions.SecurityPermissionFlag> para suministrar `Evidence` al ensamblado de scripts. Si el llamador no dispone de este permiso, puede establecer el parámetro `Evidence` en `null`. Esto hace que la función <xref:System.Xml.Xsl.XslTransform.Load%2A> produzca errores si encuentra el script. Se considera que el permiso `ControlEvidence` es un permiso muy eficaz que solo debería garantizarse al código de plena confianza.  
  
 Para obtener la evidencia desde el ensamblado, utilice `this.GetType().Assembly.Evidence`. Para obtener evidencia de un identificador de recurso uniforme (URI), utilice `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.  
  
 Si utiliza métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que toman <xref:System.Xml.XmlResolver> pero no `Evidence`, la zona de seguridad del ensamblado toma como valor predeterminado Plena confianza. Para más información, vea <xref:System.Security.SecurityZone> y [Conjuntos de permisos con nombre](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).  
  
 Las funciones se pueden declarar dentro del elemento `msxsl:script`. La tabla siguiente muestra los espacios de nombres que se admiten de forma predeterminada. Es posible utilizar clases fuera de los espacios de nombres enumerados. Sin embargo, el nombre de las clases debe estar completo.  
  
|Espacios de nombres predeterminados|Descripción|  
|------------------------|-----------------|  
|Sistema|Clase del sistema.|  
|System.Collection|Clases de colección|  
|System.Text|Clases de texto.|  
|System.Text.RegularExpressions|Clases de expresión regular.|  
|System.Xml|Clases XML básicas|  
|System.Xml.Xsl|Clases XSLT|  
|System.Xml.Xpath|Clases XML Path Language (XPath).|  
|Microsoft.VisualBasic|Clases para scripts de Microsoft Visual Basic.|  
  
 Cuando se declara una función, está contenida en un bloque de scripts. Las hojas de estilos pueden contener varios bloques de scripts que funcionan independientemente unos de otros. Esto significa que si se ejecuta código desde un bloque de scripts, no podrá llamar a una función definida en otro bloque a menos que se haya declarado en el mismo espacio de nombres y con el mismo lenguaje de scripts. Puesto que cada bloque de script puede estar en su propio lenguaje, y el bloque se analiza de acuerdo con las reglas de gramática de dicho analizador de lenguaje, deberá utilizar la sintaxis correcta para el lenguaje que esté siendo utilizado. Por ejemplo, en un bloque de scripts de C#, es erróneo utilizar un nodo de comentario de XML `<!-- an XML comment -->`.  
  
 Los argumentos proporcionados y los valores devueltos definidos en las funciones del script deben ser de los tipos XPath o XSLT del W3C. En la siguiente tabla se muestran los tipos correspondientes del W3C, las clases de .NET Framework equivalentes (tipo) y si el tipo del W3C es un tipo de XPath o un tipo de XSLT.  
  
|Tipo|Clase equivalente .NET Framework (tipo)|Tipo de XPath o tipo XSLT|  
|----------|----------------------------------------------|-----------------------------|  
|String|System.String|XPath|  
|Booleano|System.Boolean|XPath|  
|número|System.Double|XPath|  
|Fragmento del árbol de resultados|System.Xml.XPath.XPathNavigator|XSLT|  
|Conjunto de nodos|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Si la función de script utiliza uno de los siguientes tipos numéricos: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single o Decimal, se convierten obligatoriamente en Double, que se asigna a un número de tipo W3C XPath. El resto de los tipos se convierten obligatoriamente en tipos String con el método `ToString`.  
  
 Si la función del script utiliza un tipo distinto a los mencionados anteriormente o si no se compila al cargar la hoja de estilos en el objeto <xref:System.Xml.Xsl.XslTransform>, se inicia una excepción.  
  
 Al utilizar el elemento `msxsl:script`, se recomienda encarecidamente que el script, independientemente del lenguaje, se coloque dentro de una sección CDATA. Por ejemplo, en el código XML siguiente se muestra la plantilla de la sección CDATA donde se coloca el código.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 Se recomienda encarecidamente que todo el contenido de scripts se coloque en una sección CDATA porque existe la posibilidad de que los operadores, identificadores o delimitadores de un lenguaje determinado se interpreten erróneamente como XML. En el ejemplo siguiente se demuestra el uso del operador lógico AND en un script.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 De esta forma se inicia una excepción debido a que no se establece una secuencia de escape para el carácter Y comercial (&amp;). Este documento se carga como XML y no se aplica un tratamiento especial al texto que hay entre las etiquetas del elemento `msxsl:script`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza un script incrustado para calcular la longitud de una circunferencia dado su radio.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "calc.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XmlTextWriter to output to the console.
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
    writer.Formatting = Formatting.Indented  
  
    'Transform the file.  
    xslt.Transform(doc, Nothing, writer, Nothing)  
    writer.Close()  
  End Sub
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "calc.xsl";  
  
   public static void Main()  
   {  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XmlTextWriter to output to the console.
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting = Formatting.Indented;  
  
    //Transform the file.  
    xslt.Transform(doc, null, writer, null);  
    writer.Close();  
  }  
}  
```  
  
## <a name="input"></a>Entrada  
 number.xml  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>  
```  
  
 calc.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
    xmlns:user="urn:my-scripts">  
  
  <msxsl:script language="C#" implements-prefix="user">  
     <![CDATA[  
     public double circumference(double radius)  
     {  
       double pi = 3.14;  
       double circ = pi*radius*2;  
       return circ;  
     }  
      ]]>  
   </msxsl:script>  
  
  <xsl:template match="data">
  <circles>  
  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="user:circumference(radius)"/>
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Salida  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>
```  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
