---
title: Atributos comunes (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 7988dad410c6e51869ec9d7e40d94e874443a5f8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595461"
---
# <a name="common-attributes-c"></a><span data-ttu-id="6ccfe-102">Atributos comunes (C#)</span><span class="sxs-lookup"><span data-stu-id="6ccfe-102">Common Attributes (C#)</span></span>
<span data-ttu-id="6ccfe-103">En este tema se describen los atributos que más se usan en los programas de C#.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
- [<span data-ttu-id="6ccfe-104">Atributos globales</span><span class="sxs-lookup"><span data-stu-id="6ccfe-104">Global Attributes</span></span>](#Global)  
  
- [<span data-ttu-id="6ccfe-105">Atributo Obsolete</span><span class="sxs-lookup"><span data-stu-id="6ccfe-105">Obsolete Attribute</span></span>](#Obsolete)  
  
- [<span data-ttu-id="6ccfe-106">Atributo Conditional</span><span class="sxs-lookup"><span data-stu-id="6ccfe-106">Conditional Attribute</span></span>](#Conditional)  
  
- [<span data-ttu-id="6ccfe-107">Atributos de información del llamador</span><span class="sxs-lookup"><span data-stu-id="6ccfe-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
## <a name="Global"></a> <span data-ttu-id="6ccfe-108">Atributos globales</span><span class="sxs-lookup"><span data-stu-id="6ccfe-108">Global Attributes</span></span>  
 <span data-ttu-id="6ccfe-109">La mayoría de los atributos se aplican a elementos específicos del lenguaje, como las clases o los métodos, aunque algunos atributos son globales (se aplican a todo un ensamblado o módulo).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="6ccfe-110">Por ejemplo, el atributo <xref:System.Reflection.AssemblyVersionAttribute> se puede usar para insertar información de versión en un ensamblado, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="6ccfe-111">Los atributos globales aparecen en el código fuente después de cualquier directiva `using` de nivel superior y antes de cualquier declaración de espacio de nombres, módulo o tipo.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="6ccfe-112">Los atributos globales pueden aparecer en varios archivos de código fuente, pero estos archivos se deben compilar en un solo paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="6ccfe-113">En los proyectos de C#, los atributos globales se colocan en el archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="6ccfe-114">Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="6ccfe-115">Se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-115">They fall into the following categories:</span></span>  
  
- <span data-ttu-id="6ccfe-116">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="6ccfe-116">Assembly identity attributes</span></span>  
  
- <span data-ttu-id="6ccfe-117">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="6ccfe-117">Informational attributes</span></span>  
  
- <span data-ttu-id="6ccfe-118">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="6ccfe-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="6ccfe-119">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="6ccfe-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="6ccfe-120">Tres atributos, con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="6ccfe-121">Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia a este en el código.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="6ccfe-122">Puede establecer la versión y la referencia cultural de un ensamblado mediante atributos,</span><span class="sxs-lookup"><span data-stu-id="6ccfe-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="6ccfe-123">pero el valor de nombre lo establece el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](/visualstudio/ide/reference/assembly-information-dialog-box) o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado, a partir del archivo que contiene el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="6ccfe-124">El atributo <xref:System.Reflection.AssemblyFlagsAttribute> especifica si pueden coexistir varias copias del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="6ccfe-125">En la siguiente tabla se muestran los atributos de identidad.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="6ccfe-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ccfe-126">Attribute</span></span>|<span data-ttu-id="6ccfe-127">Propósito</span><span class="sxs-lookup"><span data-stu-id="6ccfe-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="6ccfe-128">Describe completamente la identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="6ccfe-129">Especifica la versión de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="6ccfe-130">Especifica la cultura que admite el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="6ccfe-131">Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="6ccfe-132">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="6ccfe-132">Informational Attributes</span></span>  
 <span data-ttu-id="6ccfe-133">Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="6ccfe-134">En la tabla siguiente se muestran los atributos informativos definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="6ccfe-135">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ccfe-135">Attribute</span></span>|<span data-ttu-id="6ccfe-136">Propósito</span><span class="sxs-lookup"><span data-stu-id="6ccfe-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="6ccfe-137">Define un atributo personalizado que especifica un nombre de producto para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="6ccfe-138">Define un atributo personalizado que especifica una marca comercial para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="6ccfe-139">Define un atributo personalizado que especifica una versión informativa para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="6ccfe-140">Define un atributo personalizado que especifica un nombre de compañía para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="6ccfe-141">Define un atributo personalizado que especifica un copyright para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="6ccfe-142">Indica al compilador que use un número de versión específico para el recurso de versión de archivo Win32.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="6ccfe-143">Indica si el ensamblado es compatible con Common Language Specification (CLS).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="6ccfe-144">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="6ccfe-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="6ccfe-145">Puede usar los atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="6ccfe-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="6ccfe-146">(título, descripción, alias predeterminado y configuración).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="6ccfe-147">En la tabla siguiente se muestran los atributos de manifiesto del ensamblado definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="6ccfe-148">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ccfe-148">Attribute</span></span>|<span data-ttu-id="6ccfe-149">Propósito</span><span class="sxs-lookup"><span data-stu-id="6ccfe-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="6ccfe-150">Define un atributo personalizado que especifica un título de ensamblado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="6ccfe-151">Define un atributo personalizado que especifica una descripción de ensamblado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="6ccfe-152">Define un atributo personalizado que especifica una configuración de ensamblado (por ejemplo, comercial o depuración) para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="6ccfe-153">Define un alias descriptivo predeterminado para un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
## <a name="Obsolete"></a> <span data-ttu-id="6ccfe-154">Atributo Obsolete</span><span class="sxs-lookup"><span data-stu-id="6ccfe-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="6ccfe-155">El atributo `Obsolete` marca una entidad del programa como una entidad cuyo uso ya no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="6ccfe-156">Cada uso de una entidad marcada como obsoleta generará posteriormente una advertencia o un error, en función de la configuración del atributo.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="6ccfe-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="6ccfe-158">En este ejemplo, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="6ccfe-159">Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="6ccfe-160">En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="6ccfe-161">La cadena proporcionada como primer argumento al constructor de atributos se mostrará como parte de la advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="6ccfe-162">Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="6ccfe-163">Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="6ccfe-164">El atributo `Obsolete` se puede usar sin argumentos, aunque se recomienda incluir una explicación de por qué el elemento está obsoleto y qué se debe usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="6ccfe-165">El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="6ccfe-166">`Obsolete` es un alias de <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
## <a name="Conditional"></a> <span data-ttu-id="6ccfe-167">Atributo Conditional</span><span class="sxs-lookup"><span data-stu-id="6ccfe-167">Conditional Attribute</span></span>  
 <span data-ttu-id="6ccfe-168">El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="6ccfe-169">El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="6ccfe-170">En este ejemplo, `Conditional` se aplica a un método para habilitar o deshabilitar la visualización de información de diagnóstico específica del programa:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="6ccfe-171">Si el identificador `TRACE_ON` no está definido, no se mostrará ningún resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="6ccfe-172">El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración (pero no en las compilaciones de versión), como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="6ccfe-173">Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="6ccfe-174">Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="6ccfe-175">Usar `Conditional` es una alternativa más limpia, más elegante y menos propensa a generar errores para agregar métodos dentro de los bloques `#if…#endif`, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="6ccfe-176">Los métodos condicionales deben ser métodos de una declaración de clase o struct y no deben tener ningún valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="6ccfe-177">Usar varios identificadores</span><span class="sxs-lookup"><span data-stu-id="6ccfe-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="6ccfe-178">Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si al menos uno de los símbolos condicionales está definido (es decir, si los símbolos están vinculados lógicamente entre sí mediante el operador OR).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="6ccfe-179">En este ejemplo, la presencia de `A` o de `B` dará como resultado una llamada al método:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="6ccfe-180">Para lograr el efecto de una vinculación lógica de símbolos mediante el operador AND, puede definir métodos condicionales en serie.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="6ccfe-181">Por ejemplo, el segundo método que se muestra a continuación solo se ejecutará si tanto `A` como `B` están definidos:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="6ccfe-182">Usar Conditional con clases de atributos</span><span class="sxs-lookup"><span data-stu-id="6ccfe-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="6ccfe-183">El atributo `Conditional` también se puede aplicar a una definición de clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="6ccfe-184">En este ejemplo, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define DEBUG.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
## <a name="CallerInfo"></a> <span data-ttu-id="6ccfe-185">Atributos de información del llamador</span><span class="sxs-lookup"><span data-stu-id="6ccfe-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="6ccfe-186">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="6ccfe-187">Puede obtener la ruta de acceso al código fuente, el número de línea del código fuente y el nombre del miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="6ccfe-188">Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="6ccfe-189">Cada parámetro opcional especifica un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="6ccfe-190">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="6ccfe-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="6ccfe-191">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ccfe-191">Attribute</span></span>|<span data-ttu-id="6ccfe-192">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6ccfe-192">Description</span></span>|<span data-ttu-id="6ccfe-193">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ccfe-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="6ccfe-194">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="6ccfe-195">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="6ccfe-196">Número de línea del archivo de código fuente desde el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="6ccfe-197">Nombre de método o de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-197">Method name or property name of the caller.</span></span> <span data-ttu-id="6ccfe-198">Para obtener más información, vea [Información del llamador (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-198">For more information, see [Caller Information (C#)](../caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="6ccfe-199">Para obtener más información sobre los atributos de información del llamador, vea [Información del llamador (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="6ccfe-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ccfe-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ccfe-200">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="6ccfe-201">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6ccfe-201">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="6ccfe-202">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ccfe-202">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="6ccfe-203">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="6ccfe-203">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="6ccfe-204">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="6ccfe-204">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
