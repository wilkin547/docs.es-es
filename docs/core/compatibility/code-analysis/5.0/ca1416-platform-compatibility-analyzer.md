---
title: 'Cambio importante: CA1416: Compatibilidad de plataformas'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA1416.
ms.date: 09/29/2020
ms.openlocfilehash: fa03e1f0bfa8438b3b2899aaf7c97f42533c7c02
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477550"
---
# <a name="warning-ca1416-platform-compatibility"></a><span data-ttu-id="6038b-103">Advertencia CA1416: Compatibilidad de plataformas</span><span class="sxs-lookup"><span data-stu-id="6038b-103">Warning CA1416: Platform compatibility</span></span>

<span data-ttu-id="6038b-104">La regla [CA1416](/visualstudio/code-quality/ca1416) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="6038b-104">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="6038b-105">Genera una advertencia de compilación para las llamadas a API específicas de la plataforma desde sitios de llamada que no comprueban el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6038b-105">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

## <a name="change-description"></a><span data-ttu-id="6038b-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="6038b-106">Change description</span></span>

<span data-ttu-id="6038b-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="6038b-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="6038b-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1416](/visualstudio/code-quality/ca1416).</span><span class="sxs-lookup"><span data-stu-id="6038b-108">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="6038b-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="6038b-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="6038b-110">La regla CA1416 le notifica cuando está usando API específicas de la plataforma desde lugares donde no se comprueba el contexto de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6038b-110">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="6038b-111">La regla [CA1416](/visualstudio/code-quality/ca1416), el analizador de compatibilidad de la plataforma, funciona conjuntamente con otras características que son nuevas en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="6038b-111">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="6038b-112">.NET 5 presenta <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, que permiten especificar las plataformas en las que una API *se admite* o *no se admite*.</span><span class="sxs-lookup"><span data-stu-id="6038b-112">.NET 5 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="6038b-113">En ausencia de estos atributos, se supone que se admite una API en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="6038b-113">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="6038b-114">Estos atributos se han aplicado a muchas API específicas de la plataforma en las bibliotecas principales de .NET.</span><span class="sxs-lookup"><span data-stu-id="6038b-114">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="6038b-115">En los proyectos que tienen como destino las plataformas para las que no están disponibles las API que usan, la regla [CA1416](/visualstudio/code-quality/ca1416) marca cualquier llamada API específica de la plataforma en la que no se comprueba el contexto de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6038b-115">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="6038b-116">La mayoría de las API que ahora están representadas con los atributos <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> producen excepciones <xref:System.PlatformNotSupportedException> cuando se invocan en un sistema operativo no compatible.</span><span class="sxs-lookup"><span data-stu-id="6038b-116">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="6038b-117">Ahora que estas API están marcadas como específicas de la plataforma, la regla [CA1416](/visualstudio/code-quality/ca1416) ayuda a evitar excepciones <xref:System.PlatformNotSupportedException> en tiempo de ejecución mediante la adición de comprobaciones del sistema operativo a los sitios de llamada.</span><span class="sxs-lookup"><span data-stu-id="6038b-117">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

## <a name="examples"></a><span data-ttu-id="6038b-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6038b-118">Examples</span></span>

