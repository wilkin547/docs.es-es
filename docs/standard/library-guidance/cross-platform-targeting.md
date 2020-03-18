---
title: Destino multiplataforma para bibliotecas de .NET
description: Procedimientos recomendados para la creación de bibliotecas de .NET multiplataforma.
ms.date: 08/12/2019
ms.openlocfilehash: 61adff3759984554bb83531b4f9d8a49e29c929c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731448"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="14250-103">Destinatarios multiplataforma</span><span class="sxs-lookup"><span data-stu-id="14250-103">Cross-platform targeting</span></span>

<span data-ttu-id="14250-104">La plataforma .NET moderna es compatible con varios sistemas operativos y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14250-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="14250-105">Es importante para las bibliotecas de código abierto de .NET admitir tantos desarrolladores como sea posible, ya sea que esté creando un sitio web ASP.NET hospedado en Azure o un juego de .NET en Unity.</span><span class="sxs-lookup"><span data-stu-id="14250-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="14250-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="14250-106">.NET Standard</span></span>

<span data-ttu-id="14250-107">.NET Standard es la mejor manera de agregar compatibilidad multiplataforma a una biblioteca de .NET.</span><span class="sxs-lookup"><span data-stu-id="14250-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="14250-108">[.NET Standard](../net-standard.md) es una especificación de API de .NET que se prevé que esté disponible en todas las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="14250-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="14250-109">El destino .NET Standard le permite generar bibliotecas que están limitadas a usar las API que se encuentran en una versión concreta de .NET Standard, lo que significa que la pueden usar todas las plataformas que implementan esa versión de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="14250-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="14250-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="14250-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="14250-111">El destino .NET Standard, así como la compilación correcta del proyecto, no garantiza que la biblioteca se ejecutará correctamente en todas las plataformas:</span><span class="sxs-lookup"><span data-stu-id="14250-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="14250-112">Las API específicas de plataforma producirán un error en otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="14250-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="14250-113">Por ejemplo, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> se llevará a cabo correctamente en Windows y generará <xref:System.PlatformNotSupportedException> cuando se utilice en cualquier otro sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="14250-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="14250-114">Las API pueden comportarse de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="14250-114">APIs can behave differently.</span></span> <span data-ttu-id="14250-115">Por ejemplo, las API de reflexión tienen diferentes características de rendimiento cuando una aplicación utiliza una compilación anticipada en iOS o UWP.</span><span class="sxs-lookup"><span data-stu-id="14250-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="14250-116">El equipo de .NET [ofrece un analizador Roslyn](../analyzers/api-analyzer.md) para ayudar a detectar posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="14250-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="14250-117">✔️ EMPIECE por incluir un destino de `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="14250-117">✔️ DO start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="14250-118">La mayoría de bibliotecas de uso general no deberían necesitar API fuera de .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="14250-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="14250-119">Todas las plataformas modernas admiten .NET Standard 2.0 y es la manera recomendada para admitir varias plataformas con un destino.</span><span class="sxs-lookup"><span data-stu-id="14250-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="14250-120">❌ EVITE incluir un destino de `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="14250-120">❌ AVOID including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="14250-121">.NET Standard 1.x se distribuye como un conjunto pormenorizado de paquetes NuGet, que crea un gráfico de dependencias de paquete grande y da lugar a que los desarrolladores descarguen una gran cantidad de paquetes al compilar.</span><span class="sxs-lookup"><span data-stu-id="14250-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="14250-122">Las plataformas .NET modernas, incluidas .NET Framework 4.6.1, UWP y Xamarin, admiten .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="14250-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="14250-123">Solo debe utilizar .NET Standard 1.x como destino si necesita específicamente una plataforma anterior como destino.</span><span class="sxs-lookup"><span data-stu-id="14250-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="14250-124">✔️ INCLUYA un destino de `netstandard2.0` si necesita un destino de `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="14250-124">✔️ DO include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="14250-125">Todas las plataformas que admiten .NET Standard 2.0 usarán el destino `netstandard2.0` y se aprovecharán del hecho de tener un gráfico de paquetes más pequeño, mientras que las plataformas anteriores seguirán funcionando y pasarán a usar el destino `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="14250-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="14250-126">❌ NO incluya un destino de .NET Standard si la biblioteca se basa en un modelo de aplicación específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="14250-126">❌ DO NOT include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="14250-127">Por ejemplo, una biblioteca de Kit de herramientas de control UWP depende de un modelo de aplicación que solo está disponible en UWP.</span><span class="sxs-lookup"><span data-stu-id="14250-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="14250-128">Las API específicas del modelo de aplicación no estarán disponibles en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="14250-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="14250-129">Compatibilidad con múltiples versiones</span><span class="sxs-lookup"><span data-stu-id="14250-129">Multi-targeting</span></span>

