---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065172"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="b32a9-101">CA1417: OutAttribute en parámetros de cadena para P/Invoke</span><span class="sxs-lookup"><span data-stu-id="b32a9-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="b32a9-102">La regla [CA1417](/visualstudio/code-quality/ca1417) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="b32a9-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="b32a9-103">Genera una advertencia de compilación para cualquier definición del método de [invocación de plataforma (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) donde se pasa un parámetro <xref:System.String> por valor y se marca con <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b32a9-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b32a9-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b32a9-104">Change description</span></span>

<span data-ttu-id="b32a9-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="b32a9-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="b32a9-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="b32a9-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="b32a9-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="b32a9-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="b32a9-108">La regla CA1417 marca las definiciones del método [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) en las que un parámetro <xref:System.String> está marcado con el atributo <xref:System.Runtime.InteropServices.OutAttribute> y se pasa por valor.</span><span class="sxs-lookup"><span data-stu-id="b32a9-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="b32a9-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b32a9-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="b32a9-110">El entorno de ejecución de .NET mantiene una tabla, denominada grupo de internos, que contiene una sola referencia a cada cadena literal única en un programa.</span><span class="sxs-lookup"><span data-stu-id="b32a9-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="b32a9-111">Si una cadena internalizada marcada con <xref:System.Runtime.InteropServices.OutAttribute> se pasa por valor a un método P/Invoke, el entorno de ejecución se puede desestabilizar.</span><span class="sxs-lookup"><span data-stu-id="b32a9-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="b32a9-112">Para obtener más información sobre la asignación al grupo interno de cadenas, vea los comentarios sobre <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b32a9-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b32a9-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b32a9-113">Version introduced</span></span>

<span data-ttu-id="b32a9-114">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="b32a9-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b32a9-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b32a9-115">Recommended action</span></span>

- <span data-ttu-id="b32a9-116">Si necesita serializar los datos modificados de la cadena de vuelta al autor de la llamada, pase la cadena por referencia en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b32a9-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="b32a9-117">Si no necesita serializar los datos modificados de la cadena de vuelta al autor de la llamada, simplemente quite el elemento <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b32a9-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="b32a9-118">Para obtener más información, vea [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="b32a9-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="b32a9-119">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b32a9-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="b32a9-120">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="b32a9-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="b32a9-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="b32a9-121">Category</span></span>

<span data-ttu-id="b32a9-122">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="b32a9-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b32a9-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b32a9-123">Affected APIs</span></span>

<span data-ttu-id="b32a9-124">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="b32a9-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