- <span data-ttu-id="6038b-119">El método <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> solo se admite en Windows y está decorado con el atributo `[SupportedOSPlatform("windows")]`.</span><span class="sxs-lookup"><span data-stu-id="6038b-119">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows and is decorated with `[SupportedOSPlatform("windows")]`.</span></span> <span data-ttu-id="6038b-120">El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto [tiene como destino](../../../../standard/frameworks.md) `net5.0` (pero no `net5.0-windows`).</span><span class="sxs-lookup"><span data-stu-id="6038b-120">The following code will produce a CA1416 warning at build time if the project [targets](../../../../standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="6038b-121">Para ver las acciones que puede realizar para evitar la advertencia, consulte la sección [Acción recomendada](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="6038b-121">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="6038b-122">El método <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> no se admite en el explorador y está decorado con el atributo `[UnsupportedOSPlatform("browser")]`.</span><span class="sxs-lookup"><span data-stu-id="6038b-122">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser and is decorated with `[UnsupportedOSPlatform("browser")]`.</span></span> <span data-ttu-id="6038b-123">El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto admite la plataforma del explorador.</span><span class="sxs-lookup"><span data-stu-id="6038b-123">The following code will produce a CA1416 warning at build time if the project supports the browser platform.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - <span data-ttu-id="6038b-124">Los proyectos de Blazor WebAssembly y los de la biblioteca de clases de Razor incluyen compatibilidad con los exploradores automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6038b-124">Blazor WebAssembly projects and Razor class library projects include browser support automatically.</span></span>
  > - <span data-ttu-id="6038b-125">Para agregar de forma manual el explorador como una plataforma compatible para el proyecto, agregue la entrada siguiente al archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="6038b-125">To manually add the browser as a supported platform for your project, add the following entry to your project file:</span></span>
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

## <a name="version-introduced"></a><span data-ttu-id="6038b-126">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6038b-126">Version introduced</span></span>

<span data-ttu-id="6038b-127">5.0</span><span class="sxs-lookup"><span data-stu-id="6038b-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6038b-128">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6038b-128">Recommended action</span></span>

<span data-ttu-id="6038b-129">Asegúrese de que solo se llama a las API específicas de la plataforma cuando el código se ejecuta en la plataforma adecuada.</span><span class="sxs-lookup"><span data-stu-id="6038b-129">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="6038b-130">Puede comprobar el sistema operativo actual mediante uno de los métodos `Is<Platform>` de la clase <xref:System.OperatingSystem?displayProperty=nameWithType> (por ejemplo, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>) antes de llamar a una API específica de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6038b-130">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="6038b-131">Puede usar uno de los métodos `Is<Platform>` en la condición de una instrucción `if`:</span><span class="sxs-lookup"><span data-stu-id="6038b-131">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="6038b-132">O bien, si no quiere sobrecargar una instrucción `if` adicional en tiempo de ejecución, llame a <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> en su lugar:</span><span class="sxs-lookup"><span data-stu-id="6038b-132">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="6038b-133">Si va a crear una biblioteca, puede marcar la API como específica de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6038b-133">If you're authoring a library, you can mark your API as platform-specific.</span></span> <span data-ttu-id="6038b-134">En este caso, la carga de los requisitos de comprobación recae en los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="6038b-134">In this case, the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="6038b-135">Puede marcar métodos o tipos específicos, o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="6038b-135">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="6038b-136">Si no quiere corregir todos los sitios de llamada, puede elegir una de las siguientes opciones para suprimir la advertencia:</span><span class="sxs-lookup"><span data-stu-id="6038b-136">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="6038b-137">Para suprimir la regla CA1416, puede usar `#pragma` o la marca del compilador [**DisabledWarnings**](../../../../csharp/language-reference/compiler-options/errors-warnings.md#disabledwarnings), o bien [establecer la gravedad de la regla](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) en `none` en un archivo .editorconfig.</span><span class="sxs-lookup"><span data-stu-id="6038b-137">To suppress rule CA1416, you can do so using `#pragma` or the [**DisabledWarnings**](../../../../csharp/language-reference/compiler-options/errors-warnings.md#disabledwarnings) compiler flag, or by [setting the rule's severity](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="6038b-138">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6038b-138">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="6038b-139">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="6038b-139">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6038b-140">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6038b-140">Affected APIs</span></span>

<span data-ttu-id="6038b-141">Para la plataforma Windows:</span><span class="sxs-lookup"><span data-stu-id="6038b-141">For Windows platform:</span></span>

- <span data-ttu-id="6038b-142">Todas las API que se enumeran en <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span><span class="sxs-lookup"><span data-stu-id="6038b-142">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="6038b-143">Para la plataforma de WebAssembly de Blazor:</span><span class="sxs-lookup"><span data-stu-id="6038b-143">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="6038b-144">Todas las API que se enumeran en <https://github.com/dotnet/runtime/issues/41087>.</span><span class="sxs-lookup"><span data-stu-id="6038b-144">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

### Affected APIs

- ``

### Category

- Code analysis
- Core .NET libraries

-->

## <a name="see-also"></a><span data-ttu-id="6038b-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6038b-145">See also</span></span>

- [<span data-ttu-id="6038b-146">CA1416: Validación de la compatibilidad con las plataformas</span><span class="sxs-lookup"><span data-stu-id="6038b-146">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="6038b-147">Analizador de API en .NET</span><span class="sxs-lookup"><span data-stu-id="6038b-147">.NET API analyzer</span></span>](../../../../standard/analyzers/api-analyzer.md)
