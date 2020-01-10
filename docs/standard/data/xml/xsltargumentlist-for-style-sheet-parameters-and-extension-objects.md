---
title: XsltArgumentList para parámetros Stylesheet y objetos de extensión
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: 5cd733d557dabe66145fdbb848c473411d63c62b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709626"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a>XsltArgumentList para parámetros Stylesheet y objetos de extensión
La clase <xref:System.Xml.Xsl.XsltArgumentList> contiene parámetros Extensible Stylesheet Language for Transformations (XSLT) y objetos de extensión XSLT. Cuando se pasan al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> se puede invocar a estos parámetros y objetos de extensión desde hojas de estilos.  
  
> [!NOTE]
> Las clases <xref:System.Xml.Xsl.XslTransform> y <xref:System.Xml.Xsl.XsltArgumentList> están obsoletas en .NET Framework 2.0. Puede llevar a cabo transformaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 La clase <xref:System.Xml.Xsl.XsltArgumentList> contiene parámetros XSLT y objetos de extensión de XSLT. Cuando se pasan al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> se puede invocar a estos parámetros y objetos de extensión desde hojas de estilos.  
  
 A continuación se enumeran las ventajas de pasar un objeto en lugar de utilizar un script incrustado:  
  
- Proporciona una mejor encapsulación y reutilización de clases.  
  
- Permite que las hojas de estilos sean más pequeñas y facilita su mantenimiento.  
  
- Admite llamadas a métodos en clases que pertenecen a otros espacios de nombres distintos de los definidos dentro del conjunto de espacios de nombres admitidos por el sistema <xref:System>.  
  
- Permite que se pasen fragmentos de árboles de resultados a la hoja de estilos con el uso de <xref:System.Xml.XPath.XPathNodeIterator>.  
  
## <a name="xslt-style-sheet-parameters"></a>Parámetros de XSLT de hoja de estilos  
 Los parámetros XSLT se agregan a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>. En ese momento se asocian un nombre completo y un identificador de recursos de uniforme (URI) de espacio de nombres con el objeto del parámetro.  
  
 El objeto del parámetro debería corresponder al tipo World Wide Web Consortium (W3C). La tabla siguiente muestra los tipos W3C correspondientes, las clases de .NET Framework equivalentes (tipo) y si el tipo W3C es un tipo de lenguaje de ruta XML (XPath) o tipo XSLT.  
  
|Tipo W3C|Clase equivalente .NET Framework (tipo)|Tipo de XPath o tipo XSLT|  
|--------------|----------------------------------------------|-----------------------------|  
|Cadena|System.String|XPath|  
|Booleano|System.Boolean|XPath|  
|Número|System.Double|XPath|  
|Fragmento del árbol de resultados|System.Xml.XPath.XPathNavigator|XSLT|  
|Conjunto de nodos|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Si el objeto del parámetro no es una de las clases anteriores, se obliga a que sea Double o String, según corresponda. Los tipos Int16, UInt16, Int32, UInt32, Int64, UInt64, Single y Decimal se convierten obligatoriamente a Double. Todos los demás tipos se convierten obligatoriamente a String con el método `ToString`.  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a>Para utilizar el parámetro XSLT, el usuario debe seguir los pasos siguientes:  
  
1. Crear <xref:System.Xml.Xsl.XsltArgumentList> y añadir los objetos mediante <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.  
  
2. Llamar a los parámetros desde la hoja de estilos.  
  
3. Pasar <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> para crear un parámetro que almacena la fecha de descuento calculada. Para calcular la fecha de descuento se deben sumar 20 días a partir de la fecha del pedido.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public class Sample  
  
   Private Const filename As String = "order.xml"  
   Private Const stylesheet As String = "discount.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Calculate the discount date.  
    Dim today As DateTime = DateTime.Now  
    Dim d As DateTime = today.AddDays(20)  
    xslArg.AddParam("discount", "", d.ToString())  
  
    'Create an XmlTextWriter to handle the output.  
    Dim writer As XmlTextWriter = New XmlTextWriter("orderout.xml", Nothing)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
  
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
   private const String filename = "order.xml";  
   private const String stylesheet = "discount.xsl";  
  
   public static void Main() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Calculate the discount date.  
    DateTime today = DateTime.Now;  
    DateTime d = today.AddDays(20);  
    xslArg.AddParam("discount", "", d.ToString());  
  
    //Create an XmlTextWriter to handle the output.  
    XmlTextWriter writer = new XmlTextWriter("orderout.xml", null);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  }  
}  
```  
  
### <a name="input"></a>Input  
 order.xml  
  
```xml  
<!--Represents a customer order-->  
<order>  
  <book ISBN='10-861003-324'>  
    <title>The Handmaid's Tale</title>  
    <price>19.95</price>  
  </book>  
  <cd ISBN='2-3631-4'>  
    <title>Americana</title>  
    <price>16.95</price>  
  </cd>  
