---
ms.openlocfilehash: e3c9f23ca73ed9b85d09680ec15251ebe02c7f8e
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065215"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="0f080-101">CA1416: Compatibilidad de plataformas</span><span class="sxs-lookup"><span data-stu-id="0f080-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="0f080-102">La regla CA1416 del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="0f080-102">.NET code analyzer rule CA1416 is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="0f080-103">Genera una advertencia de compilación para las llamadas a API específicas de la plataforma desde sitios de llamada que no comprueban el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0f080-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0f080-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="0f080-104">Change description</span></span>

<span data-ttu-id="0f080-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0f080-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="0f080-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla CA1416.</span><span class="sxs-lookup"><span data-stu-id="0f080-106">Several of these rules are enabled, by default, including CA1416.</span></span> <span data-ttu-id="0f080-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="0f080-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="0f080-108">La regla CA1416 le notifica cuando está usando API específicas de la plataforma desde lugares donde no se comprueba el contexto de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0f080-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="0f080-109">La regla CA1416, el analizador de compatibilidad de la plataforma, funciona conjuntamente con otras características que son nuevas en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="0f080-109">Rule CA1416, the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="0f080-110">.NET 5.0 presenta los atributos `SupportedOSPlatformAttribute` y `UnsupportedOSPlatformAttribute` (denominados <xref:System.Runtime.Versioning.MinimumOSPlatformAttribute> y <xref:System.Runtime.Versioning.RemovedInOSPlatformAttribute> en una versión preliminar anterior), que permiten especificar las plataformas que *admiten* o *no admiten* una API.</span><span class="sxs-lookup"><span data-stu-id="0f080-110">.NET 5.0 introduces `SupportedOSPlatformAttribute` and `UnsupportedOSPlatformAttribute` attributes (named <xref:System.Runtime.Versioning.MinimumOSPlatformAttribute> and <xref:System.Runtime.Versioning.RemovedInOSPlatformAttribute> in an earlier preview release), which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="0f080-111">En ausencia de estos atributos, se supone que se admite una API en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="0f080-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="0f080-112">Estos atributos se han aplicado a muchas API específicas de la plataforma en las bibliotecas principales de .NET.</span><span class="sxs-lookup"><span data-stu-id="0f080-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="0f080-113">En los proyectos que tienen como destino las plataformas para las que no están disponibles las API que usan, la regla CA1416 marca cualquier llamada API específica de la plataforma en la que no se comprueba el contexto de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0f080-113">In projects that target platforms for which APIs that they use aren't available, rule CA1416 flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="0f080-114">La mayoría de las API que ahora están representadas con los atributos `SupportedOSPlatformAttribute` y `UnsupportedOSPlatformAttribute` producen excepciones <xref:System.PlatformNotSupportedException> cuando se invocan en un sistema operativo no compatible.</span><span class="sxs-lookup"><span data-stu-id="0f080-114">Most of the APIs that are now decorated with the `SupportedOSPlatformAttribute` and `UnsupportedOSPlatformAttribute` attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="0f080-115">Ahora que estas API están marcadas como específicas de la plataforma, la regla CA1416 ayuda a evitar excepciones <xref:System.PlatformNotSupportedException> en tiempo de ejecución agregando comprobaciones del sistema operativo a los sitios de llamada.</span><span class="sxs-lookup"><span data-stu-id="0f080-115">Now that these APIs are marked as platform-specific, rule CA1416 helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="0f080-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0f080-116">Examples</span></span>

