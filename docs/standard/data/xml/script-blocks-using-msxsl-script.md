---
title: Bloques de scripts con msxsl:script
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: a63452df16e452a90eff3977ac8726cc0a5ac439
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710198"
---
# <a name="script-blocks-using-msxslscript"></a><span data-ttu-id="3f214-102">Bloques de scripts con msxsl:script</span><span class="sxs-lookup"><span data-stu-id="3f214-102">Script Blocks Using msxsl:script</span></span>
<span data-ttu-id="3f214-103">La clase <xref:System.Xml.Xsl.XslCompiledTransform> admite scripts incrustados mediante el elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="3f214-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports embedded scripts using the `msxsl:script` element.</span></span> <span data-ttu-id="3f214-104">Cuando se carga la hoja de estilos, cualquier función definida se compila en el lenguaje intermedio de Microsoft (MSIL) por medio del Code Document Object Model (CodeDOM) y se ejecutan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3f214-104">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by the Code Document Object Model (CodeDOM) and are executed during run time.</span></span> <span data-ttu-id="3f214-105">El ensamblado que se genera a partir del bloque de scripts incrustado es distinto al ensamblado que se genera para la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="3f214-105">The assembly generated from the embedded script block is separate than the assembly generated for the style sheet.</span></span>  
  
## <a name="enable-xslt-script"></a><span data-ttu-id="3f214-106">Cómo habilitar el script XSLT</span><span class="sxs-lookup"><span data-stu-id="3f214-106">Enable XSLT Script</span></span>  
 <span data-ttu-id="3f214-107">La compatibilidad con scripts incrustados es un valor XSLT opcional de la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="3f214-107">Support for embedded scripts is an optional XSLT setting on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="3f214-108">Esta compatibilidad está deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f214-108">Script support is disabled by default.</span></span> <span data-ttu-id="3f214-109">Para habilitarla, cree un objeto <xref:System.Xml.Xsl.XsltSettings> con el conjunto de propiedades <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> establecido en `true` y pase el objeto al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f214-109">To enable script support, create an <xref:System.Xml.Xsl.XsltSettings> object with the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> property set to `true` and pass the object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f214-110">El script XSLT solo se debería habilitar si necesita compatibilidad con scripts o si está trabajando en un entorno de total confianza.</span><span class="sxs-lookup"><span data-stu-id="3f214-110">XSLT scripting should be enabled only if you require script support and you are working in a fully trusted environment.</span></span>  
  
