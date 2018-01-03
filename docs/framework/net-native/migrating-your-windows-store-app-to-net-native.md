---
title: "Migrar la aplicación de la Tienda Windows a .NET Native"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
caps.latest.revision: "29"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce23d66f79f94af74250cff137499f6c8b1582ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="a97e1-102">Migrar la aplicación de la Tienda Windows a .NET Native</span><span class="sxs-lookup"><span data-stu-id="a97e1-102">Migrating Your Windows Store App to .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="a97e1-103"> proporciona la compilación estática de aplicaciones en la Tienda Windows o en el equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="a97e1-103"> provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="a97e1-104">Esto difiere de la compilación dinámica para las aplicaciones de la Tienda Windows realizada por el compilador Just-in-time (JIT) o el [generador de imágenes nativas (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a97e1-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="a97e1-105">A pesar de las diferencias, [!INCLUDE[net_native](../../../includes/net-native-md.md)] intenta mantener la compatibilidad con [.NET para aplicaciones de la Tienda Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span><span class="sxs-lookup"><span data-stu-id="a97e1-105">Despite the differences, [!INCLUDE[net_native](../../../includes/net-native-md.md)] tries to maintain compatibility with the [.NET for Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="a97e1-106">En general, lo que funciona en .NET para aplicaciones de la Tienda Windows también funciona en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-106">For the most part, things that work on the .NET for Windows Store apps also work with [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  <span data-ttu-id="a97e1-107">Sin embargo, en algunos casos, puede encontrar cambios de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a97e1-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="a97e1-108">En este documento se describen las diferencias entre las aplicaciones estándar de .NET para la Tienda Windows y [!INCLUDE[net_native](../../../includes/net-native-md.md)] en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="a97e1-108">This document discusses these differences between the standard .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the following areas:</span></span>  
  
-   [<span data-ttu-id="a97e1-109">Diferencias de tiempo de ejecución generales</span><span class="sxs-lookup"><span data-stu-id="a97e1-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="a97e1-110">Diferencias de programación dinámicas</span><span class="sxs-lookup"><span data-stu-id="a97e1-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="a97e1-111">Otras diferencias relacionadas con la reflexión</span><span class="sxs-lookup"><span data-stu-id="a97e1-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="a97e1-112">Escenarios no compatibles e interfaces API</span><span class="sxs-lookup"><span data-stu-id="a97e1-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="a97e1-113">Diferencias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a97e1-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="a97e1-114">Diferencias de tiempo de ejecución generales</span><span class="sxs-lookup"><span data-stu-id="a97e1-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="a97e1-115">Las excepciones (por ejemplo, <xref:System.TypeLoadException>) que se producen por el compilador JIT cuando una aplicación se ejecuta en Common Language Runtime (CLR) suelen generar errores en tiempo de compilación cuando las procesa [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="a97e1-116">No llame al método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> desde un subproceso de interfaz de usuario de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a97e1-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="a97e1-117">Esto puede provocar un interbloqueo en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-117">This can result in a deadlock on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="a97e1-118">No confíe en el orden de invocación de constructores de clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="a97e1-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="a97e1-119">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el orden de invocación es diferente del orden en el tiempo de ejecución estándar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-119">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="a97e1-120">(Incluso con el tiempo de ejecución estándar, no debe confiar en el orden de ejecución de los constructores de clases estáticas).</span><span class="sxs-lookup"><span data-stu-id="a97e1-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="a97e1-121">Un bucle infinito sin hacer una llamada (por ejemplo, `while(true);`) en cualquier subproceso puede hacer que la aplicación se detenga.</span><span class="sxs-lookup"><span data-stu-id="a97e1-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="a97e1-122">De igual modo, las esperas largas o infinitas pueden detener la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a97e1-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="a97e1-123">Ciertos ciclos de inicialización genérica no producen excepciones en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-123">Certain generic initialization cycles don't throw exceptions in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-124">Por ejemplo, el código siguiente produce una excepción <xref:System.TypeLoadException> en el CLR estándar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="a97e1-125">Pero no ocurre así en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-125">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="a97e1-126">En algunos casos, [!INCLUDE[net_native](../../../includes/net-native-md.md)] proporciona implementaciones diferentes de las bibliotecas de clases de.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a97e1-126">In some cases, [!INCLUDE[net_native](../../../includes/net-native-md.md)] provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="a97e1-127">Un objeto devuelto desde un método siempre implementará los miembros del tipo devuelto.</span><span class="sxs-lookup"><span data-stu-id="a97e1-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="a97e1-128">Sin embargo, dado que su implementación de respaldo es diferente, es posible que no pueda convertirlo en el mismo conjunto de tipos como lo haría en otras plataformas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a97e1-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="a97e1-129">Por ejemplo, en algunos casos, es posible que no pueda convertir el objeto de interfaz <xref:System.Collections.Generic.IEnumerable%601> devuelto por métodos como <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="a97e1-130">La caché de WinInet no está habilitada de forma predeterminada en .NET para aplicaciones de la Tienda Windows, pero lo está en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-131">Esto mejora el rendimiento, pero tiene implicaciones en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a97e1-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="a97e1-132">No es necesaria ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="a97e1-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="a97e1-133">Diferencias de programación dinámicas</span><span class="sxs-lookup"><span data-stu-id="a97e1-133">Dynamic programming differences</span></span>  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="a97e1-134"> vincula estáticamente el código de .NET Framework para que el código de la aplicación local obtenga un rendimiento máximo.</span><span class="sxs-lookup"><span data-stu-id="a97e1-134"> statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="a97e1-135">Sin embargo, el tamaño de los archivos binarios debe seguir siendo reducido para dar cabida a la totalidad de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a97e1-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="a97e1-136">El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] resuelve esta limitación mediante el uso de un reductor de dependencia que quita las referencias a código no utilizado.</span><span class="sxs-lookup"><span data-stu-id="a97e1-136">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="a97e1-137">Sin embargo, es posible que [!INCLUDE[net_native](../../../includes/net-native-md.md)] no pueda mantener o generar cierto código e información de tipos cuando dicha información no se pueda inferir de forma estática en tiempo de compilación, sino que se recupere dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a97e1-137">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="a97e1-138"> habilita la reflexión y la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="a97e1-138"> does enable reflection and dynamic programming.</span></span> <span data-ttu-id="a97e1-139">Sin embargo, no todos los tipos se pueden marcar para la reflexión, porque esto haría que el tamaño del código generado fuese demasiado grande (sobre todo porque se admite el reflejo en las API públicas en .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="a97e1-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="a97e1-140">El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] toma decisiones inteligentes acerca de qué tipos deben admitir la reflexión y mantiene los metadatos y genera código solo para esos tipos.</span><span class="sxs-lookup"><span data-stu-id="a97e1-140">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="a97e1-141">Por ejemplo, el enlace de datos requiere una aplicación para poder asignar los nombres de propiedad a las funciones.</span><span class="sxs-lookup"><span data-stu-id="a97e1-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="a97e1-142">En .NET para aplicaciones de la Tienda Windows, Common Language Runtime utiliza automáticamente la reflexión para proporcionar esta capacidad para tipos administrados y tipos nativos disponibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="a97e1-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="a97e1-143">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el compilador incluye automáticamente metadatos para tipos a los que se enlazan datos.</span><span class="sxs-lookup"><span data-stu-id="a97e1-143">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="a97e1-144">El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] también puede controlar tipos genéricos comúnmente utilizados como <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602>, que funcionan sin necesidad de directivas ni indicaciones.</span><span class="sxs-lookup"><span data-stu-id="a97e1-144">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="a97e1-145">La palabra clave [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) también se admite dentro de ciertos límites.</span><span class="sxs-lookup"><span data-stu-id="a97e1-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a97e1-146">Pruebe exhaustivamente todas las rutas de código dinámico cuando traslade su aplicación a [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-146">You should test all dynamic code paths thoroughly when porting your app to [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a97e1-147">La configuración predeterminada de [!INCLUDE[net_native](../../../includes/net-native-md.md)] es suficiente para la mayoría de los desarrolladores, pero algunos quizá deseen ajustar al máximo sus configuraciones mediante el uso de un archivo de directivas de tiempo de ejecución (.rd.xml).</span><span class="sxs-lookup"><span data-stu-id="a97e1-147">The default configuration for [!INCLUDE[net_native](../../../includes/net-native-md.md)] is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="a97e1-148">Además, en algunos casos, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no es capaz de determinar qué metadatos deben estar disponibles para la reflexión y tiene que basarse en las indicaciones, especialmente en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a97e1-148">In addition, in some cases, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="a97e1-149">Algunas construcciones como <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> y <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> no se pueden determinar estáticamente.</span><span class="sxs-lookup"><span data-stu-id="a97e1-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="a97e1-150">Dado que el compilador no puede determinar la creación de instancias, un tipo genérico que desee reflejar tiene que especificarse mediante directivas de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a97e1-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="a97e1-151">Esto no es solo porque se debe incluir todo el código, sino también porque la reflexión en tipos genéricos puede formar un ciclo infinito (por ejemplo, cuando se invoca un método genérico en un tipo genérico).</span><span class="sxs-lookup"><span data-stu-id="a97e1-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a97e1-152">Las directivas de tiempo de ejecución se definen en un archivo de directivas de tiempo de ejecución (.rd.xml).</span><span class="sxs-lookup"><span data-stu-id="a97e1-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="a97e1-153">Para obtener información general sobre el uso de este archivo, vea [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md) (Introducción).</span><span class="sxs-lookup"><span data-stu-id="a97e1-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="a97e1-154">Para obtener información sobre las directivas de tiempo de ejecución, vea [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a97e1-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="a97e1-155"> también incluye herramientas de generación de perfiles con las que los desarrolladores pueden determinar más fácilmente qué tipos aparte del conjunto predeterminado deben admitir la reflexión.</span><span class="sxs-lookup"><span data-stu-id="a97e1-155"> also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="a97e1-156">Otras diferencias relacionadas con la reflexión</span><span class="sxs-lookup"><span data-stu-id="a97e1-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="a97e1-157">Hay otra serie de diferencias relacionadas con la reflexión en el comportamiento entre .NET para aplicaciones de la Tienda Windows y [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a97e1-158">En [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a97e1-158">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="a97e1-159">No se admite la reflexión privada sobre los tipos y miembros de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a97e1-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="a97e1-160">Sin embargo, puede reflejar sobre sus propios tipos y miembros privados, así como sobre los tipos y miembros de bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="a97e1-161">La propiedad <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> devuelve correctamente `false` para un objeto <xref:System.Reflection.ParameterInfo> que representa un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="a97e1-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="a97e1-162">En .NET para aplicaciones de la Tienda Windows, devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="a97e1-163">El lenguaje intermedio (IL) no admite esto directamente y se deja la interpretación al lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a97e1-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="a97e1-164">Los miembros públicos de las estructuras <xref:System.RuntimeFieldHandle> y <xref:System.RuntimeMethodHandle> no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="a97e1-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="a97e1-165">Estos tipos solo son compatibles con LINQ, árboles de expresión e inicialización de matrices estáticas.</span><span class="sxs-lookup"><span data-stu-id="a97e1-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="a97e1-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> y <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> incluyen miembros ocultos en clases base y, por tanto, se pueden invalidar sin necesidad de hacerlo de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="a97e1-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="a97e1-167">Esto también es así para otros métodos [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a97e1-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="a97e1-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> y <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> no producirán un error al intentar crear ciertas combinaciones (por ejemplo, una matriz de byrefs).</span><span class="sxs-lookup"><span data-stu-id="a97e1-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="a97e1-169">No se puede utilizar la reflexión para invocar a los miembros que tienen parámetros de puntero.</span><span class="sxs-lookup"><span data-stu-id="a97e1-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="a97e1-170">No se puede utilizar la reflexión para obtener o establecer un campo de puntero.</span><span class="sxs-lookup"><span data-stu-id="a97e1-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="a97e1-171">Cuando el número de argumentos es incorrecto y el tipo de uno de los argumentos es incorrecto, [!INCLUDE[net_native](../../../includes/net-native-md.md)] produce <xref:System.ArgumentException> en lugar de <xref:System.Reflection.TargetParameterCountException>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-171">When the argument count is wrong and the type of one of the arguments is incorrect, [!INCLUDE[net_native](../../../includes/net-native-md.md)] throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="a97e1-172">Por lo general, no se admite la serialización binaria de excepciones.</span><span class="sxs-lookup"><span data-stu-id="a97e1-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="a97e1-173">Como resultado, se pueden agregar objetos no serializables al diccionario <xref:System.Exception.Data%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="a97e1-174">Escenarios no compatibles e interfaces API</span><span class="sxs-lookup"><span data-stu-id="a97e1-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="a97e1-175">En las secciones siguientes se enumeran varios escenarios e interfaces API no compatibles con el desarrollo general, la interoperabilidad y las tecnologías como HTTPClient y Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="a97e1-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="a97e1-176">Desarrollo general</span><span class="sxs-lookup"><span data-stu-id="a97e1-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="a97e1-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="a97e1-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="a97e1-178">Interop</span><span class="sxs-lookup"><span data-stu-id="a97e1-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="a97e1-179">Interfaces API no compatibles</span><span class="sxs-lookup"><span data-stu-id="a97e1-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="a97e1-180">Diferencias de desarrollo generales</span><span class="sxs-lookup"><span data-stu-id="a97e1-180">General development differences</span></span>  
 <span data-ttu-id="a97e1-181">**Tipos de valor**</span><span class="sxs-lookup"><span data-stu-id="a97e1-181">**Value types**</span></span>  
  
-   <span data-ttu-id="a97e1-182">Si invalida los métodos <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> y <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> para un tipo de valor, no llame a las implementaciones de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a97e1-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="a97e1-183">En .NET para aplicaciones de la Tienda Windows, estos métodos se basan en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="a97e1-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="a97e1-184">En tiempo de compilación, [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera una implementación que no se basa en la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a97e1-184">At compile time, [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="a97e1-185">Esto significa que si no se invalidan estos dos métodos, funcionarán del modo esperado, ya que [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera la implementación en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a97e1-185">This means that if you don't override these two methods, they will work as expected, because [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates the implementation at compile time.</span></span> <span data-ttu-id="a97e1-186">Sin embargo, si se invalidan estos métodos, pero se llama a la implementación de la clase base, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a97e1-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="a97e1-187">No se admiten tipos de valor superiores a un megabyte.</span><span class="sxs-lookup"><span data-stu-id="a97e1-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="a97e1-188">Los tipos de valor no pueden tener un constructor predeterminado en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-188">Value types can't have a default constructor in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-189">(C# y Visual Basic prohíben los constructores predeterminados en tipos de valor,</span><span class="sxs-lookup"><span data-stu-id="a97e1-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="a97e1-190">pero estos pueden crearse en IL).</span><span class="sxs-lookup"><span data-stu-id="a97e1-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="a97e1-191">**Matrices**</span><span class="sxs-lookup"><span data-stu-id="a97e1-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="a97e1-192">No se admiten matrices con límite inferior distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="a97e1-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="a97e1-193">Normalmente, estas matrices se crean mediante una llamada a la sobrecarga <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="a97e1-194">No se admite la creación dinámica de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="a97e1-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="a97e1-195">Estas matrices se crean normalmente mediante una llamada a una sobrecarga del método <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> que incluye un parámetro `lengths`, o mediante una llamada al método <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a97e1-196">No se admiten matrices multidimensionales que tengan cuatro o más dimensiones; es decir, que el valor de su propiedad <xref:System.Array.Rank%2A?displayProperty=nameWithType> sea de cuatro o más.</span><span class="sxs-lookup"><span data-stu-id="a97e1-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="a97e1-197">En su lugar, use [matrices escalonadas](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (una matriz de matrices).</span><span class="sxs-lookup"><span data-stu-id="a97e1-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="a97e1-198">Por ejemplo, `array[x,y,z]` no es válido, pero `array[x][y][z]` sí lo es.</span><span class="sxs-lookup"><span data-stu-id="a97e1-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="a97e1-199">No se admite varianza en matrices multidimensionales, ya que causa una excepción <xref:System.InvalidCastException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a97e1-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="a97e1-200">**Genéricos**</span><span class="sxs-lookup"><span data-stu-id="a97e1-200">**Generics**</span></span>  
  
-   <span data-ttu-id="a97e1-201">La expansión infinita de tipos genéricos produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="a97e1-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="a97e1-202">Por ejemplo, este código produce un error al compilar:</span><span class="sxs-lookup"><span data-stu-id="a97e1-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="a97e1-203">**Punteros**</span><span class="sxs-lookup"><span data-stu-id="a97e1-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="a97e1-204">No se admiten las matrices de punteros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="a97e1-205">No se puede utilizar la reflexión para obtener o establecer un campo de puntero.</span><span class="sxs-lookup"><span data-stu-id="a97e1-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="a97e1-206">**Serialización**</span><span class="sxs-lookup"><span data-stu-id="a97e1-206">**Serialization**</span></span>  
  
 <span data-ttu-id="a97e1-207">No se admite el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="a97e1-208">En su lugar, use el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="a97e1-209">**Recursos**</span><span class="sxs-lookup"><span data-stu-id="a97e1-209">**Resources**</span></span>  
  
 <span data-ttu-id="a97e1-210">No se admite el uso de recursos localizados con la clase <xref:System.Diagnostics.Tracing.EventSource> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="a97e1-211">La propiedad <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> no define los recursos localizados.</span><span class="sxs-lookup"><span data-stu-id="a97e1-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="a97e1-212">**Delegados**</span><span class="sxs-lookup"><span data-stu-id="a97e1-212">**Delegates**</span></span>  
  
 <span data-ttu-id="a97e1-213">No se admite`Delegate.BeginInvoke` ni `Delegate.EndInvoke` .</span><span class="sxs-lookup"><span data-stu-id="a97e1-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="a97e1-214">**Async**</span><span class="sxs-lookup"><span data-stu-id="a97e1-214">**Async**</span></span>  
  
 <span data-ttu-id="a97e1-215">No se admite la lógica de subprocesos en las sobrecargas de la tarea IAsync.</span><span class="sxs-lookup"><span data-stu-id="a97e1-215">Threading logic in overloads of Task IAsync isn't supported.</span></span>  
  
 <span data-ttu-id="a97e1-216">**Otras API**</span><span class="sxs-lookup"><span data-stu-id="a97e1-216">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="a97e1-217">La propiedad <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> produce una excepción <xref:System.PlatformNotSupportedException> si no se aplica al tipo un atributo <xref:System.Runtime.InteropServices.GuidAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-217">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="a97e1-218">El GUID se utiliza principalmente para la compatibilidad con COM.</span><span class="sxs-lookup"><span data-stu-id="a97e1-218">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="a97e1-219">El método <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> analiza correctamente las cadenas que contienen fechas cortas en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-219">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-220">Sin embargo, no mantiene la compatibilidad con los cambios en el análisis de fecha y hora que se describen en los artículos [KB2803771](http://support.microsoft.com/kb/2803771) y [KB2803755](http://support.microsoft.com/kb/2803755)de Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="a97e1-220">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](http://support.microsoft.com/kb/2803771) and [KB2803755](http://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="a97e1-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")` se redondea correctamente en [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-222">En algunas versiones de CLR, la cadena resultante se trunca en lugar de redondearse.</span><span class="sxs-lookup"><span data-stu-id="a97e1-222">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="a97e1-223">Diferencias de HttpClient</span><span class="sxs-lookup"><span data-stu-id="a97e1-223">HttpClient differences</span></span>  
 <span data-ttu-id="a97e1-224">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], la clase <xref:System.Net.Http.HttpClientHandler> usa internamente WinINet (a través de la clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) ) en lugar de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> usadas en las aplicaciones de .NET para la Tienda Windows estándar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-224">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="a97e1-225">WinINet no admite todas las opciones de configuración que admite la clase <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-225">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="a97e1-226">Como resultado:</span><span class="sxs-lookup"><span data-stu-id="a97e1-226">As a result:</span></span>  
  
-   <span data-ttu-id="a97e1-227">Algunas de las propiedades de capacidad en <xref:System.Net.Http.HttpClientHandler> devuelven `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelven `true` en las aplicaciones estándar de .NET para la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a97e1-227">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="a97e1-228">Algunos de los descriptores de acceso `get` de la propiedad de configuración siempre devuelven un valor fijo en [!INCLUDE[net_native](../../../includes/net-native-md.md)] que es diferente al valor configurable predeterminado en .NET para aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a97e1-228">Some of the configuration property `get` accessors always return a fixed value on [!INCLUDE[net_native](../../../includes/net-native-md.md)] that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a97e1-229">En las subsecciones siguientes se tratan algunas otras diferencias de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a97e1-229">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="a97e1-230">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="a97e1-230">**Proxy**</span></span>  
  
 <span data-ttu-id="a97e1-231">La clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) no admite la configuración o la invalidación del proxy por solicitud.</span><span class="sxs-lookup"><span data-stu-id="a97e1-231">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="a97e1-232">Esto significa que todas las solicitudes hechas en [!INCLUDE[net_native](../../../includes/net-native-md.md)] utilizan el servidor proxy configurado por el sistema o ningún servidor proxy, en función del valor de la propiedad <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-232">This means that all requests on [!INCLUDE[net_native](../../../includes/net-native-md.md)] use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="a97e1-233">En .NET para aplicaciones de la Tienda Windows, el servidor proxy se define mediante la propiedad <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-233">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="a97e1-234">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], si se ajusta <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> a un valor distinto de `null`, se produce una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-234">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="a97e1-235">La propiedad <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> devuelve `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelve `true` en las aplicaciones estándar de .NET Framework para la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a97e1-235">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a97e1-236">**Redireccionamiento automático**</span><span class="sxs-lookup"><span data-stu-id="a97e1-236">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="a97e1-237">La clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) no permite el número máximo de redirecciones automáticas que se van a configurar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-237">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="a97e1-238">El valor predeterminado de la propiedad <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> es de 50 en las aplicaciones estándar de .NET para la Tienda Windows y se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-238">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="a97e1-239">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el valor de esta propiedad es de 10, y si se intenta modificar, se produce una excepción <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-239">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="a97e1-240">La propiedad <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> devuelve `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelve `true` en .NET para aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a97e1-240">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a97e1-241">**Descompresión automática**</span><span class="sxs-lookup"><span data-stu-id="a97e1-241">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="a97e1-242">.NET para aplicaciones de la Tienda Windows permite establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> en <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>, o en <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-242">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="a97e1-243"> solo admite <xref:System.Net.DecompressionMethods.Deflate> con <xref:System.Net.DecompressionMethods.GZip>o <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-243"> only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="a97e1-244">Si se intenta establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> en <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> , la propiedad se establece, de forma silenciosa, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-244">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="a97e1-245">**Cookies**</span><span class="sxs-lookup"><span data-stu-id="a97e1-245">**Cookies**</span></span>  
  
 <span data-ttu-id="a97e1-246">La administración de cookies se realiza simultáneamente mediante <xref:System.Net.Http.HttpClient> y WinINet.</span><span class="sxs-lookup"><span data-stu-id="a97e1-246">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="a97e1-247">Las cookies de <xref:System.Net.CookieContainer> se combinan con las cookies de la caché de cookies de WinINet.</span><span class="sxs-lookup"><span data-stu-id="a97e1-247">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="a97e1-248">Si se elimina una cookie de <xref:System.Net.CookieContainer> , se evita que <xref:System.Net.Http.HttpClient> envíe la cookie, pero si WinINet ya ha visto la cookie y el usuario no ha eliminado las cookies, WinINet la envía.</span><span class="sxs-lookup"><span data-stu-id="a97e1-248">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="a97e1-249">No es posible eliminar una cookie de WinINet mediante programación con las API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-249">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="a97e1-250">Si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> en `false`, solo se consigue que <xref:System.Net.Http.HttpClient> deje de enviar cookies; puede que WinINet siga incluyendo sus cookies en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a97e1-250">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="a97e1-251">**Credenciales**</span><span class="sxs-lookup"><span data-stu-id="a97e1-251">**Credentials**</span></span>  
  
 <span data-ttu-id="a97e1-252">En .NET para aplicaciones de la Tienda Windows, las propiedades <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> trabajan de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="a97e1-252">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="a97e1-253">Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> acepta cualquier objeto que implemente la interfaz <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-253">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="a97e1-254">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> en `true` , la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> pasa a ser `null`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-254">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="a97e1-255">Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> solo se puede establecer en `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o en un objeto de tipo <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-255">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="a97e1-256">Si se asigna cualquier otro objeto <xref:System.Net.ICredentials> (el más conocido es <xref:System.Net.CredentialCache>) a la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> , se produce una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-256">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="a97e1-257">**Otras características no compatibles o no configurables**</span><span class="sxs-lookup"><span data-stu-id="a97e1-257">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="a97e1-258">En [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a97e1-258">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="a97e1-259">El valor de la propiedad <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> es siempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-259">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="a97e1-260">En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-260">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="a97e1-261">La propiedad <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> no es configurable.</span><span class="sxs-lookup"><span data-stu-id="a97e1-261">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="a97e1-262">La propiedad <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> es siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-262">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="a97e1-263">En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-263">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="a97e1-264">El encabezado `SetCookie2` de las respuestas se omite como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a97e1-264">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="a97e1-265">Diferencias de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="a97e1-265">Interop differences</span></span>  
 <span data-ttu-id="a97e1-266">**Interfaces API desusadas**</span><span class="sxs-lookup"><span data-stu-id="a97e1-266">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="a97e1-267">Hay una serie de interfaces API poco utilizadas para la interoperabilidad con código administrado que están desusadas.</span><span class="sxs-lookup"><span data-stu-id="a97e1-267">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="a97e1-268">Cuando se utilizan con [!INCLUDE[net_native](../../../includes/net-native-md.md)], estas API pueden producir una excepción <xref:System.NotImplementedException> o <xref:System.PlatformNotSupportedException> , o tener como resultado un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="a97e1-268">When used with [!INCLUDE[net_native](../../../includes/net-native-md.md)], these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="a97e1-269">En .NET para aplicaciones de la Tienda Windows, estas API se marcan como obsoletas, aunque al llamarlas se genera una advertencia del compilador en lugar de un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="a97e1-269">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="a97e1-270">Interfaces API desusadas para el cálculo de referencias de `VARIANT` :</span><span class="sxs-lookup"><span data-stu-id="a97e1-270">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a97e1-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>se admite, pero produce una excepción en algunos escenarios, como cuando se utiliza con [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) o las variantes de byref.</span><span class="sxs-lookup"><span data-stu-id="a97e1-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) or byref variants.</span></span>  
  
 <span data-ttu-id="a97e1-272">API en desuso API para compatibilidad de [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) :</span><span class="sxs-lookup"><span data-stu-id="a97e1-272">Deprecated APIs for [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) support:</span></span>  
  
|<span data-ttu-id="a97e1-273">Tipo</span><span class="sxs-lookup"><span data-stu-id="a97e1-273">Type</span></span>|<span data-ttu-id="a97e1-274">Miembro</span><span class="sxs-lookup"><span data-stu-id="a97e1-274">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="a97e1-275">Atributo no compatible</span><span class="sxs-lookup"><span data-stu-id="a97e1-275">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="a97e1-276">Interfaces API obsoletas para eventos COM clásicos:</span><span class="sxs-lookup"><span data-stu-id="a97e1-276">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="a97e1-277">Interfaces API obsoletas en la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>, que no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a97e1-277">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
|<span data-ttu-id="a97e1-278">Tipo</span><span class="sxs-lookup"><span data-stu-id="a97e1-278">Type</span></span>|<span data-ttu-id="a97e1-279">Miembro</span><span class="sxs-lookup"><span data-stu-id="a97e1-279">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="a97e1-280">Todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="a97e1-281">Todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-281">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="a97e1-282">Todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-282">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a97e1-283">Otras características de interoperabilidad no compatibles:</span><span class="sxs-lookup"><span data-stu-id="a97e1-283">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="a97e1-284">Tipo</span><span class="sxs-lookup"><span data-stu-id="a97e1-284">Type</span></span>|<span data-ttu-id="a97e1-285">Miembro</span><span class="sxs-lookup"><span data-stu-id="a97e1-285">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="a97e1-286">Todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-286">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="a97e1-287">Todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="a97e1-287">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="a97e1-288">Interfaces API de cálculo de referencias rara vez utilizadas:</span><span class="sxs-lookup"><span data-stu-id="a97e1-288">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="a97e1-289">Tipo</span><span class="sxs-lookup"><span data-stu-id="a97e1-289">Type</span></span>|<span data-ttu-id="a97e1-290">Miembro</span><span class="sxs-lookup"><span data-stu-id="a97e1-290">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 <span data-ttu-id="a97e1-291">**Compatibilidad con la invocación de plataforma y la interoperabilidad COM**</span><span class="sxs-lookup"><span data-stu-id="a97e1-291">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="a97e1-292">[!INCLUDE[net_native](../../../includes/net-native-md.md)]sigue admitiendo la mayoría de escenarios de invocación de plataforma e interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="a97e1-292">Most platform invoke and COM interop scenarios are still supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-293">En particular, se admite toda la interoperabilidad con las API de Windows en tiempo de ejecución (WinRT) y todo el cálculo de referencias necesarias para Windows en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a97e1-293">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="a97e1-294">Esto incluye compatibilidad de cálculo de referencias para:</span><span class="sxs-lookup"><span data-stu-id="a97e1-294">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="a97e1-295">Matrices (incluido <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="a97e1-295">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="a97e1-296">Delegados</span><span class="sxs-lookup"><span data-stu-id="a97e1-296">Delegates</span></span>  
  
-   <span data-ttu-id="a97e1-297">Cadenas (Unicode, Ansi y HSTRING)</span><span class="sxs-lookup"><span data-stu-id="a97e1-297">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="a97e1-298">Structs (`byref` y `byval`)</span><span class="sxs-lookup"><span data-stu-id="a97e1-298">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="a97e1-299">Uniones</span><span class="sxs-lookup"><span data-stu-id="a97e1-299">Unions</span></span>  
  
-   <span data-ttu-id="a97e1-300">Identificadores de Win32</span><span class="sxs-lookup"><span data-stu-id="a97e1-300">Win32 handles</span></span>  
  
-   <span data-ttu-id="a97e1-301">Todas las construcciones de WinRT</span><span class="sxs-lookup"><span data-stu-id="a97e1-301">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="a97e1-302">Compatibilidad parcial para calcular referencias de tipos de variante.</span><span class="sxs-lookup"><span data-stu-id="a97e1-302">Partial support for marshaling variant types.</span></span> <span data-ttu-id="a97e1-303">Se admiten los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="a97e1-303">The following are supported:</span></span>  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [<span data-ttu-id="a97e1-304">IUnknown</span><span class="sxs-lookup"><span data-stu-id="a97e1-304">IUnknown</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 <span data-ttu-id="a97e1-305">Sin embargo, [!INCLUDE[net_native](../../../includes/net-native-md.md)] no admite:</span><span class="sxs-lookup"><span data-stu-id="a97e1-305">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] doesn't support the following:</span></span>  
  
-   <span data-ttu-id="a97e1-306">Uso de eventos COM clásicos</span><span class="sxs-lookup"><span data-stu-id="a97e1-306">Using classic COM events</span></span>  
  
-   <span data-ttu-id="a97e1-307">Implementación de la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> en un tipo administrado</span><span class="sxs-lookup"><span data-stu-id="a97e1-307">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="a97e1-308">Implementar la [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interfaz en un tipo administrado a través de la <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> atributo.</span><span class="sxs-lookup"><span data-stu-id="a97e1-308">Implementing the [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="a97e1-309">Tenga en cuenta no obstante que no puede llamar a objetos COM mediante `IDispatch`y que el objeto administrado no puede implementar `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="a97e1-309">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="a97e1-310">No se admite el uso de la reflexión para invocar un método de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="a97e1-310">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="a97e1-311">Puede evitar esta limitación si encapsula la llamada de método en otro método y utiliza la reflexión para llamar en su lugar al contenedor.</span><span class="sxs-lookup"><span data-stu-id="a97e1-311">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="a97e1-312">Otras diferencias de las API de .NET para aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="a97e1-312">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="a97e1-313">En esta sección se enumeran las API restantes que no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-313">This section lists the remaining APIs that aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-314">El grupo más grande de las API no compatibles son las de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a97e1-314">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="a97e1-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="a97e1-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="a97e1-316">Los tipos de los espacios de nombres <xref:System.ComponentModel.DataAnnotations> y <xref:System.ComponentModel.DataAnnotations.Schema> no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-316">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-317">Entre estos se incluyen los siguientes tipos que están presentes en .NET para aplicaciones de la Tienda Windows destinadas a Windows 8:</span><span class="sxs-lookup"><span data-stu-id="a97e1-317">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a97e1-318">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="a97e1-318">**Visual Basic**</span></span>  
  
 <span data-ttu-id="a97e1-319">Visual Basic no es compatible actualmente con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-319">Visual Basic isn't currently supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-320">Los siguientes tipos de los espacios de nombres <xref:Microsoft.VisualBasic> y <xref:Microsoft.VisualBasic.CompilerServices> no están disponibles en [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a97e1-320">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a97e1-321">**Contexto de reflexión (espacio de nombres System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="a97e1-321">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="a97e1-322">La clase <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-322">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a97e1-323">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="a97e1-323">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="a97e1-324">La clase <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-324">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a97e1-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="a97e1-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="a97e1-326">Los tipos de los [espacios de nombres System.ServiceModel.*](http://msdn.microsoft.com/library/gg145010.aspx) no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97e1-326">The types in the [System.ServiceModel.* namespaces](http://msdn.microsoft.com/library/gg145010.aspx) aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="a97e1-327">Entre ellos se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a97e1-327">These includes the following types:</span></span>  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>|  
  
### <a name="differences-in-serializers"></a><span data-ttu-id="a97e1-328">Diferencias en los serializadores</span><span class="sxs-lookup"><span data-stu-id="a97e1-328">Differences in serializers</span></span>  
 <span data-ttu-id="a97e1-329">Las siguientes diferencias conciernen a la serialización y deserialización con las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="a97e1-329">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="a97e1-330">En [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> generan error al serializar o deserializar una clase derivada que tiene un miembro de clase base cuyo tipo no es un tipo de serialización de raíz.</span><span class="sxs-lookup"><span data-stu-id="a97e1-330">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="a97e1-331">Por ejemplo, en el siguiente código, si se intenta serializar o deserializar `Y` , se genera un error:</span><span class="sxs-lookup"><span data-stu-id="a97e1-331">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="a97e1-332">El tipo `InnerType` es desconocido para el serializador, dado que los miembros de la clase base no se recorren durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="a97e1-332">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="a97e1-333"><xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no pueden serializar una clase o estructura que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-333"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="a97e1-334">Por ejemplo, los siguientes tipos no se producen error al serializar o deserializar:</span><span class="sxs-lookup"><span data-stu-id="a97e1-334">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="a97e1-335"><xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar el valor del objeto siguiente, puesto que desconoce el tipo exacto del objeto que se va a serializar:</span><span class="sxs-lookup"><span data-stu-id="a97e1-335"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="a97e1-336"><xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar o deserializar si el tipo del objeto serializado es <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-336"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="a97e1-337">Todos los serializadores (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer>) producen error al general código de serialización para el tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o para un tipo que contenga <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a97e1-337">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a97e1-338">En su lugar, muestran errores en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a97e1-338">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="a97e1-339">No se garantiza que los siguientes constructores de los tipos de serialización funcionen del modo esperado:</span><span class="sxs-lookup"><span data-stu-id="a97e1-339">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
-   <span data-ttu-id="a97e1-340"><xref:System.Xml.Serialization.XmlSerializer> produce un error al general código para un tipo que tiene métodos con cualquiera de los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="a97e1-340"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="a97e1-341"><xref:System.Xml.Serialization.XmlSerializer> no aceptan la interfaz de serialización personalizada <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="a97e1-341"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="a97e1-342">Si tiene una clase que implementa esta interfaz, <xref:System.Xml.Serialization.XmlSerializer> considera el tipo como un tipo de objeto CLR estándar (POCO) y solo serializa sus propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="a97e1-342">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="a97e1-343">Serializar un objeto <xref:System.Exception> simple, como el siguiente, no funciona bien con <xref:System.Runtime.Serialization.DataContractSerializer> ni con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="a97e1-343">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="a97e1-344">Diferencias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a97e1-344">Visual Studio differences</span></span>  
 <span data-ttu-id="a97e1-345">**Excepciones y depuración**</span><span class="sxs-lookup"><span data-stu-id="a97e1-345">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="a97e1-346">Cuando se ejecutan aplicaciones compiladas mediante el uso de [!INCLUDE[net_native](../../../includes/net-native-md.md)] en el depurador, se habilitan las primeras excepciones para los siguientes tipos de excepción:</span><span class="sxs-lookup"><span data-stu-id="a97e1-346">When you're running apps compiled by using [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="a97e1-347">**Compilación de aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="a97e1-347">**Building apps**</span></span>  
  
 <span data-ttu-id="a97e1-348">Use las herramientas de compilación x86 que se utilizan de manera predeterminada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a97e1-348">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="a97e1-349">No recomendamos el uso de las herramientas de MSBuild AMD64, ya que podrían crear problemas de compilación. Estas herramientas se encuentran en C:\Archivos de programa (x86)\MSBuild\12.0\bin\amd64.</span><span class="sxs-lookup"><span data-stu-id="a97e1-349">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="a97e1-350">**Generadores de perfiles**</span><span class="sxs-lookup"><span data-stu-id="a97e1-350">**Profilers**</span></span>  
  
-   <span data-ttu-id="a97e1-351">El generador de perfiles de CPU de Visual Studio CPU y el generador de perfiles de memoria de XAML no muestran correctamente Just-My-Code (solo mi código).</span><span class="sxs-lookup"><span data-stu-id="a97e1-351">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="a97e1-352">El generador de perfiles de memoria de XAML no muestra con precisión los datos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="a97e1-352">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="a97e1-353">El generador de perfiles de CPU no identifica correctamente los módulos y muestra nombres de función prefijados.</span><span class="sxs-lookup"><span data-stu-id="a97e1-353">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="a97e1-354">**Proyectos de biblioteca de prueba unitaria**</span><span class="sxs-lookup"><span data-stu-id="a97e1-354">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="a97e1-355">No se admite la habilitación de [!INCLUDE[net_native](../../../includes/net-native-md.md)] en una biblioteca de prueba unitaria para un proyecto de aplicaciones de la Tienda Windows; provoca que el proyecto no se pueda compilar.</span><span class="sxs-lookup"><span data-stu-id="a97e1-355">Enabling [!INCLUDE[net_native](../../../includes/net-native-md.md)] on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97e1-356">Vea también</span><span class="sxs-lookup"><span data-stu-id="a97e1-356">See Also</span></span>  
 [<span data-ttu-id="a97e1-357">Introducción</span><span class="sxs-lookup"><span data-stu-id="a97e1-357">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="a97e1-358">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="a97e1-358">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a97e1-359">Información general de aplicaciones de .NET para la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="a97e1-359">.NET For Windows Store apps overview</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="a97e1-360">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="a97e1-360">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
