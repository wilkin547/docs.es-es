---
title: Suprimir advertencias de análisis de código
description: Obtenga información sobre las distintas formas en las que puede suprimir las infracciones de análisis de código .NET.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: b08e93089975a59fabfeb0daaf6a2a6454b2c7e8
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217268"
---
# <a name="how-to-suppress-code-analysis-warnings"></a><span data-ttu-id="2a69c-103">Cómo suprimir advertencias de análisis de código</span><span class="sxs-lookup"><span data-stu-id="2a69c-103">How to suppress code analysis warnings</span></span>

<span data-ttu-id="2a69c-104">En este artículo se tratan las distintas formas en las que puede suprimir las advertencias del análisis de código al compilar la aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="2a69c-104">This article covers the various ways you can suppress warnings from code analysis when you build your .NET app.</span></span>

> [!TIP]
> <span data-ttu-id="2a69c-105">Si utiliza Visual Studio como entorno de desarrollo, el menú de *bombilla* proporciona opciones que generan el código para suprimir las advertencias.</span><span class="sxs-lookup"><span data-stu-id="2a69c-105">If you're using Visual Studio as your development environment, the *light bulb* menu provides options that generate the code to suppress warnings for you.</span></span> <span data-ttu-id="2a69c-106">Para obtener más información, vea [suprimir infracciones](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).</span><span class="sxs-lookup"><span data-stu-id="2a69c-106">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).</span></span>

## <a name="disable-the-rule"></a><span data-ttu-id="2a69c-107">Deshabilitar la regla</span><span class="sxs-lookup"><span data-stu-id="2a69c-107">Disable the rule</span></span>

<span data-ttu-id="2a69c-108">Al deshabilitar la regla de análisis de código que está causando la advertencia, deshabilitará la regla para todo el archivo o proyecto (según el ámbito del [archivo de configuración](configuration-files.md) que use).</span><span class="sxs-lookup"><span data-stu-id="2a69c-108">By disabling the code analysis rule that's causing the warning, you disable the rule for your entire file or project (depending on the scope of the [configuration file](configuration-files.md) that you use).</span></span> <span data-ttu-id="2a69c-109">Para deshabilitar la regla, establezca su gravedad `none` en en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2a69c-109">To disable the rule, set its severity to `none` in the configuration file.</span></span>

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

<span data-ttu-id="2a69c-110">Para obtener más información sobre los niveles de gravedad de las reglas, consulte [configurar la gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)de la regla.</span><span class="sxs-lookup"><span data-stu-id="2a69c-110">For more information about rule severities, see [Configure rule severity](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span></span>

## <a name="use-a-preprocessor-directive"></a><span data-ttu-id="2a69c-111">Usar una directiva de preprocesador</span><span class="sxs-lookup"><span data-stu-id="2a69c-111">Use a preprocessor directive</span></span>

<span data-ttu-id="2a69c-112">Utilice una directiva [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) o [disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) para suprimir la advertencia solo para una línea de código específica.</span><span class="sxs-lookup"><span data-stu-id="2a69c-112">Use a [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) or [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) directive to suppress the warning for only a specific line of code.</span></span>

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

## <a name="use-the-suppressmessageattribute"></a><span data-ttu-id="2a69c-113">Usar el SuppressMessageAttribute</span><span class="sxs-lookup"><span data-stu-id="2a69c-113">Use the SuppressMessageAttribute</span></span>

<span data-ttu-id="2a69c-114">Puede usar un <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> para suprimir una advertencia en el archivo de código fuente o en un archivo de supresiones globales para el proyecto (*GlobalSuppressions.CS* o *GlobalSuppressions. VB*).</span><span class="sxs-lookup"><span data-stu-id="2a69c-114">You can use a <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> to suppress a warning either in the source file or in a global suppressions file for the project (*GlobalSuppressions.cs* or *GlobalSuppressions.vb*).</span></span> <span data-ttu-id="2a69c-115">Este atributo proporciona una manera de suprimir una advertencia solo en determinadas partes del proyecto o archivo.</span><span class="sxs-lookup"><span data-stu-id="2a69c-115">This attribute provides a way to suppress a warning in only certain parts of your project or file.</span></span>

<span data-ttu-id="2a69c-116">Los dos parámetros posicionales obligatorios para el <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atributo son la *categoría* de la regla y el *identificador* de la regla.</span><span class="sxs-lookup"><span data-stu-id="2a69c-116">The two required, positional parameters for the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> attribute are the *category* of the rule and the *rule ID*.</span></span> <span data-ttu-id="2a69c-117">El siguiente fragmento de código pasa `"Usage"` y `"CA2200:Rethrow to preserve stack details"` para estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="2a69c-117">The following code snippet passes `"Usage"` and `"CA2200:Rethrow to preserve stack details"` for these parameters.</span></span>

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

<span data-ttu-id="2a69c-118">Si agrega el atributo al archivo de supresiones globales, el [ámbito](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) de la supresión se limita al nivel deseado, por ejemplo `"member"` .</span><span class="sxs-lookup"><span data-stu-id="2a69c-118">If you add the attribute to the global suppressions file, you [scope](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) the suppression to the desired level, for example `"member"`.</span></span> <span data-ttu-id="2a69c-119">Especifique la API en la que se debe suprimir la advertencia mediante la <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a69c-119">You specify the API where the warning should be suppressed using the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> property.</span></span>

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

<span data-ttu-id="2a69c-120">Para suprimir las advertencias del código generado por el compilador que no se asignan al origen de usuario proporcionado explícitamente, debe colocar el atributo de supresión en un archivo de supresiones global.</span><span class="sxs-lookup"><span data-stu-id="2a69c-120">To suppress warnings for compiler-generated code that doesn't map to explicitly provided user source, you must put the suppression attribute in a global suppressions file.</span></span> <span data-ttu-id="2a69c-121">Por ejemplo, el siguiente código suprime una infracción en un constructor emitido por compilador:</span><span class="sxs-lookup"><span data-stu-id="2a69c-121">For example, the following code suppresses a violation against a compiler-emitted constructor:</span></span>

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a><span data-ttu-id="2a69c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a69c-122">See also</span></span>

- [<span data-ttu-id="2a69c-123">Suprimir infracciones (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="2a69c-123">Suppress violations (Visual Studio)</span></span>](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