</order>  
```  
  
 discount.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:param name="discount"/>  
  <xsl:template match="/">  
    <order>  
      <xsl:variable name="sub-total" select="sum(//price)"/>  
      <total><xsl:value-of select="$sub-total"/></total>  
      15% discount if paid by: <xsl:value-of select="$discount"/>  
    </order>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a>Resultados  
  
```xml  
<order>  
   <total>36.9</total>   
   15% discount if paid by: 5/6/2001 5:01:15 PM   
</order>  
```  
  
## <a name="xslt-extension-objects"></a>Objetos de extensión de XSLT  
 Los objetos de extensión XSLT se añaden a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. En ese momento se asocian un nombre completo y un identificador URI de espacio de nombres con el objeto de extensión.  
  
 Cuando se agrega un objeto, el llamador de <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> debe ser de confianza total en la directiva de seguridad. Si el llamador es de confianza parcial, la adición producirá errores.  
  
 El hecho de que un objeto se agregue correctamente, no garantiza que la ejecución vaya a producirse correctamente. Cuando se llama al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, los permisos se calculan con la evidencia proporcionada durante la ejecución del método <xref:System.Xml.Xsl.XslTransform.Load%2A> y dicho conjunto de permisos se asigna a todo el proceso de transformación. Si un objeto de extensión intenta iniciar una acción que requiere permisos que no se han encontrado en el conjunto, se inicia una excepción.  
  
 Los tipos de datos devueltos desde los objetos de extensión pertenecen a uno de los cuatro tipos de datos básicos de Xpath: datos de tipo numérico, datos de tipo cadena, datos booleanos y conjuntos de nodos.  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a>Para utilizar objetos de extensión de XSLT, el usuario debe seguir los pasos siguientes:  
  
1. Crear <xref:System.Xml.Xsl.XsltArgumentList> y añadir el objeto de extensión mediante <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  
  
2. Invocar al objeto de extensión desde la hoja de estilos.  
  
3. Pasar <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se calcula la longitud de una circunferencia dado su radio.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "circle.xsl"  
  
   Public Shared Sub Main()  
        Dim test As Sample = New Sample  
   End Sub  
  
  Public Sub New()  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Add an object to calculate the circumference of the circle.  
    Dim obj As Calculate = New Calculate  
    xslArg.AddExtensionObject("urn:myObj", obj)  
  
    'Create an XmlTextWriter to output to the console.  
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
    writer.Close()  
  
  End Sub  
  
  'Calculates the circumference of a circle given the radius.  
  Public Class Calculate  
  
    Private circ As double = 0  
  
    Public Function Circumference(radius As Double) As Double  
       circ = Math.PI*2*radius  
       Return circ  
    End Function  
  End Class  
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
   private const String stylesheet = "circle.xsl";  
  
   public static void Main() {  
  
        Sample test = new Sample();  
    }  
  
  public Sample() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Add an object to calculate the circumference of the circle.  
    Calculate obj = new Calculate();  
    xslArg.AddExtensionObject("urn:myObj", obj);  
  
    //Create an XmlTextWriter to output to the console.  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  
  }  
  
  //Calculates the circumference of a circle given the radius.  
  public class Calculate {  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a>Input  
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
  
 circle.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:myObj="urn:myObj">  
  
  <xsl:template match="data">  
  <circles>  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="myObj:Circumference(radius)"/>          
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a>Resultados  
 `<circles xmlns:myObj="urn:myObj">`  
  
 `<circle>`  
  
 `<radius>12</radius>`  
  
 `<circumference>75.398223686155</circumference>`  
  
 `</circle>`  
  
 `<circle>`  
  
 `<radius>37.5</radius>`  
  
 `<circumference>235.61944901923448</circumference>`  
  
 `</circle>`  
  
 `</circles>`  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
