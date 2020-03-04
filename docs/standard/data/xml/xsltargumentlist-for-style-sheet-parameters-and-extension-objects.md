---
title: XsltArgumentList para parámetros Stylesheet y objetos de extensión
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: 34ffb9923337bbad90b2170a16d610d26c7f6f23
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160201"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a><span data-ttu-id="f83ba-102">XsltArgumentList para parámetros Stylesheet y objetos de extensión</span><span class="sxs-lookup"><span data-stu-id="f83ba-102">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>
<span data-ttu-id="f83ba-103">La clase <xref:System.Xml.Xsl.XsltArgumentList> contiene parámetros Extensible Stylesheet Language for Transformations (XSLT) y objetos de extensión XSLT.</span><span class="sxs-lookup"><span data-stu-id="f83ba-103">The <xref:System.Xml.Xsl.XsltArgumentList> class contains Extensible Stylesheet Language for Transformations (XSLT) parameters and XSLT extension objects.</span></span> <span data-ttu-id="f83ba-104">Cuando se pasan al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> se puede invocar a estos parámetros y objetos de extensión desde hojas de estilos.</span><span class="sxs-lookup"><span data-stu-id="f83ba-104">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f83ba-105">Las clases <xref:System.Xml.Xsl.XslTransform> y <xref:System.Xml.Xsl.XsltArgumentList> están obsoletas en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f83ba-105">The <xref:System.Xml.Xsl.XslTransform> and <xref:System.Xml.Xsl.XsltArgumentList> classes are obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="f83ba-106">Puede llevar a cabo transformaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-106">You can perform XSLT transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="f83ba-107">Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f83ba-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="f83ba-108">La clase <xref:System.Xml.Xsl.XsltArgumentList> contiene parámetros XSLT y objetos de extensión de XSLT.</span><span class="sxs-lookup"><span data-stu-id="f83ba-108">The <xref:System.Xml.Xsl.XsltArgumentList> class contains XSLT parameters and XSLT extension objects.</span></span> <span data-ttu-id="f83ba-109">Cuando se pasan al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> se puede invocar a estos parámetros y objetos de extensión desde hojas de estilos.</span><span class="sxs-lookup"><span data-stu-id="f83ba-109">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
 <span data-ttu-id="f83ba-110">A continuación se enumeran las ventajas de pasar un objeto en lugar de utilizar un script incrustado:</span><span class="sxs-lookup"><span data-stu-id="f83ba-110">The following are advantages to passing an object rather than using an embedded script:</span></span>  
  
- <span data-ttu-id="f83ba-111">Proporciona una mejor encapsulación y reutilización de clases.</span><span class="sxs-lookup"><span data-stu-id="f83ba-111">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="f83ba-112">Permite que las hojas de estilos sean más pequeñas y facilita su mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="f83ba-112">Allows style sheets to be smaller and more maintainable.</span></span>  
  
- <span data-ttu-id="f83ba-113">Admite llamadas a métodos en clases que pertenecen a otros espacios de nombres distintos de los definidos dentro del conjunto de espacios de nombres admitidos por el sistema <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-113">Supports calling methods on classes belonging to namespaces other than those defined within the set of supported <xref:System> namespaces.</span></span>  
  
- <span data-ttu-id="f83ba-114">Permite que se pasen fragmentos de árboles de resultados a la hoja de estilos con el uso de <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-114">Supports passing result tree fragments to the style sheet with the use of the <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
## <a name="xslt-style-sheet-parameters"></a><span data-ttu-id="f83ba-115">Parámetros de XSLT de hoja de estilos</span><span class="sxs-lookup"><span data-stu-id="f83ba-115">XSLT Style Sheet Parameters</span></span>  
 <span data-ttu-id="f83ba-116">Los parámetros XSLT se agregan a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-116">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="f83ba-117">En ese momento se asocian un nombre completo y un identificador de recursos de uniforme (URI) de espacio de nombres con el objeto del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f83ba-117">A qualified name and namespace Uniform Resource Identifier (URI) are associated with the parameter object at that time.</span></span>  
  
 <span data-ttu-id="f83ba-118">El objeto del parámetro debería corresponder al tipo World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="f83ba-118">The parameter object should correspond to a World Wide Web Consortium (W3C) type.</span></span> <span data-ttu-id="f83ba-119">La tabla siguiente muestra los tipos W3C correspondientes, las clases de .NET Framework equivalentes (tipo) y si el tipo W3C es un tipo de lenguaje de ruta XML (XPath) o tipo XSLT.</span><span class="sxs-lookup"><span data-stu-id="f83ba-119">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (type), and whether the W3C type is an XML Path Language (XPath) type or XSLT type.</span></span>  
  