<span data-ttu-id="14250-130">En ocasiones necesitará tener acceso a las API específicas del marco de las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="14250-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="14250-131">La mejor manera de llamar a las API específicas del marco es usar varios destinos, que crea el proyecto para muchos [marcos de destino de .NET](../frameworks.md) en lugar de solo para uno.</span><span class="sxs-lookup"><span data-stu-id="14250-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="14250-132">Para evitar que los consumidores tengan que crear para marcos individuales, debe procurar tener una salida de .NET Standard además de una o más salidas específicas del marco.</span><span class="sxs-lookup"><span data-stu-id="14250-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="14250-133">Con varias versiones, todos los ensamblados se empaquetan dentro de un único paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="14250-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="14250-134">Después, los consumidores pueden hacer referencia al mismo paquete y NuGet seleccionará la implementación apropiada.</span><span class="sxs-lookup"><span data-stu-id="14250-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="14250-135">La biblioteca de .NET Standard actúa como la biblioteca de reserva que se usa en todas partes, salvo en los casos donde el paquete NuGet ofrece una implementación específica del marco.</span><span class="sxs-lookup"><span data-stu-id="14250-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="14250-136">Varios destinos le permiten usar la compilación condicional en el código y llamar a las API específicas del marco.</span><span class="sxs-lookup"><span data-stu-id="14250-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="14250-137">![Paquete NuGet con varios ensamblados](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "Paquete NuGet con varios ensamblados")</span><span class="sxs-lookup"><span data-stu-id="14250-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="14250-138">✔️ ES RECOMENDABLE usar las implementaciones de .NET como destino además de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="14250-138">✔️ CONSIDER targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="14250-139">El uso de las implementaciones de .NET como destino le permite llamar a las API específicas de la plataforma que se encuentran fuera de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="14250-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="14250-140">No elimine la compatibilidad con .NET Standard al hacer esto.</span><span class="sxs-lookup"><span data-stu-id="14250-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="14250-141">En su lugar, empiece desde la implementación y ofrezca API de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="14250-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="14250-142">De este modo, la biblioteca se puede usar en cualquier lugar y admite la carga ligera de características en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="14250-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="14250-143">❌ EVITE varios destinos, así como usar .NET Standard como destino, si el código fuente es el mismo para todos los destinos.</span><span class="sxs-lookup"><span data-stu-id="14250-143">❌ AVOID multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="14250-144">NuGet usará automáticamente el ensamblado de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="14250-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="14250-145">El uso de las implementaciones de .NET individuales como destino aumenta el tamaño de `*.nupkg` sin obtener ventaja alguna.</span><span class="sxs-lookup"><span data-stu-id="14250-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="14250-146">✔️ ES RECOMENDABLE agregar un destino para `net461` cuando se ofrece un destino de `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="14250-146">✔️ CONSIDER adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="14250-147">El uso de .NET Standard 2.0 de .NET Framework tiene algunos problemas que se han solucionado en .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="14250-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="14250-148">Puede mejorar la experiencia para los desarrolladores que siguen usando .NET Framework 4.6.1 - 4.7.1 ofreciéndoles un archivo binario que se ha creado para .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="14250-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="14250-149">✔️ DEBE distribuir las bibliotecas mediante un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="14250-149">✔️ DO distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="14250-150">NuGet seleccionará el mejor destino para el desarrollador y evitará que tenga de tener que elegir la implementación apropiada.</span><span class="sxs-lookup"><span data-stu-id="14250-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="14250-151">✔️ USE una propiedad `TargetFrameworks` del archivo de proyecto cuando haya varios destinos.</span><span class="sxs-lookup"><span data-stu-id="14250-151">✔️ DO use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="14250-152">✔️ ES RECOMENDABLE usar [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) cuando haya varios destinos para UWP y Xamarin, ya que simplifica considerablemente el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="14250-152">✔️ CONSIDER using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="14250-153">Destinos antiguos</span><span class="sxs-lookup"><span data-stu-id="14250-153">Older targets</span></span>

<span data-ttu-id="14250-154">.NET admite las versiones de destino de .NET Framework que llevan mucho tiempo sin soporte técnico, así como las plataformas que ya no se suelen utilizar.</span><span class="sxs-lookup"><span data-stu-id="14250-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="14250-155">Si bien es valioso hacer que la biblioteca funcione en tantos destinos como sea posible, tener que trabajar con API ausentes puede agregar una sobrecarga significativa.</span><span class="sxs-lookup"><span data-stu-id="14250-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="14250-156">Creemos que ciertos marcos ya no valen la pena como destino, considerando su alcance y limitaciones.</span><span class="sxs-lookup"><span data-stu-id="14250-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="14250-157">❌ NO incluya un destino de Biblioteca de clases portátil (PCL).</span><span class="sxs-lookup"><span data-stu-id="14250-157">❌ DO NOT include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="14250-158">Por ejemplo, `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="14250-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="14250-159">.NET standard es la forma moderna de admitir las bibliotecas de .NET multiplataforma y reemplaza a las PCL.</span><span class="sxs-lookup"><span data-stu-id="14250-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="14250-160">❌ NO incluya destinos para las plataformas de .NET que ya no se admitan.</span><span class="sxs-lookup"><span data-stu-id="14250-160">❌ DO NOT include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="14250-161">Por ejemplo: `SL4`, `WP`.</span><span class="sxs-lookup"><span data-stu-id="14250-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="14250-162">[Anterior](get-started.md)
>[Siguiente](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="14250-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
