---
title: Atributos comunes
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400724"
---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="e2044-102">Common Attributes (Visual Basic) (Atributos comunes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2044-102">Common Attributes (Visual Basic)</span></span>

<span data-ttu-id="e2044-103">En este tema se describen los atributos que se usan con más frecuencia en Visual Basic programas.</span><span class="sxs-lookup"><span data-stu-id="e2044-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>

- [<span data-ttu-id="e2044-104">Atributos globales</span><span class="sxs-lookup"><span data-stu-id="e2044-104">Global Attributes</span></span>](#Global)

- [<span data-ttu-id="e2044-105">Atributo Obsolete</span><span class="sxs-lookup"><span data-stu-id="e2044-105">Obsolete Attribute</span></span>](#Obsolete)

- [<span data-ttu-id="e2044-106">Atributo Conditional</span><span class="sxs-lookup"><span data-stu-id="e2044-106">Conditional Attribute</span></span>](#Conditional)

- [<span data-ttu-id="e2044-107">Atributos de información del llamador</span><span class="sxs-lookup"><span data-stu-id="e2044-107">Caller Info Attributes</span></span>](#CallerInfo)

- [<span data-ttu-id="e2044-108">Atributos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2044-108">Visual Basic Attributes</span></span>](#VB)

## <a name="global-attributes"></a><a name="Global"></a><span data-ttu-id="e2044-109">Atributos globales</span><span class="sxs-lookup"><span data-stu-id="e2044-109">Global Attributes</span></span>

<span data-ttu-id="e2044-110">La mayoría de los atributos se aplican a elementos específicos del lenguaje, como las clases o los métodos, aunque algunos atributos son globales (se aplican a todo un ensamblado o módulo).</span><span class="sxs-lookup"><span data-stu-id="e2044-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="e2044-111">Por ejemplo, el atributo <xref:System.Reflection.AssemblyVersionAttribute> se puede usar para insertar información de versión en un ensamblado, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2044-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

<span data-ttu-id="e2044-112">Los atributos globales aparecen en el código fuente después de cualquier instrucción de nivel superior `Imports` y antes de cualquier declaración de espacio de nombres, módulo o tipo.</span><span class="sxs-lookup"><span data-stu-id="e2044-112">Global attributes appear in the source code after any top-level `Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="e2044-113">Los atributos globales pueden aparecer en varios archivos de código fuente, pero estos archivos se deben compilar en un solo paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="e2044-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="e2044-114">En el caso de los proyectos de Visual Basic, los atributos globales normalmente se colocan en el archivo AssemblyInfo. VB (el archivo se crea automáticamente cuando se crea un proyecto en Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="e2044-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>

<span data-ttu-id="e2044-115">Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="e2044-116">Se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="e2044-116">They fall into the following categories:</span></span>

- <span data-ttu-id="e2044-117">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e2044-117">Assembly identity attributes</span></span>

- <span data-ttu-id="e2044-118">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="e2044-118">Informational attributes</span></span>

- <span data-ttu-id="e2044-119">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e2044-119">Assembly manifest attributes</span></span>

### <a name="assembly-identity-attributes"></a><span data-ttu-id="e2044-120">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e2044-120">Assembly Identity Attributes</span></span>

<span data-ttu-id="e2044-121">Tres atributos, con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="e2044-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="e2044-122">Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia a este en el código.</span><span class="sxs-lookup"><span data-stu-id="e2044-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="e2044-123">Puede establecer la versión y la referencia cultural de un ensamblado mediante atributos,</span><span class="sxs-lookup"><span data-stu-id="e2044-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="e2044-124">pero el valor de nombre lo establece el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](/visualstudio/ide/reference/assembly-information-dialog-box) o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado, a partir del archivo que contiene el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="e2044-125">El atributo <xref:System.Reflection.AssemblyFlagsAttribute> especifica si pueden coexistir varias copias del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="e2044-126">En la siguiente tabla se muestran los atributos de identidad.</span><span class="sxs-lookup"><span data-stu-id="e2044-126">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="e2044-127">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2044-127">Attribute</span></span>|<span data-ttu-id="e2044-128">Propósito</span><span class="sxs-lookup"><span data-stu-id="e2044-128">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="e2044-129">Describe completamente la identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-129">Fully describes the identity of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="e2044-130">Especifica la versión de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-130">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="e2044-131">Especifica la cultura que admite el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-131">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="e2044-132">Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2044-132">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

### <a name="informational-attributes"></a><span data-ttu-id="e2044-133">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="e2044-133">Informational Attributes</span></span>

<span data-ttu-id="e2044-134">Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-134">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="e2044-135">En la tabla siguiente se muestran los atributos informativos definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2044-135">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="e2044-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2044-136">Attribute</span></span>|<span data-ttu-id="e2044-137">Propósito</span><span class="sxs-lookup"><span data-stu-id="e2044-137">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="e2044-138">Define un atributo personalizado que especifica un nombre de producto para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-138">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="e2044-139">Define un atributo personalizado que especifica una marca comercial para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-139">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="e2044-140">Define un atributo personalizado que especifica una versión informativa para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-140">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="e2044-141">Define un atributo personalizado que especifica un nombre de compañía para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-141">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="e2044-142">Define un atributo personalizado que especifica un copyright para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-142">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="e2044-143">Indica al compilador que use un número de versión específico para el recurso de versión de archivo Win32.</span><span class="sxs-lookup"><span data-stu-id="e2044-143">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="e2044-144">Indica si el ensamblado es compatible con Common Language Specification (CLS).</span><span class="sxs-lookup"><span data-stu-id="e2044-144">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

### <a name="assembly-manifest-attributes"></a><span data-ttu-id="e2044-145">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e2044-145">Assembly Manifest Attributes</span></span>

<span data-ttu-id="e2044-146">Puede usar los atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e2044-146">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="e2044-147">(título, descripción, alias predeterminado y configuración).</span><span class="sxs-lookup"><span data-stu-id="e2044-147">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="e2044-148">En la tabla siguiente se muestran los atributos de manifiesto del ensamblado definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2044-148">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="e2044-149">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2044-149">Attribute</span></span>|<span data-ttu-id="e2044-150">Propósito</span><span class="sxs-lookup"><span data-stu-id="e2044-150">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="e2044-151">Define un atributo personalizado que especifica un título de ensamblado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-151">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="e2044-152">Define un atributo personalizado que especifica una descripción de ensamblado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-152">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="e2044-153">Define un atributo personalizado que especifica una configuración de ensamblado (por ejemplo, comercial o depuración) para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-153">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="e2044-154">Define un alias descriptivo predeterminado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2044-154">Defines a friendly default alias for an assembly manifest</span></span>|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a><span data-ttu-id="e2044-155">Atributo obsoleto</span><span class="sxs-lookup"><span data-stu-id="e2044-155">Obsolete Attribute</span></span>

<span data-ttu-id="e2044-156">El atributo `Obsolete` marca una entidad del programa como una entidad cuyo uso ya no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="e2044-156">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="e2044-157">Cada uso de una entidad marcada como obsoleta generará posteriormente una advertencia o un error, en función de la configuración del atributo.</span><span class="sxs-lookup"><span data-stu-id="e2044-157">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="e2044-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2044-158">For example:</span></span>

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

<span data-ttu-id="e2044-159">En este ejemplo, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="e2044-159">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="e2044-160">Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e2044-160">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="e2044-161">En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="e2044-161">Calling `B.NewMethod`, however, produces no warning or error.</span></span>

<span data-ttu-id="e2044-162">La cadena proporcionada como primer argumento al constructor de atributos se mostrará como parte de la advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="e2044-162">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="e2044-163">Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:</span><span class="sxs-lookup"><span data-stu-id="e2044-163">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

<span data-ttu-id="e2044-164">Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases.</span><span class="sxs-lookup"><span data-stu-id="e2044-164">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>

<span data-ttu-id="e2044-165">El atributo `Obsolete` se puede usar sin argumentos, aunque se recomienda incluir una explicación de por qué el elemento está obsoleto y qué se debe usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e2044-165">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>

<span data-ttu-id="e2044-166">El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos.</span><span class="sxs-lookup"><span data-stu-id="e2044-166">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="e2044-167">`Obsolete` es un alias de <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2044-167">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

## <a name="conditional-attribute"></a><a name="Conditional"></a><span data-ttu-id="e2044-168">Atributo Conditional</span><span class="sxs-lookup"><span data-stu-id="e2044-168">Conditional Attribute</span></span>

<span data-ttu-id="e2044-169">El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="e2044-169">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="e2044-170">El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="e2044-170">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="e2044-171">En este ejemplo, `Conditional` se aplica a un método para habilitar o deshabilitar la visualización de información de diagnóstico específica del programa:</span><span class="sxs-lookup"><span data-stu-id="e2044-171">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

<span data-ttu-id="e2044-172">Si el identificador `TRACE_ON` no está definido, no se mostrará ningún resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e2044-172">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>

<span data-ttu-id="e2044-173">El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración (pero no en las compilaciones de versión), como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2044-173">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

<span data-ttu-id="e2044-174">Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="e2044-174">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="e2044-175">Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="e2044-175">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="e2044-176">Usar `Conditional` es una alternativa más limpia, más elegante y menos propensa a generar errores para agregar métodos dentro de los bloques `#if…#endif`, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2044-176">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

<span data-ttu-id="e2044-177">Los métodos condicionales deben ser métodos de una declaración de clase o struct y no deben tener ningún valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e2044-177">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>

### <a name="using-multiple-identifiers"></a><span data-ttu-id="e2044-178">Usar varios identificadores</span><span class="sxs-lookup"><span data-stu-id="e2044-178">Using Multiple Identifiers</span></span>

<span data-ttu-id="e2044-179">Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si al menos uno de los símbolos condicionales está definido (es decir, si los símbolos están vinculados lógicamente entre sí mediante el operador OR).</span><span class="sxs-lookup"><span data-stu-id="e2044-179">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="e2044-180">En este ejemplo, la presencia de `A` o de `B` dará como resultado una llamada al método:</span><span class="sxs-lookup"><span data-stu-id="e2044-180">In this example, the presence of either `A` or `B` will result in a method call:</span></span>

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

<span data-ttu-id="e2044-181">Para lograr el efecto de una vinculación lógica de símbolos mediante el operador AND, puede definir métodos condicionales en serie.</span><span class="sxs-lookup"><span data-stu-id="e2044-181">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="e2044-182">Por ejemplo, el segundo método que se muestra a continuación solo se ejecutará si tanto `A` como `B` están definidos:</span><span class="sxs-lookup"><span data-stu-id="e2044-182">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="e2044-183">Usar Conditional con clases de atributos</span><span class="sxs-lookup"><span data-stu-id="e2044-183">Using Conditional with Attribute Classes</span></span>

<span data-ttu-id="e2044-184">El atributo `Conditional` también se puede aplicar a una definición de clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="e2044-184">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="e2044-185">En este ejemplo, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define DEBUG.</span><span class="sxs-lookup"><span data-stu-id="e2044-185">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a><span data-ttu-id="e2044-186">Atributos de información del llamador</span><span class="sxs-lookup"><span data-stu-id="e2044-186">Caller Info Attributes</span></span>

<span data-ttu-id="e2044-187">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="e2044-187">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="e2044-188">Puede obtener la ruta de acceso al código fuente, el número de línea del código fuente y el nombre del miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="e2044-188">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>

<span data-ttu-id="e2044-189">Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="e2044-189">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="e2044-190">Cada parámetro opcional especifica un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e2044-190">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="e2044-191">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e2044-191">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="e2044-192">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2044-192">Attribute</span></span>|<span data-ttu-id="e2044-193">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2044-193">Description</span></span>|<span data-ttu-id="e2044-194">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2044-194">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="e2044-195">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="e2044-195">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="e2044-196">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e2044-196">This is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="e2044-197">Número de línea del archivo de código fuente desde el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="e2044-197">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="e2044-198">Nombre de método o de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="e2044-198">Method name or property name of the caller.</span></span> <span data-ttu-id="e2044-199">Para obtener más información, vea [información del llamador (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="e2044-199">For more information, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>|`String`|

<span data-ttu-id="e2044-200">Para obtener más información sobre los atributos de información del llamador, vea [información del llamador (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="e2044-200">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>

## <a name="visual-basic-attributes"></a><a name="VB"></a><span data-ttu-id="e2044-201">Atributos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2044-201">Visual Basic Attributes</span></span>

<span data-ttu-id="e2044-202">En la tabla siguiente se enumeran los atributos que son específicos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e2044-202">The following table lists the attributes that are specific to Visual Basic.</span></span>

|<span data-ttu-id="e2044-203">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2044-203">Attribute</span></span>|<span data-ttu-id="e2044-204">Propósito</span><span class="sxs-lookup"><span data-stu-id="e2044-204">Purpose</span></span>|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|<span data-ttu-id="e2044-205">Indica al compilador que la clase debe exponerse como un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="e2044-205">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|<span data-ttu-id="e2044-206">Permite tener acceso a los miembros de módulo usando solo la calificación necesaria para el módulo.</span><span class="sxs-lookup"><span data-stu-id="e2044-206">Allows module members to be accessed using only the qualification needed for the module.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|<span data-ttu-id="e2044-207">Especifica el tamaño de una cadena de longitud fija en una estructura para su uso con funciones de entrada y salida de archivo.</span><span class="sxs-lookup"><span data-stu-id="e2044-207">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|<span data-ttu-id="e2044-208">Especifica el tamaño de una matriz fija en una estructura para su uso con funciones de entrada y salida de archivo.</span><span class="sxs-lookup"><span data-stu-id="e2044-208">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|

### <a name="comclassattribute"></a><span data-ttu-id="e2044-209">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="e2044-209">COMClassAttribute</span></span>

<span data-ttu-id="e2044-210">`COMClassAttribute`Se usa para simplificar el proceso de creación de componentes com a partir de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e2044-210">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="e2044-211">Los objetos COM son considerablemente diferentes de los ensamblados de .NET Framework y sin `COMClassAttribute` , debe seguir una serie de pasos para generar un objeto com a partir de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e2044-211">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="e2044-212">En el caso de las clases marcadas con `COMClassAttribute` , el compilador realiza muchos de estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e2044-212">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>

### <a name="hidemodulenameattribute"></a><span data-ttu-id="e2044-213">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="e2044-213">HideModuleNameAttribute</span></span>

<span data-ttu-id="e2044-214">Use `HideModuleNameAttribute` para permitir el acceso a los miembros de módulo usando solo la calificación necesaria para el módulo.</span><span class="sxs-lookup"><span data-stu-id="e2044-214">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>

### <a name="vbfixedstringattribute"></a><span data-ttu-id="e2044-215">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="e2044-215">VBFixedStringAttribute</span></span>

<span data-ttu-id="e2044-216">Use `VBFixedStringAttribute` para forzar Visual Basic para crear una cadena de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="e2044-216">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="e2044-217">Las cadenas son de longitud variable de forma predeterminada, y este atributo es útil cuando se almacenan cadenas en archivos.</span><span class="sxs-lookup"><span data-stu-id="e2044-217">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="e2044-218">El código siguiente muestra este proceso:</span><span class="sxs-lookup"><span data-stu-id="e2044-218">The following code demonstrates this:</span></span>

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a><span data-ttu-id="e2044-219">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="e2044-219">VBFixedArrayAttribute</span></span>

<span data-ttu-id="e2044-220">Use `VBFixedArrayAttribute` para declarar matrices de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="e2044-220">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="e2044-221">Al igual que las cadenas de Visual Basic, las matrices son de longitud variable de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e2044-221">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="e2044-222">Este atributo es útil al serializar o escribir datos en archivos.</span><span class="sxs-lookup"><span data-stu-id="e2044-222">This attribute is useful when serializing or writing data to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2044-223">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2044-223">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="e2044-224">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2044-224">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="e2044-225">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2044-225">Attributes</span></span>](../../../../standard/attributes/index.md)
- <span data-ttu-id="e2044-226">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2044-226">[Reflection (Visual Basic)](../reflection.md)</span></span>
- <span data-ttu-id="e2044-227">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2044-227">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>