|<span data-ttu-id="f83ba-120">Tipo W3C</span><span class="sxs-lookup"><span data-stu-id="f83ba-120">W3C Type</span></span>|<span data-ttu-id="f83ba-121">Clase equivalente .NET Framework (tipo)</span><span class="sxs-lookup"><span data-stu-id="f83ba-121">Equivalent .NET Framework class (type)</span></span>|<span data-ttu-id="f83ba-122">Tipo de XPath o tipo XSLT</span><span class="sxs-lookup"><span data-stu-id="f83ba-122">XPath type or XSLT type</span></span>|  
|--------------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="f83ba-123">Cadena</span><span class="sxs-lookup"><span data-stu-id="f83ba-123">String</span></span>|<span data-ttu-id="f83ba-124">System.String</span><span class="sxs-lookup"><span data-stu-id="f83ba-124">System.String</span></span>|<span data-ttu-id="f83ba-125">XPath</span><span class="sxs-lookup"><span data-stu-id="f83ba-125">XPath</span></span>|  
|<span data-ttu-id="f83ba-126">Booleano</span><span class="sxs-lookup"><span data-stu-id="f83ba-126">Boolean</span></span>|<span data-ttu-id="f83ba-127">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="f83ba-127">System.Boolean</span></span>|<span data-ttu-id="f83ba-128">XPath</span><span class="sxs-lookup"><span data-stu-id="f83ba-128">XPath</span></span>|  
|<span data-ttu-id="f83ba-129">número</span><span class="sxs-lookup"><span data-stu-id="f83ba-129">Number</span></span>|<span data-ttu-id="f83ba-130">System.Double</span><span class="sxs-lookup"><span data-stu-id="f83ba-130">System.Double</span></span>|<span data-ttu-id="f83ba-131">XPath</span><span class="sxs-lookup"><span data-stu-id="f83ba-131">XPath</span></span>|  
|<span data-ttu-id="f83ba-132">Fragmento del árbol de resultados</span><span class="sxs-lookup"><span data-stu-id="f83ba-132">Result Tree Fragment</span></span>|<span data-ttu-id="f83ba-133">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="f83ba-133">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="f83ba-134">XSLT</span><span class="sxs-lookup"><span data-stu-id="f83ba-134">XSLT</span></span>|  
|<span data-ttu-id="f83ba-135">Conjunto de nodos</span><span class="sxs-lookup"><span data-stu-id="f83ba-135">Node Set</span></span>|<span data-ttu-id="f83ba-136">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="f83ba-136">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="f83ba-137">XPath</span><span class="sxs-lookup"><span data-stu-id="f83ba-137">XPath</span></span>|  
  
 <span data-ttu-id="f83ba-138">Si el objeto del parámetro no es una de las clases anteriores, se obliga a que sea Double o String, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f83ba-138">If the parameter object is not one of the above classes, it is forced to either a Double or String, as appropriate.</span></span> <span data-ttu-id="f83ba-139">Los tipos Int16, UInt16, Int32, UInt32, Int64, UInt64, Single y Decimal se convierten obligatoriamente a Double.</span><span class="sxs-lookup"><span data-stu-id="f83ba-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single and Decimal types are forced to a Double.</span></span> <span data-ttu-id="f83ba-140">Todos los demás tipos se convierten obligatoriamente a String con el método `ToString`.</span><span class="sxs-lookup"><span data-stu-id="f83ba-140">All other types are forced to a String using the `ToString` method.</span></span>  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a><span data-ttu-id="f83ba-141">Para utilizar el parámetro XSLT, el usuario debe seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f83ba-141">To use the XSLT parameter, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="f83ba-142">Crear <xref:System.Xml.Xsl.XsltArgumentList> y añadir los objetos mediante <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-142">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the objects using <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span></span>  
  
2. <span data-ttu-id="f83ba-143">Llamar a los parámetros desde la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="f83ba-143">Call the parameters from the style sheet.</span></span>  
  
3. <span data-ttu-id="f83ba-144">Pasar <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-144">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f83ba-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f83ba-145">Example</span></span>  
 <span data-ttu-id="f83ba-146">En el ejemplo siguiente se utiliza el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> para crear un parámetro que almacena la fecha de descuento calculada.</span><span class="sxs-lookup"><span data-stu-id="f83ba-146">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold a calculated discount date.</span></span> <span data-ttu-id="f83ba-147">Para calcular la fecha de descuento se deben sumar 20 días a partir de la fecha del pedido.</span><span class="sxs-lookup"><span data-stu-id="f83ba-147">The discount date is calculated to be 20 days from the order date.</span></span>  
  
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
  