## <a name="msxslscript-element-definition"></a><span data-ttu-id="3f214-111">Definición del elemento msxsl:script</span><span class="sxs-lookup"><span data-stu-id="3f214-111">msxsl:script Element Definition</span></span>  
 <span data-ttu-id="3f214-112">El elemento `msxsl:script` es una extensión de Microsoft de la recomendación de XSLT 1.0 y tiene la siguiente definición:</span><span class="sxs-lookup"><span data-stu-id="3f214-112">The `msxsl:script` element is a Microsoft extension to the XSLT 1.0 recommendation and has the following definition:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="3f214-113">El prefijo `msxsl` está enlazado al identificador URI del espacio de nombres `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="3f214-113">The `msxsl` prefix is bound to the `urn:schemas-microsoft-com:xslt` namespace URI.</span></span> <span data-ttu-id="3f214-114">La hoja de estilos debe incluir la declaración de espacio de nombres `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="3f214-114">The style sheet must include the `xmlns:msxsl=urn:schemas-microsoft-com:xslt` namespace declaration.</span></span>  
  
 <span data-ttu-id="3f214-115">El atributo `language` es opcional.</span><span class="sxs-lookup"><span data-stu-id="3f214-115">The `language` attribute is optional.</span></span> <span data-ttu-id="3f214-116">Su valor es el lenguaje de código del bloque de código incrustado.</span><span class="sxs-lookup"><span data-stu-id="3f214-116">Its value is the code language of the embedded code block.</span></span> <span data-ttu-id="3f214-117">El lenguaje se asigna al compilador CodeDOM apropiado utilizando el método <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f214-117">The language is mapped to the appropriate CodeDOM compiler using the <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3f214-118">La clase <xref:System.Xml.Xsl.XslCompiledTransform> admite cualquier lenguaje de Microsoft .NET Framework, asumiendo que en el equipo está instalado el proveedor apropiado y está registrado en la sección system.codecom del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3f214-118">The <xref:System.Xml.Xsl.XslCompiledTransform> class can support any Microsoft .NET language, assuming the appropriate provider is installed on the machine and is registered in the system.codedom section of the machine.config file.</span></span> <span data-ttu-id="3f214-119">Si no se especifica un atributo `language`, el lenguaje predeterminado es JScript.</span><span class="sxs-lookup"><span data-stu-id="3f214-119">If a `language` attribute is not specified, the language defaults to JScript.</span></span> <span data-ttu-id="3f214-120">El nombre del lenguaje no distingue mayúsculas de minúsculas, por lo que 'JavaScript' y 'javascript' son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="3f214-120">The language name is not case-sensitive so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="3f214-121">El atributo `implements-prefix` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3f214-121">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="3f214-122">Este atributo se utiliza para declarar un espacio de nombres y asociarlo con el bloque del script.</span><span class="sxs-lookup"><span data-stu-id="3f214-122">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="3f214-123">El valor de este atributo es el prefijo que representa el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3f214-123">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="3f214-124">Este prefijo puede definirse en cualquier parte de la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="3f214-124">This prefix can be defined somewhere in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f214-125">Al utilizar el elemento `msxsl:script`, se recomienda encarecidamente que el script, independientemente del lenguaje, se coloque dentro de una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="3f214-125">When using the `msxsl:script` element, we strongly recommend that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="3f214-126">Puesto que el script puede contener operadores, identificadores o delimitadores para un lenguaje específico, si no está contenido en la sección CDATA, podría interpretarse erróneamente como XML.</span><span class="sxs-lookup"><span data-stu-id="3f214-126">Because the script can contain operators, identifiers, or delimiters for a given language, if it is not contained within a CDATA section, it has the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="3f214-127">El siguiente XML muestra una plantilla de la sección CDATA en donde se puede colocar el código.</span><span class="sxs-lookup"><span data-stu-id="3f214-127">The following XML shows a template of the CDATA section where code can be placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a><span data-ttu-id="3f214-128">Funciones del script</span><span class="sxs-lookup"><span data-stu-id="3f214-128">Script Functions</span></span>  
 <span data-ttu-id="3f214-129">Las funciones se pueden declarar dentro del elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="3f214-129">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="3f214-130">Cuando se declara una función, está contenida en un bloque de scripts.</span><span class="sxs-lookup"><span data-stu-id="3f214-130">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="3f214-131">Las hojas de estilos pueden contener varios bloques de scripts que funcionan independientemente unos de otros.</span><span class="sxs-lookup"><span data-stu-id="3f214-131">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="3f214-132">Esto significa que si se ejecuta código desde un bloque de scripts, no podrá llamar a una función definida en otro bloque a menos que se haya declarado en el mismo espacio de nombres y con el mismo lenguaje de scripts.</span><span class="sxs-lookup"><span data-stu-id="3f214-132">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="3f214-133">Puesto que cada bloque de script puede estar en su propio lenguaje, y el bloque se analiza de acuerdo con las reglas de gramática de dicho analizador de lenguaje, se recomienda utilizar la sintaxis correcta para el lenguaje que esté siendo utilizado.</span><span class="sxs-lookup"><span data-stu-id="3f214-133">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser we recommend that you use the correct syntax for the language in use.</span></span> <span data-ttu-id="3f214-134">Por ejemplo, si está en un bloque de scripts de Microsoft C#, utilice la sintaxis de comentarios de C#.</span><span class="sxs-lookup"><span data-stu-id="3f214-134">For example, if you are in a Microsoft C# script block, use the C# comment syntax.</span></span>  
  
 <span data-ttu-id="3f214-135">Los argumentos suministrados y los valores devueltos a la función pueden ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="3f214-135">The supplied arguments and return values to the function can be of any type.</span></span> <span data-ttu-id="3f214-136">Puesto que los tipos XPath del W3C son un subconjunto de los tipos de Common Language Runtime (CLR), la conversión de tipos tiene lugar en los tipos que no se consideran un tipo de XPath.</span><span class="sxs-lookup"><span data-stu-id="3f214-136">Because the W3C XPath types are a subset of the common language runtime (CLR) types, type conversion takes place on types that are not considered to be an XPath type.</span></span> <span data-ttu-id="3f214-137">En la siguiente tabla se muestran los tipos del W3C correspondientes y el tipo CLR equivalente.</span><span class="sxs-lookup"><span data-stu-id="3f214-137">The following table shows the corresponding W3C types and the equivalent CLR type.</span></span>  
  