- <span data-ttu-id="0f080-117">El método <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> solo se admite en Windows (está decorado con el atributo `[SupportedOSPlatform("windows")]`).</span><span class="sxs-lookup"><span data-stu-id="0f080-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows (it's decorated with `[SupportedOSPlatform("windows")]`).</span></span> <span data-ttu-id="0f080-118">El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto [tiene como destino](../../../../docs/standard/frameworks.md) `net5.0` (pero no `net5.0-windows`).</span><span class="sxs-lookup"><span data-stu-id="0f080-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="0f080-119">Para ver las acciones que puede realizar para evitar la advertencia, consulte la sección [Acción recomendada](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="0f080-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="0f080-120">El método <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> no se admite en el explorador (está decorado con el atributo `[UnsupportedOSPlatform("browser")]`).</span><span class="sxs-lookup"><span data-stu-id="0f080-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser (it's decorated with `[UnsupportedOSPlatform("browser")]`).</span></span> <span data-ttu-id="0f080-121">El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto usa el SDK de WebAssembly de Blazor (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) o si incluye `browser` como plataforma compatible (`<SupportedPlatform Include="browser" />`) en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f080-121">The following code will produce a CA1416 warning at build time if the project uses the Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) or includes `browser` as a supported platform (`<SupportedPlatform Include="browser" />`) in the project file.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a><span data-ttu-id="0f080-122">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0f080-122">Version introduced</span></span>

<span data-ttu-id="0f080-123">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="0f080-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0f080-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="0f080-124">Recommended action</span></span>

<span data-ttu-id="0f080-125">Asegúrese de que solo se llama a las API específicas de la plataforma cuando el código se ejecuta en la plataforma adecuada.</span><span class="sxs-lookup"><span data-stu-id="0f080-125">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="0f080-126">Puede comprobar el sistema operativo actual mediante uno de los métodos `Is<Platform>` de la clase <xref:System.OperatingSystem?displayProperty=nameWithType> (por ejemplo, `System.OperatingSystem.IsWindows()`) antes de llamar a una API específica de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0f080-126">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, `System.OperatingSystem.IsWindows()`, before calling a platform-specific API.</span></span>

<span data-ttu-id="0f080-127">Puede usar uno de los métodos `Is<Platform>` en la condición de una instrucción `if`:</span><span class="sxs-lookup"><span data-stu-id="0f080-127">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="0f080-128">O bien, si no quiere sobrecargar una instrucción `if` adicional en tiempo de ejecución, llame a <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> en su lugar:</span><span class="sxs-lookup"><span data-stu-id="0f080-128">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0f080-129">También puede marcar la API como específica de la plataforma, en cuyo caso la tarea de comprobar los requisitos corresponde a los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="0f080-129">You can also mark your API as platform-specific, in which case the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="0f080-130">Puede marcar métodos o tipos específicos, o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="0f080-130">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0f080-131">Si no quiere corregir todos los sitios de llamada, puede elegir una de las siguientes opciones para suprimir la advertencia:</span><span class="sxs-lookup"><span data-stu-id="0f080-131">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="0f080-132">Para suprimir la regla CA1416, puede usar `#pragma` o la marca del compilador [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md), o bien puede [establecer la gravedad de la regla](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) en `none` en un archivo .editorconfig.</span><span class="sxs-lookup"><span data-stu-id="0f080-132">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="0f080-133">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f080-133">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="0f080-134">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="0f080-134">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="0f080-135">Categoría</span><span class="sxs-lookup"><span data-stu-id="0f080-135">Category</span></span>

- <span data-ttu-id="0f080-136">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="0f080-136">Code analysis</span></span>
- <span data-ttu-id="0f080-137">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="0f080-137">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0f080-138">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0f080-138">Affected APIs</span></span>

<span data-ttu-id="0f080-139">Para la plataforma Windows:</span><span class="sxs-lookup"><span data-stu-id="0f080-139">For Windows platform:</span></span>

- <span data-ttu-id="0f080-140">Todas las API que se enumeran en <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span><span class="sxs-lookup"><span data-stu-id="0f080-140">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="0f080-141">Para la plataforma de WebAssembly de Blazor:</span><span class="sxs-lookup"><span data-stu-id="0f080-141">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="0f080-142">Todas las API que se enumeran en <https://github.com/dotnet/runtime/issues/41087>.</span><span class="sxs-lookup"><span data-stu-id="0f080-142">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="0f080-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f080-143">See also</span></span>

- [<span data-ttu-id="0f080-144">Analizador de API en .NET</span><span class="sxs-lookup"><span data-stu-id="0f080-144">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