### <a name="input"></a><span data-ttu-id="f83ba-148">Entrada</span><span class="sxs-lookup"><span data-stu-id="f83ba-148">Input</span></span>  
 <span data-ttu-id="f83ba-149">order.xml</span><span class="sxs-lookup"><span data-stu-id="f83ba-149">order.xml</span></span>  
  
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
  
 <span data-ttu-id="f83ba-150">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="f83ba-150">discount.xsl</span></span>  
  
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
  
### <a name="output"></a><span data-ttu-id="f83ba-151">Resultado</span><span class="sxs-lookup"><span data-stu-id="f83ba-151">Output</span></span>  
  
```xml  
<order>  
   <total>36.9</total>
   15% discount if paid by: 5/6/2001 5:01:15 PM
</order>  
```  
  
## <a name="xslt-extension-objects"></a><span data-ttu-id="f83ba-152">Objetos de extensión de XSLT</span><span class="sxs-lookup"><span data-stu-id="f83ba-152">XSLT Extension Objects</span></span>  
 <span data-ttu-id="f83ba-153">Los objetos de extensión XSLT se añaden a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-153">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="f83ba-154">En ese momento se asocian un nombre completo y un identificador URI de espacio de nombres con el objeto de extensión.</span><span class="sxs-lookup"><span data-stu-id="f83ba-154">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
 <span data-ttu-id="f83ba-155">Cuando se agrega un objeto, el llamador de <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> debe ser de confianza total en la directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f83ba-155">When an object is added, the caller of the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> must be fully trusted in the security policy.</span></span> <span data-ttu-id="f83ba-156">Si el llamador es de confianza parcial, la adición producirá errores.</span><span class="sxs-lookup"><span data-stu-id="f83ba-156">If the caller is semi-trusted, the addition will fail.</span></span>  
  
 <span data-ttu-id="f83ba-157">El hecho de que un objeto se agregue correctamente, no garantiza que la ejecución vaya a producirse correctamente.</span><span class="sxs-lookup"><span data-stu-id="f83ba-157">Though an object is added successfully, it does not guarantee that the execution will be successful.</span></span> <span data-ttu-id="f83ba-158">Cuando se llama al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, los permisos se calculan con la evidencia proporcionada durante la ejecución del método <xref:System.Xml.Xsl.XslTransform.Load%2A> y dicho conjunto de permisos se asigna a todo el proceso de transformación.</span><span class="sxs-lookup"><span data-stu-id="f83ba-158">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at <xref:System.Xml.Xsl.XslTransform.Load%2A> time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="f83ba-159">Si un objeto de extensión intenta iniciar una acción que requiere permisos que no se han encontrado en el conjunto, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="f83ba-159">If an extension object attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
 <span data-ttu-id="f83ba-160">Los tipos de datos devueltos desde los objetos de extensión pertenecen a uno de los cuatro tipos de datos básicos de Xpath: datos de tipo numérico, datos de tipo cadena, datos booleanos y conjuntos de nodos.</span><span class="sxs-lookup"><span data-stu-id="f83ba-160">The data types returned from extension objects are one of the four basic XPath data types of number, string, Boolean, and node set.</span></span>  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a><span data-ttu-id="f83ba-161">Para utilizar objetos de extensión de XSLT, el usuario debe seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f83ba-161">To use the XSLT extension object, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="f83ba-162">Crear <xref:System.Xml.Xsl.XsltArgumentList> y añadir el objeto de extensión mediante <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-162">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span></span>  
  
2. <span data-ttu-id="f83ba-163">Invocar al objeto de extensión desde la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="f83ba-163">Invoke the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="f83ba-164">Pasar <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="f83ba-164">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f83ba-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f83ba-165">Example</span></span>  
 <span data-ttu-id="f83ba-166">En el ejemplo siguiente se calcula la longitud de una circunferencia dado su radio.</span><span class="sxs-lookup"><span data-stu-id="f83ba-166">The following example calculates the circumference of a circle given its radius.</span></span>  
  
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
  
### <a name="input"></a><span data-ttu-id="f83ba-167">Entrada</span><span class="sxs-lookup"><span data-stu-id="f83ba-167">Input</span></span>  
 <span data-ttu-id="f83ba-168">number.xml</span><span class="sxs-lookup"><span data-stu-id="f83ba-168">number.xml</span></span>  
  
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
  
 <span data-ttu-id="f83ba-169">circle.xsl</span><span class="sxs-lookup"><span data-stu-id="f83ba-169">circle.xsl</span></span>  
  
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
  
### <a name="output"></a><span data-ttu-id="f83ba-170">Resultado</span><span class="sxs-lookup"><span data-stu-id="f83ba-170">Output</span></span>  
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
  
## <a name="see-also"></a><span data-ttu-id="f83ba-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="f83ba-171">See also</span></span>

- [<span data-ttu-id="f83ba-172">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="f83ba-172">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
