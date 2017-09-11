---
title: Glosario de .NET
description: "Descubra el significado de algunos de los términos usados en la documentación de .NET."
keywords: "Glosario de .NET, diccionario de .NET, terminología de .NET, plataforma .NET, .NET Framework, entorno de ejecución .NET"
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: 33b22ab80f9b4d42975f2c41c880543c615a3e01
ms.openlocfilehash: c66f1b2b85d377c84712c0ad73682cdeeb7249fd
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2017

---

# <a name="net-glossary"></a><span data-ttu-id="a90ed-104">Glosario de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-104">.NET Glossary</span></span>

<span data-ttu-id="a90ed-105">El objetivo principal de este glosario es aclarar los significados de algunos de los términos y acrónimos que aparecen frecuentemente en la documentación de .NET sin definiciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="a90ed-106">AOT</span><span class="sxs-lookup"><span data-stu-id="a90ed-106">AOT</span></span>

<span data-ttu-id="a90ed-107">Compilador Ahead Of Time.</span><span class="sxs-lookup"><span data-stu-id="a90ed-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="a90ed-108">Similar a [JIT](#jit), este compilador también convierte [IL](#il) en código de máquina.</span><span class="sxs-lookup"><span data-stu-id="a90ed-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="a90ed-109">A diferencia de la compilación JIT, la compilación AOT ocurre antes de que la aplicación se ejecute y, normalmente, se realiza en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="a90ed-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="a90ed-110">Dado que las cadenas de la herramienta de AOT no se compilan en tiempo de ejecución, no tienen que minimizar el tiempo dedicado a compilar.</span><span class="sxs-lookup"><span data-stu-id="a90ed-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="a90ed-111">Esto significa que pueden dedicar más tiempo a la optimización.</span><span class="sxs-lookup"><span data-stu-id="a90ed-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="a90ed-112">Puesto que el contexto de AOT es toda la aplicación, el compilador AOT también realiza vinculación entre módulos y el análisis de todo el programa, lo que significa que se siguen todas las referencias y se genera un archivo ejecutable único.</span><span class="sxs-lookup"><span data-stu-id="a90ed-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="a90ed-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-113">ASP.NET</span></span> 

<span data-ttu-id="a90ed-114">La implementación original de ASP.NET que se distribuye con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a90ed-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="a90ed-115">A veces, ASP.NET es un término genérico que hace referencia a ambas implementaciones de ASP.NET, incluido ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="a90ed-116">El significado que lleva el término en una instancia específica se determina según el contexto.</span><span class="sxs-lookup"><span data-stu-id="a90ed-116">The meaning that the term carries in any given instance is determined by context.</span></span> 

