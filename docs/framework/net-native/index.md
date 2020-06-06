---
title: Compilar aplicaciones con .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
ms.openlocfilehash: 1f176e81905fe68c6d740a13240fe814659a7a59
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128372"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="be7f4-102">Compilar aplicaciones con .NET Native</span><span class="sxs-lookup"><span data-stu-id="be7f4-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="be7f4-103">.NET Native es una tecnología de precompilación para compilar e implementar aplicaciones de Windows que se incluyen con Visual Studio 2015 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="be7f4-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="be7f4-104">Su función es compilar automáticamente, a código nativo, aquellas versiones de lanzamiento de las aplicaciones escritas en código administrado (C# o Visual Basic) y que tienen como destino .NET Framework y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="be7f4-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="be7f4-105">Normalmente, las aplicaciones que tienen como destino .NET Framework se compilan en lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="be7f4-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="be7f4-106">En tiempo de ejecución, el compilador Just-In-Time (JIT) convierte el IL en código nativo.</span><span class="sxs-lookup"><span data-stu-id="be7f4-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="be7f4-107">En cambio, .NET Native compila aplicaciones de Windows directamente en código nativo.</span><span class="sxs-lookup"><span data-stu-id="be7f4-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="be7f4-108">Para los desarrolladores, esto significa:</span><span class="sxs-lookup"><span data-stu-id="be7f4-108">For developers, this means:</span></span>