|<span data-ttu-id="3f214-138">Tipo del W3C</span><span class="sxs-lookup"><span data-stu-id="3f214-138">W3C type</span></span>|<span data-ttu-id="3f214-139">Tipo CLR</span><span class="sxs-lookup"><span data-stu-id="3f214-139">CLR type</span></span>|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 <span data-ttu-id="3f214-140">Los tipos CLR numéricos se convierten en <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="3f214-140">CLR numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="3f214-141">El tipo <xref:System.DateTime> se convierte en <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="3f214-141">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="3f214-142">Los tipos <xref:System.Xml.XPath.IXPathNavigable> se convierten en <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="3f214-142"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="3f214-143">**XPathNavigator[]** se convierte en <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="3f214-143">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="3f214-144">El resto de los tipos inician un error.</span><span class="sxs-lookup"><span data-stu-id="3f214-144">All other types throw an error.</span></span>  
  
### <a name="importing-namespaces-and-assemblies"></a><span data-ttu-id="3f214-145">Importación de espacios de nombres y ensamblajes</span><span class="sxs-lookup"><span data-stu-id="3f214-145">Importing Namespaces and Assemblies</span></span>  
 <span data-ttu-id="3f214-146">La clase <xref:System.Xml.Xsl.XslCompiledTransform> predefine un conjunto de ensamblajes y espacios de nombres que admite de manera predeterminada el elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="3f214-146">The <xref:System.Xml.Xsl.XslCompiledTransform> class predefines a set of assemblies and namespaces that are supported by default by the `msxsl:script` element.</span></span> <span data-ttu-id="3f214-147">Sin embargo, puede utilizar las clases y los miembros que pertenecen a un espacio de nombres que no está en la lista predefinida importando el ensamblaje y el espacio de nombres del bloque `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="3f214-147">However, you can use classes and members belonging to a namespace that is not on the predefined list by importing the assembly and namespace in `msxsl:script` block.</span></span>  
  
#### <a name="assemblies"></a><span data-ttu-id="3f214-148">Assemblies</span><span class="sxs-lookup"><span data-stu-id="3f214-148">Assemblies</span></span>  
 <span data-ttu-id="3f214-149">Se hace referencia a los dos siguientes ensamblajes de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="3f214-149">The following two assemblies are referenced by default:</span></span>  
  
- <span data-ttu-id="3f214-150">System.dll</span><span class="sxs-lookup"><span data-stu-id="3f214-150">System.dll</span></span>  
  
- <span data-ttu-id="3f214-151">System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="3f214-151">System.Xml.dll</span></span>  
  
- <span data-ttu-id="3f214-152">Microsoft.VisualBasic.dll (cuando el lenguaje de scripts es VB)</span><span class="sxs-lookup"><span data-stu-id="3f214-152">Microsoft.VisualBasic.dll (when the script language is VB)</span></span>  
  
 <span data-ttu-id="3f214-153">Puede importar los ensamblajes adicionales utilizando el elemento `msxsl:assembly`.</span><span class="sxs-lookup"><span data-stu-id="3f214-153">You can import the additional assemblies using the `msxsl:assembly` element.</span></span> <span data-ttu-id="3f214-154">Esto incluye el ensamblaje cuando se compila la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="3f214-154">This includes the assembly when the style sheet is compiled.</span></span> <span data-ttu-id="3f214-155">El elemento `msxsl:assembly` tiene la siguiente definición:</span><span class="sxs-lookup"><span data-stu-id="3f214-155">The `msxsl:assembly` element has the following definition:</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="3f214-156">El atributo `name` contiene el nombre del ensamblaje y el atributo `href` contiene la ruta al ensamblaje.</span><span class="sxs-lookup"><span data-stu-id="3f214-156">The `name` attribute contains the name of the assembly and the `href` attribute contains the path to the assembly.</span></span> <span data-ttu-id="3f214-157">El nombre del ensamblaje puede ser un nombre completo como, por ejemplo, "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", o un nombre corto como, por ejemplo, "System.Web".</span><span class="sxs-lookup"><span data-stu-id="3f214-157">The assembly name can be a full name, such as "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", or a short name, such as "System.Web".</span></span>  
  
#### <a name="namespaces"></a><span data-ttu-id="3f214-158">Espacios de nombres de</span><span class="sxs-lookup"><span data-stu-id="3f214-158">Namespaces</span></span>  
 <span data-ttu-id="3f214-159">Los siguientes espacios de nombres están incluidos de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="3f214-159">The following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="3f214-160">System</span><span class="sxs-lookup"><span data-stu-id="3f214-160">System</span></span>  
  
- <span data-ttu-id="3f214-161">System.Collection</span><span class="sxs-lookup"><span data-stu-id="3f214-161">System.Collection</span></span>  
  
- <span data-ttu-id="3f214-162">System.Text</span><span class="sxs-lookup"><span data-stu-id="3f214-162">System.Text</span></span>  
  
- <span data-ttu-id="3f214-163">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="3f214-163">System.Text.RegularExpressions</span></span>  
  
- <span data-ttu-id="3f214-164">System.Xml</span><span class="sxs-lookup"><span data-stu-id="3f214-164">System.Xml</span></span>  
  
- <span data-ttu-id="3f214-165">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="3f214-165">System.Xml.Xsl</span></span>  
  
- <span data-ttu-id="3f214-166">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="3f214-166">System.Xml.XPath</span></span>  
  
- <span data-ttu-id="3f214-167">Microsoft.VisualBasic (cuando el lenguaje de scripts es VB)</span><span class="sxs-lookup"><span data-stu-id="3f214-167">Microsoft.VisualBasic (when the script language is VB)</span></span>  
  
 <span data-ttu-id="3f214-168">Puede agregar compatibilidad para espacios de nombres adicionales utilizando el atributo `namespace`.</span><span class="sxs-lookup"><span data-stu-id="3f214-168">You can add support for additional namespaces using the `namespace` attribute.</span></span> <span data-ttu-id="3f214-169">El valor del atributo es el nombre del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3f214-169">The attribute value is the name of the namespace.</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a><span data-ttu-id="3f214-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f214-170">Example</span></span>  
 <span data-ttu-id="3f214-171">En el ejemplo siguiente se utiliza un script incrustado para calcular la longitud de una circunferencia dado su radio.</span><span class="sxs-lookup"><span data-stu-id="3f214-171">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a><span data-ttu-id="3f214-172">number.xml</span><span class="sxs-lookup"><span data-stu-id="3f214-172">number.xml</span></span>  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a><span data-ttu-id="3f214-173">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="3f214-173">calc.xsl</span></span>  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="3f214-174">Resultados</span><span class="sxs-lookup"><span data-stu-id="3f214-174">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f214-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f214-175">See also</span></span>

- [<span data-ttu-id="3f214-176">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="3f214-176">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="3f214-177">Generación y compilación dinámicas de código fuente</span><span class="sxs-lookup"><span data-stu-id="3f214-177">Dynamic Source Code Generation and Compilation</span></span>](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
