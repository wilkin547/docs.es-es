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
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a><span data-ttu-id="12410-102">Escritura de scripts de hojas de estilos XSLT mediante \<msxsl:script></span><span class="sxs-lookup"><span data-stu-id="12410-102">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>
<span data-ttu-id="12410-103">Esta clase <xref:System.Xml.Xsl.XslTransform> admite scripts incrustados mediante el elemento `script`.</span><span class="sxs-lookup"><span data-stu-id="12410-103">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12410-104">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="12410-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="12410-105">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="12410-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="12410-106">Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="12410-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="12410-107">Esta clase <xref:System.Xml.Xsl.XslTransform> admite scripts incrustados mediante el elemento `script`.</span><span class="sxs-lookup"><span data-stu-id="12410-107">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span> <span data-ttu-id="12410-108">Cuando se carga la hoja de estilos, las funciones definidas se compilan en el lenguaje intermedio de Microsoft (MSIL) ya que se incluyen en una definición de clase y no se produce pérdida alguna de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="12410-108">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by being wrapped in a class definition and have no performance loss as a result.</span></span>  
  
 <span data-ttu-id="12410-109">A continuación se define el elemento `<msxsl:script>`:</span><span class="sxs-lookup"><span data-stu-id="12410-109">The `<msxsl:script>` element is defined below:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="12410-110">donde `msxsl` es un prefijo enlazado al espacio de nombres `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="12410-110">where `msxsl` is a prefix bound to the namespace `urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="12410-111">El atributo `language` no es obligatorio, pero si se especifica, su valor deberá ser uno de los siguientes: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic` o `CSharp`.</span><span class="sxs-lookup"><span data-stu-id="12410-111">The `language` attribute is not mandatory, but if specified, its value must be one of the following: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`, or `CSharp`.</span></span> <span data-ttu-id="12410-112">Si no se especifica, el lenguaje predeterminado es JScript.</span><span class="sxs-lookup"><span data-stu-id="12410-112">If not specified, the language defaults to JScript.</span></span> <span data-ttu-id="12410-113">`language-name` no distingue entre mayúsculas y minúsculas, entonces 'JavaScript' y 'javascript' son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="12410-113">The `language-name` is not case-sensitive, so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="12410-114">El atributo `implements-prefix` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="12410-114">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="12410-115">Este atributo se utiliza para declarar un espacio de nombres y asociarlo con el bloque del script.</span><span class="sxs-lookup"><span data-stu-id="12410-115">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="12410-116">El valor de este atributo es el prefijo que representa el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="12410-116">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="12410-117">Este espacio de nombres puede definirse en cualquier parte de la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="12410-117">This namespace can be defined somewhere in a style sheet.</span></span>  
  
 <span data-ttu-id="12410-118">Puesto que el elemento `msxsl:script` pertenece al espacio de nombres `urn:schemas-microsoft-com:xslt`, la hoja de estilos debe incluir la declaración del espacio de nombres `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="12410-118">Because the `msxsl:script` element belongs to the namespace `urn:schemas-microsoft-com:xslt`, the style sheet must include the namespace declaration `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="12410-119">Si el llamador del script no tiene permiso de acceso a <xref:System.Security.Permissions.SecurityPermissionFlag>, el script de una hoja de estilos no se compilará y la llamada a <xref:System.Xml.Xsl.XslTransform.Load%2A> producirá errores.</span><span class="sxs-lookup"><span data-stu-id="12410-119">If the caller of the script does not have <xref:System.Security.Permissions.SecurityPermissionFlag> access permission, then the script in a style sheet will never compile and the call to <xref:System.Xml.Xsl.XslTransform.Load%2A> will fail.</span></span>  
  
 <span data-ttu-id="12410-120">Si el llamador tiene permiso `UnmanagedCode`, el script se compilará, pero las operaciones permitidas dependen de la evidencia suministrada en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="12410-120">If the caller has `UnmanagedCode` permission, the script compiles, but the operations that are allowed are dependent on the evidence that is supplied at load time.</span></span>  
  
 <span data-ttu-id="12410-121">Si utiliza uno de los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que toman <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator> para cargar la hoja de estilos, tendrá que utilizar la sobrecarga <xref:System.Xml.Xsl.XslTransform.Load%2A> que toma un parámetro <xref:System.Security.Policy.Evidence> como uno de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="12410-121">If you are using one of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlReader> or <xref:System.Xml.XPath.XPathNavigator> to load the style sheet, you need to use the <xref:System.Xml.Xsl.XslTransform.Load%2A> overload that takes an <xref:System.Security.Policy.Evidence> parameter as one of its arguments.</span></span> <span data-ttu-id="12410-122">Para proporcionar evidencia, el llamador debe tener permiso <xref:System.Security.Permissions.SecurityPermissionFlag> para suministrar `Evidence` al ensamblado de scripts.</span><span class="sxs-lookup"><span data-stu-id="12410-122">To provide evidence, the caller must have <xref:System.Security.Permissions.SecurityPermissionFlag> permission to supply `Evidence` for the script assembly.</span></span> <span data-ttu-id="12410-123">Si el llamador no dispone de este permiso, puede establecer el parámetro `Evidence` en `null`.</span><span class="sxs-lookup"><span data-stu-id="12410-123">If the caller does not have this permission, then they can set the `Evidence` parameter to `null`.</span></span> <span data-ttu-id="12410-124">Esto hace que la función <xref:System.Xml.Xsl.XslTransform.Load%2A> produzca errores si encuentra el script.</span><span class="sxs-lookup"><span data-stu-id="12410-124">This causes the <xref:System.Xml.Xsl.XslTransform.Load%2A> function to fail if it finds script.</span></span> <span data-ttu-id="12410-125">Se considera que el permiso `ControlEvidence` es un permiso muy eficaz que solo debería garantizarse al código de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="12410-125">The `ControlEvidence` permission is considered a very powerful permission that should only be granted to highly trusted code.</span></span>  
  
 <span data-ttu-id="12410-126">Para obtener la evidencia desde el ensamblado, utilice `this.GetType().Assembly.Evidence`.</span><span class="sxs-lookup"><span data-stu-id="12410-126">To get the evidence from your assembly, use `this.GetType().Assembly.Evidence`.</span></span> <span data-ttu-id="12410-127">Para obtener evidencia de un identificador de recurso uniforme (URI), utilice `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span><span class="sxs-lookup"><span data-stu-id="12410-127">To get the evidence from a Uniform Resource Identifier (URI), use `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span></span>  
  
 <span data-ttu-id="12410-128">Si utiliza métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que toman <xref:System.Xml.XmlResolver> pero no `Evidence`, la zona de seguridad del ensamblado toma como valor predeterminado Plena confianza.</span><span class="sxs-lookup"><span data-stu-id="12410-128">If you use <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlResolver> but no `Evidence`, the security zone for the assembly defaults to Full Trust.</span></span> <span data-ttu-id="12410-129">Para más información, vea <xref:System.Security.SecurityZone> y [Conjuntos de permisos con nombre](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="12410-129">For more information, see <xref:System.Security.SecurityZone> and [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="12410-130">Las funciones se pueden declarar dentro del elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="12410-130">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="12410-131">La tabla siguiente muestra los espacios de nombres que se admiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="12410-131">The following table shows the namespaces that are supported by default.</span></span> <span data-ttu-id="12410-132">Es posible utilizar clases fuera de los espacios de nombres enumerados.</span><span class="sxs-lookup"><span data-stu-id="12410-132">You can use classes outside the listed namespaces.</span></span> <span data-ttu-id="12410-133">Sin embargo, el nombre de las clases debe estar completo.</span><span class="sxs-lookup"><span data-stu-id="12410-133">However, these classes must be fully qualified.</span></span>  
  
|<span data-ttu-id="12410-134">Espacios de nombres predeterminados</span><span class="sxs-lookup"><span data-stu-id="12410-134">Default Namespaces</span></span>|<span data-ttu-id="12410-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="12410-135">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="12410-136">Sistema</span><span class="sxs-lookup"><span data-stu-id="12410-136">System</span></span>|<span data-ttu-id="12410-137">Clase del sistema.</span><span class="sxs-lookup"><span data-stu-id="12410-137">System class.</span></span>|  
|<span data-ttu-id="12410-138">System.Collection</span><span class="sxs-lookup"><span data-stu-id="12410-138">System.Collection</span></span>|<span data-ttu-id="12410-139">Clases de colección</span><span class="sxs-lookup"><span data-stu-id="12410-139">Collection classes.</span></span>|  
|<span data-ttu-id="12410-140">System.Text</span><span class="sxs-lookup"><span data-stu-id="12410-140">System.Text</span></span>|<span data-ttu-id="12410-141">Clases de texto.</span><span class="sxs-lookup"><span data-stu-id="12410-141">Text classes.</span></span>|  
|<span data-ttu-id="12410-142">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="12410-142">System.Text.RegularExpressions</span></span>|<span data-ttu-id="12410-143">Clases de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="12410-143">Regular expression classes.</span></span>|  
|<span data-ttu-id="12410-144">System.Xml</span><span class="sxs-lookup"><span data-stu-id="12410-144">System.Xml</span></span>|<span data-ttu-id="12410-145">Clases XML básicas</span><span class="sxs-lookup"><span data-stu-id="12410-145">Core XML classes.</span></span>|  
|<span data-ttu-id="12410-146">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="12410-146">System.Xml.Xsl</span></span>|<span data-ttu-id="12410-147">Clases XSLT</span><span class="sxs-lookup"><span data-stu-id="12410-147">XSLT classes.</span></span>|  
|<span data-ttu-id="12410-148">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="12410-148">System.Xml.XPath</span></span>|<span data-ttu-id="12410-149">Clases XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="12410-149">XML Path Language (XPath) classes.</span></span>|  
|<span data-ttu-id="12410-150">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="12410-150">Microsoft.VisualBasic</span></span>|<span data-ttu-id="12410-151">Clases para scripts de Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12410-151">Classes for Microsoft Visual Basic scripts.</span></span>|  
  
 <span data-ttu-id="12410-152">Cuando se declara una función, está contenida en un bloque de scripts.</span><span class="sxs-lookup"><span data-stu-id="12410-152">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="12410-153">Las hojas de estilos pueden contener varios bloques de scripts que funcionan independientemente unos de otros.</span><span class="sxs-lookup"><span data-stu-id="12410-153">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="12410-154">Esto significa que si se ejecuta código desde un bloque de scripts, no podrá llamar a una función definida en otro bloque a menos que se haya declarado en el mismo espacio de nombres y con el mismo lenguaje de scripts.</span><span class="sxs-lookup"><span data-stu-id="12410-154">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="12410-155">Puesto que cada bloque de script puede estar en su propio lenguaje, y el bloque se analiza de acuerdo con las reglas de gramática de dicho analizador de lenguaje, deberá utilizar la sintaxis correcta para el lenguaje que esté siendo utilizado.</span><span class="sxs-lookup"><span data-stu-id="12410-155">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser, you must use the correct syntax for the language in use.</span></span> <span data-ttu-id="12410-156">Por ejemplo, en un bloque de scripts de C#, es erróneo utilizar un nodo de comentario de XML `<!-- an XML comment -->`.</span><span class="sxs-lookup"><span data-stu-id="12410-156">For example, if you are in a C# script block, then it is an error to use an XML comment node `<!-- an XML comment -->` in the block.</span></span>  
  
 <span data-ttu-id="12410-157">Los argumentos proporcionados y los valores devueltos definidos en las funciones del script deben ser de los tipos XPath o XSLT del W3C.</span><span class="sxs-lookup"><span data-stu-id="12410-157">The supplied arguments and return values defined by the script functions must be one of the World Wide Web Consortium (W3C) XPath or XSLT types.</span></span> <span data-ttu-id="12410-158">En la siguiente tabla se muestran los tipos correspondientes del W3C, las clases de .NET Framework equivalentes (tipo) y si el tipo del W3C es un tipo de XPath o un tipo de XSLT.</span><span class="sxs-lookup"><span data-stu-id="12410-158">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (Type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="12410-159">Tipo</span><span class="sxs-lookup"><span data-stu-id="12410-159">Type</span></span>|<span data-ttu-id="12410-160">Clase equivalente .NET Framework (tipo)</span><span class="sxs-lookup"><span data-stu-id="12410-160">Equivalent .NET Framework Class (Type)</span></span>|<span data-ttu-id="12410-161">Tipo de XPath o tipo XSLT</span><span class="sxs-lookup"><span data-stu-id="12410-161">XPath type or XSLT type</span></span>|  
|----------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="12410-162">String</span><span class="sxs-lookup"><span data-stu-id="12410-162">String</span></span>|<span data-ttu-id="12410-163">System.String</span><span class="sxs-lookup"><span data-stu-id="12410-163">System.String</span></span>|<span data-ttu-id="12410-164">XPath</span><span class="sxs-lookup"><span data-stu-id="12410-164">XPath</span></span>|  
|<span data-ttu-id="12410-165">Booleano</span><span class="sxs-lookup"><span data-stu-id="12410-165">Boolean</span></span>|<span data-ttu-id="12410-166">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="12410-166">System.Boolean</span></span>|<span data-ttu-id="12410-167">XPath</span><span class="sxs-lookup"><span data-stu-id="12410-167">XPath</span></span>|  
|<span data-ttu-id="12410-168">número</span><span class="sxs-lookup"><span data-stu-id="12410-168">Number</span></span>|<span data-ttu-id="12410-169">System.Double</span><span class="sxs-lookup"><span data-stu-id="12410-169">System.Double</span></span>|<span data-ttu-id="12410-170">XPath</span><span class="sxs-lookup"><span data-stu-id="12410-170">XPath</span></span>|  
|<span data-ttu-id="12410-171">Fragmento del árbol de resultados</span><span class="sxs-lookup"><span data-stu-id="12410-171">Result Tree Fragment</span></span>|<span data-ttu-id="12410-172">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="12410-172">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="12410-173">XSLT</span><span class="sxs-lookup"><span data-stu-id="12410-173">XSLT</span></span>|  
|<span data-ttu-id="12410-174">Conjunto de nodos</span><span class="sxs-lookup"><span data-stu-id="12410-174">Node Set</span></span>|<span data-ttu-id="12410-175">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="12410-175">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="12410-176">XPath</span><span class="sxs-lookup"><span data-stu-id="12410-176">XPath</span></span>|  
  
 <span data-ttu-id="12410-177">Si la función de script utiliza uno de los siguientes tipos numéricos: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single o Decimal, se convierten obligatoriamente en Double, que se asigna a un número de tipo W3C XPath.</span><span class="sxs-lookup"><span data-stu-id="12410-177">If the script function utilizes one of the following numeric types: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, or Decimal, they are forced to Double, which maps to the W3C XPath type number.</span></span> <span data-ttu-id="12410-178">El resto de los tipos se convierten obligatoriamente en tipos String con el método `ToString`.</span><span class="sxs-lookup"><span data-stu-id="12410-178">All other types are forced to a string by calling the `ToString` method.</span></span>  
  
 <span data-ttu-id="12410-179">Si la función del script utiliza un tipo distinto a los mencionados anteriormente o si no se compila al cargar la hoja de estilos en el objeto <xref:System.Xml.Xsl.XslTransform>, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="12410-179">If the script function utilizes a type other than the ones mentioned above, or if the function does not compile when the style sheet is loaded into the <xref:System.Xml.Xsl.XslTransform> object, an exception is thrown.</span></span>  
  
 <span data-ttu-id="12410-180">Al utilizar el elemento `msxsl:script`, se recomienda encarecidamente que el script, independientemente del lenguaje, se coloque dentro de una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="12410-180">When using the `msxsl:script` element, it is highly recommended that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="12410-181">Por ejemplo, en el código XML siguiente se muestra la plantilla de la sección CDATA donde se coloca el código.</span><span class="sxs-lookup"><span data-stu-id="12410-181">For example, the following XML shows the template of the CDATA section where your code is placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="12410-182">Se recomienda encarecidamente que todo el contenido de scripts se coloque en una sección CDATA porque existe la posibilidad de que los operadores, identificadores o delimitadores de un lenguaje determinado se interpreten erróneamente como XML.</span><span class="sxs-lookup"><span data-stu-id="12410-182">It is highly recommended that all script content be placed in a CDATA section, because operators, identifiers, or delimiters for a given language have the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="12410-183">En el ejemplo siguiente se demuestra el uso del operador lógico AND en un script.</span><span class="sxs-lookup"><span data-stu-id="12410-183">The following example shows the use of the logical AND operator in script.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 <span data-ttu-id="12410-184">De esta forma se inicia una excepción debido a que no se establece una secuencia de escape para el carácter Y comercial (&amp;).</span><span class="sxs-lookup"><span data-stu-id="12410-184">This throws an exception because the ampersands are not escaped.</span></span> <span data-ttu-id="12410-185">Este documento se carga como XML y no se aplica un tratamiento especial al texto que hay entre las etiquetas del elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="12410-185">The document is loaded as XML, and no special treatment is applied to the text between the `msxsl:script` element tags.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12410-186">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12410-186">Example</span></span>  
 <span data-ttu-id="12410-187">En el ejemplo siguiente se utiliza un script incrustado para calcular la longitud de una circunferencia dado su radio.</span><span class="sxs-lookup"><span data-stu-id="12410-187">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
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
  
## <a name="input"></a><span data-ttu-id="12410-188">Entrada</span><span class="sxs-lookup"><span data-stu-id="12410-188">Input</span></span>  
 <span data-ttu-id="12410-189">number.xml</span><span class="sxs-lookup"><span data-stu-id="12410-189">number.xml</span></span>  
  
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
  
 <span data-ttu-id="12410-190">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="12410-190">calc.xsl</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="12410-191">Salida</span><span class="sxs-lookup"><span data-stu-id="12410-191">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12410-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="12410-192">See also</span></span>

- [<span data-ttu-id="12410-193">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="12410-193">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
