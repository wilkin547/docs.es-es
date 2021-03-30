---
title: Supresión de advertencias de análisis de código
description: Obtenga más información sobre las distintas formas de suprimir infracciones de análisis del código de .NET.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: a8fdfbddd2393f9c6c8cd882a63a9ecc6cb1dc95
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105637044"
---
# <a name="how-to-suppress-code-analysis-warnings"></a><span data-ttu-id="2ea74-103">Procedimiento para suprimir advertencias de análisis de código</span><span class="sxs-lookup"><span data-stu-id="2ea74-103">How to suppress code analysis warnings</span></span>

<span data-ttu-id="2ea74-104">En este artículo se tratan las distintas formas de suprimir advertencias de análisis del código al compilar una aplicación de .NET.</span><span class="sxs-lookup"><span data-stu-id="2ea74-104">This article covers the various ways you can suppress warnings from code analysis when you build your .NET app.</span></span>

> [!TIP]
> <span data-ttu-id="2ea74-105">Si utiliza Visual Studio como entorno de desarrollo, el menú de *bombilla* proporciona opciones que generan el código para suprimir las advertencias.</span><span class="sxs-lookup"><span data-stu-id="2ea74-105">If you're using Visual Studio as your development environment, the *light bulb* menu provides options that generate the code to suppress warnings for you.</span></span> <span data-ttu-id="2ea74-106">Para obtener más información, consulte [Supresión de infracciones](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).</span><span class="sxs-lookup"><span data-stu-id="2ea74-106">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).</span></span>

## <a name="disable-the-rule"></a><span data-ttu-id="2ea74-107">Deshabilitación de la regla</span><span class="sxs-lookup"><span data-stu-id="2ea74-107">Disable the rule</span></span>

<span data-ttu-id="2ea74-108">Al deshabilitar la regla de análisis de código que causa la advertencia, deshabilitará la regla para todo el archivo o proyecto (según el ámbito del [archivo de configuración](configuration-files.md) que use).</span><span class="sxs-lookup"><span data-stu-id="2ea74-108">By disabling the code analysis rule that's causing the warning, you disable the rule for your entire file or project (depending on the scope of the [configuration file](configuration-files.md) that you use).</span></span> <span data-ttu-id="2ea74-109">Para deshabilitar la regla, establezca su gravedad en `none` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ea74-109">To disable the rule, set its severity to `none` in the configuration file.</span></span>

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

<span data-ttu-id="2ea74-110">Para obtener más información sobre los niveles de gravedad de las reglas, consulte [Nivel de gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="2ea74-110">For more information about rule severities, see [Configure rule severity](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span></span>

## <a name="use-a-preprocessor-directive"></a><span data-ttu-id="2ea74-111">Uso de una directiva de preprocesador</span><span class="sxs-lookup"><span data-stu-id="2ea74-111">Use a preprocessor directive</span></span>

<span data-ttu-id="2ea74-112">Use una directiva [Advertencia #pragma (C#)](../../csharp/language-reference/preprocessor-directives.md#pragma-warning) o [Deshabilitar (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) para suprimir la advertencia solo para una línea de código específica.</span><span class="sxs-lookup"><span data-stu-id="2ea74-112">Use a [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives.md#pragma-warning) or [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) directive to suppress the warning for only a specific line of code.</span></span>

```csharp
    try { ... }
    catch (Exception e)
    {
#pragma warning disable CA2200 // Rethrow to preserve stack details
        throw e;
#pragma warning restore CA2200 // Rethrow to preserve stack details
    }
```

```vb
    Try
        ...
    Catch e As Exception
#Disable Warning CA2200 ' Rethrow to preserve stack details
        Throw e
#Enable Warning CA2200 ' Rethrow to preserve stack details
    End Try
```

## <a name="use-the-suppressmessageattribute"></a><span data-ttu-id="2ea74-113">Uso de SuppressMessageAttribute</span><span class="sxs-lookup"><span data-stu-id="2ea74-113">Use the SuppressMessageAttribute</span></span>

<span data-ttu-id="2ea74-114">Puede usar <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> para suprimir una advertencia en el archivo de código fuente o en un archivo de supresiones globales para el proyecto (*GlobalSuppressions.cs* o *GlobalSuppressions.vb*).</span><span class="sxs-lookup"><span data-stu-id="2ea74-114">You can use a <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> to suppress a warning either in the source file or in a global suppressions file for the project (*GlobalSuppressions.cs* or *GlobalSuppressions.vb*).</span></span> <span data-ttu-id="2ea74-115">Este atributo proporciona una manera de suprimir una advertencia solo en determinadas partes del proyecto o archivo.</span><span class="sxs-lookup"><span data-stu-id="2ea74-115">This attribute provides a way to suppress a warning in only certain parts of your project or file.</span></span>

<span data-ttu-id="2ea74-116">Los dos parámetros posicionales requeridos para el atributo <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> son la *categoría* de la regla y el *identificador de la regla*.</span><span class="sxs-lookup"><span data-stu-id="2ea74-116">The two required, positional parameters for the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> attribute are the *category* of the rule and the *rule ID*.</span></span> <span data-ttu-id="2ea74-117">El siguiente fragmento de código pasa `"Usage"` y `"CA2200:Rethrow to preserve stack details"` para estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="2ea74-117">The following code snippet passes `"Usage"` and `"CA2200:Rethrow to preserve stack details"` for these parameters.</span></span>

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.")]
private static void IngorableCharacters()
{
    try
    {
        ...
    }
    catch (Exception e)
    {
        throw e;
    }
}
```

<span data-ttu-id="2ea74-118">Si agrega el atributo al archivo de supresiones globales, el [ámbito](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) de la supresión quedará limitado al nivel deseado, por ejemplo, `"member"`.</span><span class="sxs-lookup"><span data-stu-id="2ea74-118">If you add the attribute to the global suppressions file, you [scope](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) the suppression to the desired level, for example `"member"`.</span></span> <span data-ttu-id="2ea74-119">Especifique la API en la que se debe suprimir la advertencia mediante la propiedad <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target>.</span><span class="sxs-lookup"><span data-stu-id="2ea74-119">You specify the API where the warning should be suppressed using the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> property.</span></span>

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

<span data-ttu-id="2ea74-120">En el caso del código generado por el compilador que no se asigna explícitamente al código fuente que el usuario ha proporcionado, para suprimir las advertencias debe colocar el atributo de supresión en un archivo de supresiones globales.</span><span class="sxs-lookup"><span data-stu-id="2ea74-120">To suppress warnings for compiler-generated code that doesn't map to explicitly provided user source, you must put the suppression attribute in a global suppressions file.</span></span> <span data-ttu-id="2ea74-121">Por ejemplo, el siguiente código suprime una infracción en un constructor emitido por el compilador:</span><span class="sxs-lookup"><span data-stu-id="2ea74-121">For example, the following code suppresses a violation against a compiler-emitted constructor:</span></span>

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a><span data-ttu-id="2ea74-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ea74-122">See also</span></span>

- [<span data-ttu-id="2ea74-123">Supresión de infracciones (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="2ea74-123">Suppress violations (Visual Studio)</span></span>](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