- <span data-ttu-id="be7f4-109">Las aplicaciones incluyen el rendimiento del código nativo.</span><span class="sxs-lookup"><span data-stu-id="be7f4-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="be7f4-110">Normalmente, el rendimiento será superior al código que se compila primero en IL y que, a continuación, se compila en código nativo mediante el compilador JIT.</span><span class="sxs-lookup"><span data-stu-id="be7f4-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="be7f4-111">Puede seguir programando en C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="be7f4-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="be7f4-112">Puede continuar beneficiándose de los recursos proporcionados por .NET Framework, incluida su biblioteca de clases, la administración automática de memoria, la recolección de elementos no utilizados y el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="be7f4-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="be7f4-113">En el caso de los usuarios de las aplicaciones, .NET Native ofrece estas ventajas:</span><span class="sxs-lookup"><span data-stu-id="be7f4-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="be7f4-114">Tiempos de ejecución más rápidos para la mayoría de las aplicaciones y los escenarios.</span><span class="sxs-lookup"><span data-stu-id="be7f4-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="be7f4-115">Tiempos de inicio más rápidos para la mayoría de las aplicaciones y los escenarios.</span><span class="sxs-lookup"><span data-stu-id="be7f4-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="be7f4-116">Pocos costos de implementación y actualización.</span><span class="sxs-lookup"><span data-stu-id="be7f4-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="be7f4-117">Uso optimizado de la memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be7f4-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be7f4-118">En la gran mayoría de las aplicaciones y los escenarios, .NET Native ofrece tiempos de inicio significativamente más rápidos y un rendimiento superior en comparación con una aplicación compilada en IL o en una imagen de NGEN.</span><span class="sxs-lookup"><span data-stu-id="be7f4-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="be7f4-119">Sin embargo, los resultados pueden variar.</span><span class="sxs-lookup"><span data-stu-id="be7f4-119">However, your results may vary.</span></span> <span data-ttu-id="be7f4-120">Para asegurarse de que la aplicación se ha beneficiado de las mejoras de rendimiento de .NET Native, debe comparar su rendimiento con el de la versión nativa de non-.NET de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be7f4-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="be7f4-121">Para obtener más información, vea [información general sobre la sesión de rendimiento](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="be7f4-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="be7f4-122">Pero .NET Native implica más que una compilación en código nativo.</span><span class="sxs-lookup"><span data-stu-id="be7f4-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="be7f4-123">Transforma la manera en que se compilan y ejecutan las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be7f4-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="be7f4-124">En concreto:</span><span class="sxs-lookup"><span data-stu-id="be7f4-124">In particular:</span></span>

- <span data-ttu-id="be7f4-125">Durante la precompilación, las partes necesarias de .NET Framework se vinculan estáticamente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be7f4-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="be7f4-126">Esto permite que la aplicación se ejecute con bibliotecas locales de aplicación de .NET Framework y que el compilador realice un análisis global para ofrecer un gran rendimiento.</span><span class="sxs-lookup"><span data-stu-id="be7f4-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="be7f4-127">Como resultado, las aplicaciones se inician sistemáticamente más rápido después de las actualizaciones de.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be7f4-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="be7f4-128">El tiempo de ejecución de .NET Native está optimizado para la precompilación estática y, en la mayoría de los casos, ofrece un rendimiento superior.</span><span class="sxs-lookup"><span data-stu-id="be7f4-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="be7f4-129">Al mismo tiempo, conserva las características de reflexión principales que los desarrolladores encuentran tan productivas.</span><span class="sxs-lookup"><span data-stu-id="be7f4-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="be7f4-130">.NET Native usa el mismo back-end que el compilador de C++, que está optimizado para escenarios de precompilación estáticos.</span><span class="sxs-lookup"><span data-stu-id="be7f4-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="be7f4-131">.NET Native es capaz de aportar las ventajas de rendimiento de C++ a los desarrolladores de código administrado, ya que utiliza las mismas herramientas o similares que C++ de forma subyacente, tal como se muestra en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="be7f4-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="be7f4-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="be7f4-132">.NET Native</span></span>|<span data-ttu-id="be7f4-133">C++</span><span class="sxs-lookup"><span data-stu-id="be7f4-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="be7f4-134">Bibliotecas</span><span class="sxs-lookup"><span data-stu-id="be7f4-134">Libraries</span></span>|<span data-ttu-id="be7f4-135">.NET Framework + Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="be7f4-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="be7f4-136">Win32 + Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="be7f4-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="be7f4-137">Compilador</span><span class="sxs-lookup"><span data-stu-id="be7f4-137">Compiler</span></span>|<span data-ttu-id="be7f4-138">Compilador de optimización de UTC</span><span class="sxs-lookup"><span data-stu-id="be7f4-138">UTC optimizing compiler</span></span>|<span data-ttu-id="be7f4-139">Compilador de optimización de UTC</span><span class="sxs-lookup"><span data-stu-id="be7f4-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="be7f4-140">Implementado</span><span class="sxs-lookup"><span data-stu-id="be7f4-140">Deployed</span></span>|<span data-ttu-id="be7f4-141">Archivos binarios listos para ejecutarse</span><span class="sxs-lookup"><span data-stu-id="be7f4-141">Ready-to-run binaries</span></span>|<span data-ttu-id="be7f4-142">Archivos binarios listos para ejecutarse (ASM)</span><span class="sxs-lookup"><span data-stu-id="be7f4-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="be7f4-143">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="be7f4-143">Runtime</span></span>|<span data-ttu-id="be7f4-144">MRT.dll (tiempo de ejecución de CLR mínimo)</span><span class="sxs-lookup"><span data-stu-id="be7f4-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="be7f4-145">CRT.dll (tiempo de ejecución de C)</span><span class="sxs-lookup"><span data-stu-id="be7f4-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="be7f4-146">Para aplicaciones de Windows 10, cargue los archivos binarios de compilación de código con .NET Native en paquetes de aplicación (archivos .appx) en la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="be7f4-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="be7f4-147">En esta sección</span><span class="sxs-lookup"><span data-stu-id="be7f4-147">In This Section</span></span>

<span data-ttu-id="be7f4-148">Para obtener más información sobre el desarrollo de aplicaciones con la compilación de código con .NET Native, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="be7f4-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="be7f4-149">Introducción a la compilación de código con .NET Native: tutorial de experiencia del programador</span><span class="sxs-lookup"><span data-stu-id="be7f4-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="be7f4-150">[.NET Native y compilación:](net-native-and-compilation.md) cómo compila .NET Native el proyecto de código nativo.</span><span class="sxs-lookup"><span data-stu-id="be7f4-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="be7f4-151">Reflexión y .NET Native</span><span class="sxs-lookup"><span data-stu-id="be7f4-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="be7f4-152">API basada en la reflexión</span><span class="sxs-lookup"><span data-stu-id="be7f4-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="be7f4-153">Referencia de la API de reflexión</span><span class="sxs-lookup"><span data-stu-id="be7f4-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="be7f4-154">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="be7f4-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="be7f4-155">Serialización y metadatos</span><span class="sxs-lookup"><span data-stu-id="be7f4-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="be7f4-156">Migrar la aplicación de la Tienda Windows a .NET Native</span><span class="sxs-lookup"><span data-stu-id="be7f4-156">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="be7f4-157">Solución de problemas generales de .NET Native</span><span class="sxs-lookup"><span data-stu-id="be7f4-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