<span data-ttu-id="a90ed-117">Vea [ASP.NET](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="a90ed-117">See [ASP.NET](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="a90ed-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a90ed-118">ASP.NET Core</span></span>

<span data-ttu-id="a90ed-119">Una implementación multiplataforma, de alto rendimiento y de código abierto de ASP.NET compilada en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="a90ed-120">Vea [ASP.NET Core](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="a90ed-120">See [ASP.NET Core](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="a90ed-121">ensamblado</span><span class="sxs-lookup"><span data-stu-id="a90ed-121">assembly</span></span>

<span data-ttu-id="a90ed-122">Un archivo *.dll* que contiene una colección de API que pueden llamarse mediante aplicaciones u otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a90ed-122">A *.dll* file that contains a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="a90ed-123">Un ensamblado de .NET es una colección de tipos.</span><span class="sxs-lookup"><span data-stu-id="a90ed-123">A .NET assembly is a collection of types.</span></span> <span data-ttu-id="a90ed-124">Un ensamblado incluye interfaces, clases, estructuras, enumeraciones y delegados.</span><span class="sxs-lookup"><span data-stu-id="a90ed-124">An assembly includes interfaces, classes, structures, enumerations, and delegates.</span></span>  <span data-ttu-id="a90ed-125">A veces, se hace referencia a los ensamblados de la carpeta *bin* de un proyecto como *archivos binarios*.</span><span class="sxs-lookup"><span data-stu-id="a90ed-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="a90ed-126">Vea también [biblioteca](#library).</span><span class="sxs-lookup"><span data-stu-id="a90ed-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="a90ed-127">CLR</span><span class="sxs-lookup"><span data-stu-id="a90ed-127">CLR</span></span>

<span data-ttu-id="a90ed-128">Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a90ed-128">Common Language Runtime.</span></span>

<span data-ttu-id="a90ed-129">El significado exacto depende del contexto, pero normalmente hace referencia al entorno de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a90ed-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="a90ed-130">CLR controla la asignación y administración de memoria.</span><span class="sxs-lookup"><span data-stu-id="a90ed-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="a90ed-131">CLR es también una máquina virtual que no solo ejecuta aplicaciones, sino que también genera y compila código sobre la marcha mediante un compilador JIT.</span><span class="sxs-lookup"><span data-stu-id="a90ed-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="a90ed-132">La implementación actual de Microsoft CLR es solo Windows.</span><span class="sxs-lookup"><span data-stu-id="a90ed-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="a90ed-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="a90ed-133">CoreCLR</span></span>

<span data-ttu-id="a90ed-134">.NET Core Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a90ed-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="a90ed-135">Este CLR se crea a partir del mismo código base que el CLR.</span><span class="sxs-lookup"><span data-stu-id="a90ed-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="a90ed-136">Originalmente, CoreCLR era el entorno de ejecución de Silverlight y estaba diseñado para ejecutarse en varias plataformas, concretamente Windows OS X. Ahora, CoreCLR forma parte de .NET Core y representa una versión simplificada de CLR.</span><span class="sxs-lookup"><span data-stu-id="a90ed-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="a90ed-137">Sigue siendo un entorno de ejecución multiplataforma y ahora incluye compatibilidad con muchas distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="a90ed-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="a90ed-138">CoreCLR es también una máquina virtual con funciones de ejecución de código y JIT.</span><span class="sxs-lookup"><span data-stu-id="a90ed-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="a90ed-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="a90ed-139">CoreFX</span></span>

<span data-ttu-id="a90ed-140">Biblioteca de clases base (BCL) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a90ed-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="a90ed-141">Un conjunto de bibliotecas que conforman los espacios de nombres de System.* (y hasta cierto punto Microsoft.*).</span><span class="sxs-lookup"><span data-stu-id="a90ed-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="a90ed-142">BCL es un marco de nivel inferior de uso general donde se compilan marcos de trabajo de la aplicación de nivel superior, como ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="a90ed-143">El código fuente de la BCL de .NET Core se encuentra en el [repositorio CoreFX](https://github.com/dotnet/corefx).</span><span class="sxs-lookup"><span data-stu-id="a90ed-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="a90ed-144">En cambio, la mayoría de las API de .NET Core también están disponibles en .NET Framework, por lo que puede considerar CoreFX como una bifurcación de la BCL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a90ed-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="a90ed-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="a90ed-145">CoreRT</span></span>

<span data-ttu-id="a90ed-146">Entorno de ejecución .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-146">.NET Core runtime.</span></span>

<span data-ttu-id="a90ed-147">A diferencia de CLR o CoreCLR, CoreRT no es una máquina virtual, lo que significa que no incluye las funciones para generar y ejecutar código sobre la marcha porque no incluye un [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="a90ed-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="a90ed-148">En cambio, incluye [GC](#gc), reflexión y capacidad de identificación del tipo en tiempo de ejecución (RTTI).</span><span class="sxs-lookup"><span data-stu-id="a90ed-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="a90ed-149">Con todo, su sistema de tipos está diseñado para que no sean necesarios los metadatos para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="a90ed-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="a90ed-150">Esto permite tener una cadena de herramientas de [AOT](#aot) que puede vincular metadatos superfluos y (más importante) identificar código que no usa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="a90ed-151">CoreRT está en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a90ed-151">CoreRT is in development.</span></span>

<span data-ttu-id="a90ed-152">Vea [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introducción a .NET Native y CoreRT).</span><span class="sxs-lookup"><span data-stu-id="a90ed-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="a90ed-153">ecosistema</span><span class="sxs-lookup"><span data-stu-id="a90ed-153">ecosystem</span></span>

<span data-ttu-id="a90ed-154">Todo el software en tiempo de ejecución, las herramientas de desarrollo y los recursos de la comunidad que se usan para compilar y ejecutar aplicaciones de una tecnología determinada.</span><span class="sxs-lookup"><span data-stu-id="a90ed-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="a90ed-155">El término "ecosistema de .NET" se diferencia de términos parecidos como "pila de .NET" en que incluye bibliotecas y aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="a90ed-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="a90ed-156">Aquí se muestra un ejemplo en una frase:</span><span class="sxs-lookup"><span data-stu-id="a90ed-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="a90ed-157">"La finalidad de [.NET Standard](#net-standard) es establecer una mayor uniformidad en el ecosistema de .NET".</span><span class="sxs-lookup"><span data-stu-id="a90ed-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="a90ed-158">marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="a90ed-158">framework</span></span>

<span data-ttu-id="a90ed-159">En general, una colección completa de API que facilita el desarrollo y la implementación de aplicaciones que se basan en una tecnología concreta.</span><span class="sxs-lookup"><span data-stu-id="a90ed-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="a90ed-160">En este sentido general, ASP.NET Core y Windows Forms son ejemplos de marcos de trabajo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="a90ed-161">Vea también [biblioteca](#library).</span><span class="sxs-lookup"><span data-stu-id="a90ed-161">See also [library](#library).</span></span>

<span data-ttu-id="a90ed-162">Los siguientes términos tienen un significado técnico más específico:</span><span class="sxs-lookup"><span data-stu-id="a90ed-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="a90ed-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a90ed-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="a90ed-164">Plataforma de destino</span><span class="sxs-lookup"><span data-stu-id="a90ed-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="a90ed-165">TFM (moniker de la plataforma de destino)</span><span class="sxs-lookup"><span data-stu-id="a90ed-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="a90ed-166">En la documentación existente, "marco de trabajo" a veces hace referencia a una [implementación de .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="a90ed-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="a90ed-167">Por ejemplo, un artículo puede llamar marco de trabajo a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="a90ed-168">Tenemos previsto eliminar de la documentación este uso confuso.</span><span class="sxs-lookup"><span data-stu-id="a90ed-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="a90ed-169">GC</span><span class="sxs-lookup"><span data-stu-id="a90ed-169">GC</span></span>

<span data-ttu-id="a90ed-170">Recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a90ed-170">Garbage collector.</span></span>

<span data-ttu-id="a90ed-171">El recolector de elementos no utilizados es una implementación de administración de memoria automática.</span><span class="sxs-lookup"><span data-stu-id="a90ed-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="a90ed-172">GC libera la memoria ocupada por objetos que ya no se usan.</span><span class="sxs-lookup"><span data-stu-id="a90ed-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="a90ed-173">Vea [Garbage Collection](garbage-collection/index.md) (Recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="a90ed-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="a90ed-174">IL</span><span class="sxs-lookup"><span data-stu-id="a90ed-174">IL</span></span>

<span data-ttu-id="a90ed-175">Lenguaje intermedio.</span><span class="sxs-lookup"><span data-stu-id="a90ed-175">Intermediate language.</span></span>

<span data-ttu-id="a90ed-176">Los lenguajes .NET de nivel alto, como C#, compilan en un conjunto de instrucciones independiente del hardware, lo que se denomina lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="a90ed-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="a90ed-177">A veces, se hace referencia al IL como MSIL (IL de Microsoft) o CIL (Common IL).</span><span class="sxs-lookup"><span data-stu-id="a90ed-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="a90ed-178">JIT</span><span class="sxs-lookup"><span data-stu-id="a90ed-178">JIT</span></span>

<span data-ttu-id="a90ed-179">Compilador Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="a90ed-179">Just-in-time compiler.</span></span>

<span data-ttu-id="a90ed-180">Similar a [AOT](#aot), este compilador convierte el [IL](#il) en código de máquina que entienda el procesador.</span><span class="sxs-lookup"><span data-stu-id="a90ed-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="a90ed-181">A diferencia de AOT, la compilación JIT se produce a petición y se lleva a cabo en el mismo equipo en que debe ejecutarse el código.</span><span class="sxs-lookup"><span data-stu-id="a90ed-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="a90ed-182">Puesto que la compilación JIT tiene lugar durante la ejecución de la aplicación, el tiempo de compilación es parte del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a90ed-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="a90ed-183">Por tanto, los compiladores JIT tienen que compensar el tiempo invertido en optimizar el código con el ahorro que puede generar el código resultante.</span><span class="sxs-lookup"><span data-stu-id="a90ed-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="a90ed-184">Pero un JIT conoce el hardware real y puede liberar a los desarrolladores de tener que enviar diferentes implementaciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="a90ed-185">implementación de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-185">implementation of .NET</span></span>

<span data-ttu-id="a90ed-186">Una implementación de .NET incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a90ed-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="a90ed-187">Uno o varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a90ed-187">One or more runtimes.</span></span> <span data-ttu-id="a90ed-188">Ejemplos: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="a90ed-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="a90ed-189">Una biblioteca de clases que implementa una versión de .NET Standard y puede incluir API adicionales.</span><span class="sxs-lookup"><span data-stu-id="a90ed-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="a90ed-190">Ejemplos: biblioteca de clases base de .NET Framework, biblioteca de clases base de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="a90ed-191">Opcionalmente, uno o varios marcos de trabajo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="a90ed-192">Ejemplos: ASP.NET, Windows Forms y WPF se incluyen en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a90ed-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="a90ed-193">Opcionalmente, herramientas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a90ed-193">Optionally, development tools.</span></span> <span data-ttu-id="a90ed-194">Algunas herramientas de desarrollo se comparten entre varias implementaciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="a90ed-195">Ejemplos de implementaciones de .NET:</span><span class="sxs-lookup"><span data-stu-id="a90ed-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="a90ed-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a90ed-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="a90ed-197">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="a90ed-198">Plataforma universal de Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="a90ed-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="a90ed-199">biblioteca</span><span class="sxs-lookup"><span data-stu-id="a90ed-199">library</span></span>

<span data-ttu-id="a90ed-200">Una colección de API que pueden llamarse mediante aplicaciones u otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a90ed-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="a90ed-201">Una biblioteca de .NET se compone de uno o varios [ensamblados](#assembly).</span><span class="sxs-lookup"><span data-stu-id="a90ed-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="a90ed-202">Las palabras biblioteca y [marco de trabajo](#framework) se usan a menudo como sinónimos.</span><span class="sxs-lookup"><span data-stu-id="a90ed-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="a90ed-203">metapaquete</span><span class="sxs-lookup"><span data-stu-id="a90ed-203">metapackage</span></span>

<span data-ttu-id="a90ed-204">Un paquete de NuGet que no tiene ninguna biblioteca propia pero es solo una lista de dependencias.</span><span class="sxs-lookup"><span data-stu-id="a90ed-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="a90ed-205">Los paquetes incluidos pueden establecer opcionalmente la API de una plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="a90ed-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="a90ed-206">Vea [Paquetes, metapaquetes y marcos de trabajo](../core/packages.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="a90ed-207">Mono</span><span class="sxs-lookup"><span data-stu-id="a90ed-207">Mono</span></span>

<span data-ttu-id="a90ed-208">Mono es una implementación de .NET que se usa principalmente cuando se requiere un entorno de ejecución pequeño.</span><span class="sxs-lookup"><span data-stu-id="a90ed-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="a90ed-209">Es el entorno de ejecución que activa las aplicaciones de Xamarin en Android, Mac, iOS, tvOS y watchOS, y se centra principalmente en aplicaciones que requieren una superficie pequeña.</span><span class="sxs-lookup"><span data-stu-id="a90ed-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="a90ed-210">Admite todas las versiones de .NET Standard publicadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="a90ed-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="a90ed-211">Históricamente, Mono implementaba la API de .NET Framework más grande y emulaba algunas de las funciones más populares en Unix.</span><span class="sxs-lookup"><span data-stu-id="a90ed-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="a90ed-212">A veces, se usa para ejecutar aplicaciones de .NET que se basan en estas capacidades en Unix.</span><span class="sxs-lookup"><span data-stu-id="a90ed-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="a90ed-213">Mono se suele usar con un compilador Just-In-Time, pero también incluye un compilador estático completo (compilación Ahead Of Time) que se usa en plataformas como iOS.</span><span class="sxs-lookup"><span data-stu-id="a90ed-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="a90ed-214">Para más información sobre Mono, consulte la [documentación de Mono](http://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="a90ed-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="a90ed-215">.NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-215">.NET</span></span>

<span data-ttu-id="a90ed-216">El término que engloba [.NET Standard](#net-standard) y todas las cargas de trabajo e [implementaciones de .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="a90ed-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="a90ed-217">Siempre en mayúsculas, nunca ".Net".</span><span class="sxs-lookup"><span data-stu-id="a90ed-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="a90ed-218">Consulte la [Guía de la plataforma .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="a90ed-219">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-219">.NET Core</span></span> 

<span data-ttu-id="a90ed-220">Una implementación multiplataforma, de alto rendimiento y de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="a90ed-221">Incluye Core Common Language Runtime (CoreCLR), el entorno de ejecución AOT de Core (CoreRT, en desarrollo), la biblioteca de clases base de Core y el SDK de Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="a90ed-222">Vea [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="a90ed-223">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a90ed-223">.NET Core CLI</span></span>

<span data-ttu-id="a90ed-224">Una cadena de herramientas multiplataforma para desarrollar aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="a90ed-225">Vea [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="a90ed-226">SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a90ed-226">.NET Core SDK</span></span>

<span data-ttu-id="a90ed-227">Un conjunto de bibliotecas y herramientas que permiten a los desarrolladores crear aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a90ed-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="a90ed-228">Incluye la [CLI de .NET Core](#net-core-cli) para compilar aplicaciones, el entorno de ejecución y las bibliotecas de .NET Core para compilar y ejecutar aplicaciones, y el ejecutable dotnet (*dotnet.exe*) que ejecuta comandos de la CLI y ejecuta aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="a90ed-229">Vea [Información general sobre el SDK de .NET Core](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="a90ed-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a90ed-230">.NET Framework</span></span>

<span data-ttu-id="a90ed-231">Una implementación de .NET que se ejecuta solo en Windows.</span><span class="sxs-lookup"><span data-stu-id="a90ed-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="a90ed-232">Incluye Common Language Runtime (CLR), la biblioteca de clases base y las bibliotecas de marco de trabajo de la aplicación, como ASP.NET, Windows Forms y WPF.</span><span class="sxs-lookup"><span data-stu-id="a90ed-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="a90ed-233">Vea [Guía de .NET Framework](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="a90ed-234">.NET Native</span><span class="sxs-lookup"><span data-stu-id="a90ed-234">.NET Native</span></span>

<span data-ttu-id="a90ed-235">Una cadena de herramientas del compilador que genera código nativo Ahead Of Time (AOT), en lugar de Just-In-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a90ed-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="a90ed-236">La compilación se produce en el equipo del desarrollador, de forma similar a cómo funcionan el compilador y el enlazador de C++.</span><span class="sxs-lookup"><span data-stu-id="a90ed-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="a90ed-237">Quita el código que no se usa y emplea más tiempo en optimizarlo.</span><span class="sxs-lookup"><span data-stu-id="a90ed-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="a90ed-238">Extrae código de bibliotecas y lo combina en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="a90ed-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="a90ed-239">El resultado es un módulo único que representa toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="a90ed-240">UWP fue el primer marco de trabajo de la aplicación compatible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a90ed-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="a90ed-241">Ahora, se admite la compilación de aplicaciones de consola nativas para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="a90ed-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="a90ed-242">Vea [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introducción a .NET Native y CoreRT).</span><span class="sxs-lookup"><span data-stu-id="a90ed-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="a90ed-243">Estándar .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-243">.NET Standard</span></span>

<span data-ttu-id="a90ed-244">Una especificación formal de las API de .NET que están disponibles en cada implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="a90ed-245">La especificación de .NET Standard a veces se denomina "biblioteca" en la documentación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="a90ed-246">Dado que una biblioteca incluye implementaciones de API, no solo especificaciones (interfaces), es confuso denominar "biblioteca" a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a90ed-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="a90ed-247">Tenemos previsto eliminar este uso de la documentación, excepto en relación con el nombre del metapaquete de .NET Standard (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="a90ed-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="a90ed-248">Vea [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="a90ed-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="a90ed-249">NGEN</span></span>

<span data-ttu-id="a90ed-250">Generación (de imágenes) nativas.</span><span class="sxs-lookup"><span data-stu-id="a90ed-250">Native (image) generation.</span></span>

<span data-ttu-id="a90ed-251">Esta tecnología se puede considerar como un compilador JIT persistente.</span><span class="sxs-lookup"><span data-stu-id="a90ed-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="a90ed-252">Normalmente, compila código en el equipo en que se ejecuta el código, pero la compilación se suele producir durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="a90ed-253">paquete</span><span class="sxs-lookup"><span data-stu-id="a90ed-253">package</span></span>

<span data-ttu-id="a90ed-254">Un paquete de NuGet &mdash; o simplemente un paquete &mdash; es un archivo *.zip* con uno o varios ensamblados del mismo nombre junto con metadatos adicionales, como el nombre del autor.</span><span class="sxs-lookup"><span data-stu-id="a90ed-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="a90ed-255">El archivo *.zip* tiene una extensión *.nupkg* y puede contener recursos (como archivos *.dll* y *.xml*) para usar con varios marcos de trabajo y versiones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple frameworks and versions.</span></span> <span data-ttu-id="a90ed-256">Cuando se instala en una aplicación o biblioteca, se seleccionan los recursos adecuados en función de la plataforma de destino especificada por la aplicación o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a90ed-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="a90ed-257">Los recursos que definen la interfaz se encuentran en la carpeta *ref* y los recursos que definen la implementación se encuentran en la carpeta *lib*.</span><span class="sxs-lookup"><span data-stu-id="a90ed-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="a90ed-258">platform</span><span class="sxs-lookup"><span data-stu-id="a90ed-258">platform</span></span>

<span data-ttu-id="a90ed-259">Un sistema operativo y el hardware en que se ejecuta, como Windows, macOS, Linux, iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="a90ed-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="a90ed-260">Aquí tiene ejemplos de uso en frases:</span><span class="sxs-lookup"><span data-stu-id="a90ed-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="a90ed-261">".NET Core es una implementación multiplataforma de .NET".</span><span class="sxs-lookup"><span data-stu-id="a90ed-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="a90ed-262">"Los perfiles de PCL representan plataformas de Microsoft, mientras que .NET Standard es independiente de la plataforma".</span><span class="sxs-lookup"><span data-stu-id="a90ed-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="a90ed-263">La documentación de .NET usa con frecuencia "plataforma de .NET" para indicar una implementación de .NET o la pila de .NET que incluye todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="a90ed-264">Estos dos usos tienden a confundirse con el significado principal (sistema operativo o hardware), por tanto, tenemos previsto eliminar estos usos de la documentación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="a90ed-265">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a90ed-265">runtime</span></span>

<span data-ttu-id="a90ed-266">El entorno de ejecución de un programa administrado.</span><span class="sxs-lookup"><span data-stu-id="a90ed-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="a90ed-267">El sistema operativo forma parte del entorno de ejecución, pero no del entorno de ejecución .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="a90ed-268">Estos son algunos ejemplos de los entornos de ejecución .NET:</span><span class="sxs-lookup"><span data-stu-id="a90ed-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="a90ed-269">Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="a90ed-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="a90ed-270">Core Common Language Runtime (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="a90ed-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="a90ed-271">.NET Native (para UWP)</span><span class="sxs-lookup"><span data-stu-id="a90ed-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="a90ed-272">Entorno de ejecución Mono</span><span class="sxs-lookup"><span data-stu-id="a90ed-272">Mono runtime</span></span>

<span data-ttu-id="a90ed-273">A veces, la documentación de .NET usa "entorno de ejecución" para indicar una implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="a90ed-274">Por ejemplo, en las siguientes frases "entorno de ejecución" debe reemplazarse por "implementación":</span><span class="sxs-lookup"><span data-stu-id="a90ed-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="a90ed-275">"Los diversos entornos de ejecución .NET implementan versiones concretas de .NET Standard".</span><span class="sxs-lookup"><span data-stu-id="a90ed-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="a90ed-276">"Las bibliotecas diseñadas para ejecutarse en varios entornos de ejecución deben tener como destino este marco de trabajo".</span><span class="sxs-lookup"><span data-stu-id="a90ed-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="a90ed-277">(Hace referencia a .NET Standard).</span><span class="sxs-lookup"><span data-stu-id="a90ed-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="a90ed-278">"Los diversos entornos de ejecución .NET implementan versiones concretas de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a90ed-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="a90ed-279">…</span><span class="sxs-lookup"><span data-stu-id="a90ed-279">…</span></span> <span data-ttu-id="a90ed-280">Cada versión del entorno de ejecución de .NET anuncia la última versión de .NET Standard que admite...".</span><span class="sxs-lookup"><span data-stu-id="a90ed-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="a90ed-281">Tenemos previsto eliminar este uso incoherente.</span><span class="sxs-lookup"><span data-stu-id="a90ed-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="a90ed-282">pila</span><span class="sxs-lookup"><span data-stu-id="a90ed-282">stack</span></span>

<span data-ttu-id="a90ed-283">Un conjunto de tecnologías de programación que se usan para compilar y ejecutar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a90ed-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="a90ed-284">La "pila de .NET" hace referencia a .NET Standard y a todas las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="a90ed-285">La frase "una pila de .NET" puede hacer referencia a una implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="a90ed-286">versión de .NET Framework de destino</span><span class="sxs-lookup"><span data-stu-id="a90ed-286">target framework</span></span>

<span data-ttu-id="a90ed-287">La colección de API de las que depende una aplicación o biblioteca de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="a90ed-288">Una aplicación o biblioteca puede tener como destino una versión de .NET Standard (por ejemplo, .NET Standard 2.0), que es la especificación de un conjunto estándar de API de todas las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="a90ed-289">Una aplicación o biblioteca también puede tener como destino una versión de una implementación específica de .NET; en este caso, obtiene acceso a las API específicas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="a90ed-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="a90ed-290">Por ejemplo, una aplicación que tenga como destino Xamarin.iOS obtiene acceso a contenedores de la API de iOS proporcionados por Xamarin.</span><span class="sxs-lookup"><span data-stu-id="a90ed-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="a90ed-291">Para algunas plataformas de destino (por ejemplo, .NET Framework), las API disponibles se definen mediante los ensamblados que una implementación de .NET instala en un sistema y pueden incluir las API del marco de trabajo de la aplicación (por ejemplo, ASP.NET o Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="a90ed-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="a90ed-292">Para plataformas de destino basadas en paquetes (por ejemplo, .NET Standard y .NET Core), las API se definen mediante los paquetes instalados en la aplicación o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a90ed-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="a90ed-293">En ese caso, la plataforma de destino especifica implícitamente un metapaquete que hace referencia a todos los paquetes que forman el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a90ed-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="a90ed-294">Vea [Plataformas de destino](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="a90ed-295">TFM</span><span class="sxs-lookup"><span data-stu-id="a90ed-295">TFM</span></span>

<span data-ttu-id="a90ed-296">Moniker de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="a90ed-296">Target framework moniker.</span></span>

<span data-ttu-id="a90ed-297">Un formato de token normalizado para especificar la plataforma de destino de una aplicación o biblioteca de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="a90ed-298">Se suele hacer referencia a las plataformas de destino mediante un nombre corto, como `net462`.</span><span class="sxs-lookup"><span data-stu-id="a90ed-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="a90ed-299">Los TFM de formato largo (como .NETFramework,Version=4.6.2) existen, pero no se suelen usar para especificar una plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="a90ed-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="a90ed-300">Vea [Plataformas de destino](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a90ed-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="a90ed-301">UWP</span><span class="sxs-lookup"><span data-stu-id="a90ed-301">UWP</span></span>

<span data-ttu-id="a90ed-302">Plataforma universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="a90ed-302">Universal Windows Platform.</span></span>

<span data-ttu-id="a90ed-303">Una implementación de .NET que se usa para compilar aplicaciones Windows modernas y táctiles y software para Internet de las cosas (IoT).</span><span class="sxs-lookup"><span data-stu-id="a90ed-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="a90ed-304">Se ha diseñado para unificar los diferentes tipos de dispositivos de destino, incluidos equipos, tabletas, phablets, teléfonos e incluso la consola Xbox.</span><span class="sxs-lookup"><span data-stu-id="a90ed-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="a90ed-305">UWP proporciona muchos servicios, como una tienda de aplicaciones centralizada, un entorno de ejecución (AppContainer) y un conjunto de API de Windows para usar en lugar de Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="a90ed-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="a90ed-306">Las aplicaciones pueden escribirse en C++, C#, VB.NET y JavaScript.</span><span class="sxs-lookup"><span data-stu-id="a90ed-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="a90ed-307">Al usar C# y VB.NET, .NET Core proporciona las API de .NET.</span><span class="sxs-lookup"><span data-stu-id="a90ed-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="a90ed-308">Vea también</span><span class="sxs-lookup"><span data-stu-id="a90ed-308">See also</span></span>

[<span data-ttu-id="a90ed-309">Guía de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="a90ed-310">Guía de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a90ed-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="a90ed-311">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a90ed-311">.NET Core</span></span>](../core/index.md)  
<span data-ttu-id="a90ed-312">[ASP.NET Overview](/aspnet/index#pivot=aspnet) (Información general de ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="a90ed-312">[ASP.NET Overview](/aspnet/index#pivot=aspnet)</span></span>  
<span data-ttu-id="a90ed-313">[ASP.NET Core Overview](/aspnet/index#pivot=core) (Información general de ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="a90ed-313">[ASP.NET Core Overview](/aspnet/index#pivot=core)</span></span>  


