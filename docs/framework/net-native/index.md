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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052640"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="9ac2e-102">Compilar aplicaciones con .NET Native</span><span class="sxs-lookup"><span data-stu-id="9ac2e-102">Compiling Apps with .NET Native</span></span>
<span data-ttu-id="9ac2e-103">.NET native es una tecnología de precompilación para compilar e implementar aplicaciones de Windows que se incluye con Visual Studio 2015 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="9ac2e-104">Su función es compilar automáticamente, a código nativo, aquellas versiones de lanzamiento de las aplicaciones escritas en código administrado (C# o Visual Basic) y que tienen como destino .NET Framework y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="9ac2e-105">Normalmente, las aplicaciones que tienen como destino .NET Framework se compilan en lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="9ac2e-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="9ac2e-106">En tiempo de ejecución, el compilador Just-In-Time (JIT) convierte el IL en código nativo.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="9ac2e-107">En cambio, .NET Native compila aplicaciones de Windows directamente en código nativo.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="9ac2e-108">Para los desarrolladores, esto significa:</span><span class="sxs-lookup"><span data-stu-id="9ac2e-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="9ac2e-109">Las aplicaciones cuentan con el rendimiento del código nativo.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="9ac2e-110">Normalmente, el rendimiento será mejor para el código que primero se compilan en IL y, a continuación, se compilan en código nativo por el compilador JIT.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="9ac2e-111">Puede seguir programando en C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="9ac2e-112">Puede continuar beneficiándose de los recursos proporcionados por .NET Framework, incluida su biblioteca de clases, la administración automática de memoria, la recolección de elementos no utilizados y el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="9ac2e-113">Para los usuarios de las aplicaciones, .NET Native ofrece las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="9ac2e-113">For users of your apps, .NET Native offers these advantages:</span></span>  
  
- <span data-ttu-id="9ac2e-114">Tiempos de ejecución más rápidos para la mayoría de las aplicaciones y escenarios.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="9ac2e-115">Tiempos de inicio más rápidos para la mayoría de las aplicaciones y escenarios.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="9ac2e-116">Bajos costes de implementación y actualización.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="9ac2e-117">Uso de memoria de la aplicación optimizada.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9ac2e-118">Para la mayoría de las aplicaciones y escenarios de .NET Native ofrece tiempos de arranque considerablemente más rápidos y un rendimiento superior en comparación con una aplicación que se compilan en IL o en una imagen NGEN.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="9ac2e-119">Sin embargo, los resultados pueden variar.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-119">However, your results may vary.</span></span> <span data-ttu-id="9ac2e-120">Para asegurarse de que la aplicación se ha beneficiado de las mejoras de rendimiento de .NET Native, se debe comparar su rendimiento con el de la versión de la aplicación no - .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="9ac2e-121">Para obtener más información, consulte [información general sobre la sesión de rendimiento](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="9ac2e-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="9ac2e-122">Pero .NET Native implica más que una compilación en código nativo.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="9ac2e-123">Transforma la manera en que se compilan y ejecutan las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="9ac2e-124">En concreto:</span><span class="sxs-lookup"><span data-stu-id="9ac2e-124">In particular:</span></span>  
  
- <span data-ttu-id="9ac2e-125">Durante la precompilación, las partes necesarias de .NET Framework se vinculan estáticamente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="9ac2e-126">Esto permite que la aplicación se ejecute con bibliotecas locales de aplicación de .NET Framework y que el compilador realice un análisis global para ofrecer un gran rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="9ac2e-127">Como resultado, las aplicaciones se inician sistemáticamente más rápido después de las actualizaciones de.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="9ac2e-128">El tiempo de ejecución .NET Native está optimizado para la precompilación estática y en la mayoría de los casos, ofrece un rendimiento superior.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="9ac2e-129">Al mismo tiempo, conserva las características de reflexión principales que los desarrolladores encuentran tan productivas.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- <span data-ttu-id="9ac2e-130">.NET native usa el mismo back-end como el C++ compilador, que está optimizado para escenarios de precompilación estáticos.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="9ac2e-131">.NET native es capaz de ofrecer las ventajas de rendimiento C++ administrado a los desarrolladores de código porque usa las mismas o parecidas herramientas como C++ bajo el capó, como se muestra en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||<span data-ttu-id="9ac2e-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="9ac2e-132">.NET Native</span></span>|<span data-ttu-id="9ac2e-133">C++</span><span class="sxs-lookup"><span data-stu-id="9ac2e-133">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="9ac2e-134">Bibliotecas</span><span class="sxs-lookup"><span data-stu-id="9ac2e-134">Libraries</span></span>|<span data-ttu-id="9ac2e-135">.NET Framework + Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9ac2e-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="9ac2e-136">Win32 + Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9ac2e-136">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="9ac2e-137">Compilador</span><span class="sxs-lookup"><span data-stu-id="9ac2e-137">Compiler</span></span>|<span data-ttu-id="9ac2e-138">Compilador de optimización de UTC</span><span class="sxs-lookup"><span data-stu-id="9ac2e-138">UTC optimizing compiler</span></span>|<span data-ttu-id="9ac2e-139">Compilador de optimización de UTC</span><span class="sxs-lookup"><span data-stu-id="9ac2e-139">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="9ac2e-140">Implementado</span><span class="sxs-lookup"><span data-stu-id="9ac2e-140">Deployed</span></span>|<span data-ttu-id="9ac2e-141">Archivos binarios listos para ejecutarse</span><span class="sxs-lookup"><span data-stu-id="9ac2e-141">Ready-to-run binaries</span></span>|<span data-ttu-id="9ac2e-142">Archivos binarios listos para ejecutarse (ASM)</span><span class="sxs-lookup"><span data-stu-id="9ac2e-142">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="9ac2e-143">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9ac2e-143">Runtime</span></span>|<span data-ttu-id="9ac2e-144">MRT.dll (tiempo de ejecución de CLR mínimo)</span><span class="sxs-lookup"><span data-stu-id="9ac2e-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="9ac2e-145">CRT.dll (tiempo de ejecución de C)</span><span class="sxs-lookup"><span data-stu-id="9ac2e-145">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="9ac2e-146">Para aplicaciones de Windows 10, cargue los archivos binarios de compilación de código con .NET Native en paquetes de aplicación (archivos .appx) en la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ac2e-147">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9ac2e-147">In This Section</span></span>  
 <span data-ttu-id="9ac2e-148">Para obtener más información sobre el desarrollo de aplicaciones con la compilación de código con .NET Native, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="9ac2e-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="9ac2e-149">Introducción a la compilación de código nativa. NET: Tutorial de experiencia del desarrollador</span><span class="sxs-lookup"><span data-stu-id="9ac2e-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="9ac2e-150">[.NET native y compilación:](../../../docs/framework/net-native/net-native-and-compilation.md) Cómo compila .NET Native el proyecto de código nativo.</span><span class="sxs-lookup"><span data-stu-id="9ac2e-150">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- <span data-ttu-id="9ac2e-151">[Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) (Reflexión y .NET Native)</span><span class="sxs-lookup"><span data-stu-id="9ac2e-151">[Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)</span></span>  
  
    - <span data-ttu-id="9ac2e-152">[APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md) (API basadas en Reflection)</span><span class="sxs-lookup"><span data-stu-id="9ac2e-152">[APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)</span></span>  
  
    - [<span data-ttu-id="9ac2e-153">Referencia de la API de reflexión</span><span class="sxs-lookup"><span data-stu-id="9ac2e-153">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="9ac2e-154">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="9ac2e-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="9ac2e-155">Serialización y metadatos</span><span class="sxs-lookup"><span data-stu-id="9ac2e-155">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="9ac2e-156">Migrar la aplicación de la Tienda Windows a .NET Native</span><span class="sxs-lookup"><span data-stu-id="9ac2e-156">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="9ac2e-157">Solución de problemas generales de .NET Native</span><span class="sxs-lookup"><span data-stu-id="9ac2e-157">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
