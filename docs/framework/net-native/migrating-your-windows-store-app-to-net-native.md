---
description: Más información acerca de cómo migrar la aplicación de la tienda Windows a .NET Native
title: Migrar la aplicación de la Tienda Windows a .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 39f8427474b37c42d856366bf4e4d677ba77e7f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738720"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a><span data-ttu-id="162f0-103">Migrar la aplicación de la tienda Windows a .NET Native</span><span class="sxs-lookup"><span data-stu-id="162f0-103">Migrate Your Windows Store App to .NET Native</span></span>

<span data-ttu-id="162f0-104">.NET Native proporciona la compilación estática de aplicaciones en la tienda Windows o en el equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="162f0-104">.NET Native provides static compilation of apps in the Windows Store or on the developer's computer.</span></span> <span data-ttu-id="162f0-105">Esto difiere de la compilación dinámica para las aplicaciones de la Tienda Windows realizada por el compilador Just-in-time (JIT) o el [generador de imágenes nativas (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="162f0-105">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="162f0-106">A pesar de las diferencias, .NET Native intenta mantener la compatibilidad con [.net para aplicaciones de la tienda Windows](/previous-versions/windows/apps/br230302(v=vs.140)).</span><span class="sxs-lookup"><span data-stu-id="162f0-106">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](/previous-versions/windows/apps/br230302(v=vs.140)).</span></span> <span data-ttu-id="162f0-107">En su mayor parte, todo lo que funciona en .NET para aplicaciones de la tienda Windows también funciona con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-107">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="162f0-108">Sin embargo, en algunos casos, puede encontrar cambios de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="162f0-108">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="162f0-109">En este documento se describen estas diferencias entre las aplicaciones estándar de .NET para la tienda Windows y .NET Native en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="162f0-109">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>

- [<span data-ttu-id="162f0-110">Diferencias de tiempo de ejecución generales</span><span class="sxs-lookup"><span data-stu-id="162f0-110">General runtime differences</span></span>](#Runtime)

- [<span data-ttu-id="162f0-111">Diferencias de programación dinámicas</span><span class="sxs-lookup"><span data-stu-id="162f0-111">Dynamic programming differences</span></span>](#Dynamic)

- [<span data-ttu-id="162f0-112">Otras diferencias relacionadas con la reflexión</span><span class="sxs-lookup"><span data-stu-id="162f0-112">Other reflection-related differences</span></span>](#Reflection)

- [<span data-ttu-id="162f0-113">Escenarios no compatibles e interfaces API</span><span class="sxs-lookup"><span data-stu-id="162f0-113">Unsupported scenarios and APIs</span></span>](#Unsupported)

- [<span data-ttu-id="162f0-114">Diferencias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="162f0-114">Visual Studio differences</span></span>](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a><span data-ttu-id="162f0-115">Diferencias de tiempo de ejecución generales</span><span class="sxs-lookup"><span data-stu-id="162f0-115">General runtime differences</span></span>

- <span data-ttu-id="162f0-116">Las excepciones, como <xref:System.TypeLoadException> , que inicia el compilador JIT cuando una aplicación se ejecuta en el Common Language Runtime (CLR) suelen producir errores en tiempo de compilación cuando se procesan por .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-116">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>

- <span data-ttu-id="162f0-117">No llame al método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> desde un subproceso de interfaz de usuario de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="162f0-117">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="162f0-118">Esto puede producir un interbloqueo en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-118">This can result in a deadlock on .NET Native.</span></span>

- <span data-ttu-id="162f0-119">No confíe en el orden de invocación de constructores de clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="162f0-119">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="162f0-120">En .NET Native, el orden de invocación es diferente del orden en el tiempo de ejecución estándar.</span><span class="sxs-lookup"><span data-stu-id="162f0-120">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="162f0-121">(Incluso con el tiempo de ejecución estándar, no debe confiar en el orden de ejecución de los constructores de clases estáticas).</span><span class="sxs-lookup"><span data-stu-id="162f0-121">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>

- <span data-ttu-id="162f0-122">Un bucle infinito sin hacer una llamada (por ejemplo, `while(true);`) en cualquier subproceso puede hacer que la aplicación se detenga.</span><span class="sxs-lookup"><span data-stu-id="162f0-122">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="162f0-123">De igual modo, las esperas largas o infinitas pueden detener la aplicación.</span><span class="sxs-lookup"><span data-stu-id="162f0-123">Similarly, large or infinite waits may bring the app to a halt.</span></span>

- <span data-ttu-id="162f0-124">Ciertos ciclos de inicialización genéricos no producen excepciones en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-124">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="162f0-125">Por ejemplo, el código siguiente produce una excepción <xref:System.TypeLoadException> en el CLR estándar.</span><span class="sxs-lookup"><span data-stu-id="162f0-125">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="162f0-126">En .NET Native, no.</span><span class="sxs-lookup"><span data-stu-id="162f0-126">In .NET Native, it doesn't.</span></span>

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- <span data-ttu-id="162f0-127">En algunos casos, .NET Native proporciona implementaciones diferentes de .NET Framework bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="162f0-127">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="162f0-128">Un objeto devuelto desde un método siempre implementará los miembros del tipo devuelto.</span><span class="sxs-lookup"><span data-stu-id="162f0-128">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="162f0-129">Sin embargo, dado que su implementación de respaldo es diferente, es posible que no pueda convertirlo en el mismo conjunto de tipos como lo haría en otras plataformas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="162f0-129">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="162f0-130">Por ejemplo, en algunos casos, es posible que no pueda convertir el objeto de interfaz <xref:System.Collections.Generic.IEnumerable%601> devuelto por métodos como <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.</span><span class="sxs-lookup"><span data-stu-id="162f0-130">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>

- <span data-ttu-id="162f0-131">La caché de WinInet no está habilitada de forma predeterminada en .NET para aplicaciones de la tienda Windows, pero está en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-131">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="162f0-132">Esto mejora el rendimiento, pero tiene implicaciones en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="162f0-132">This improves performance but has working set implications.</span></span> <span data-ttu-id="162f0-133">No es necesaria ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="162f0-133">No developer action is necessary.</span></span>

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a><span data-ttu-id="162f0-134">Diferencias de programación dinámicas</span><span class="sxs-lookup"><span data-stu-id="162f0-134">Dynamic programming differences</span></span>

<span data-ttu-id="162f0-135">.NET Native vincula estáticamente en el código del .NET Framework para que el código de la aplicación sea local para obtener el máximo rendimiento.</span><span class="sxs-lookup"><span data-stu-id="162f0-135">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="162f0-136">Sin embargo, el tamaño de los archivos binarios debe seguir siendo reducido para dar cabida a la totalidad de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="162f0-136">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="162f0-137">El compilador de .NET Native resuelve esta limitación mediante el uso de un reductor de dependencia que quita las referencias a código no utilizado.</span><span class="sxs-lookup"><span data-stu-id="162f0-137">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="162f0-138">Sin embargo, es posible que .NET Native no mantenga ni genere información de tipo y código cuando esa información no se pueda inferir de forma estática en tiempo de compilación, sino que se recupere dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="162f0-138">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>

<span data-ttu-id="162f0-139">.NET Native habilita la reflexión y la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="162f0-139">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="162f0-140">Sin embargo, no todos los tipos se pueden marcar para la reflexión, porque esto haría que el tamaño del código generado fuese demasiado grande (sobre todo porque se admite el reflejo en las API públicas en .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="162f0-140">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="162f0-141">El compilador de .NET Native toma decisiones inteligentes sobre qué tipos deben admitir la reflexión y mantiene los metadatos y genera código solo para esos tipos.</span><span class="sxs-lookup"><span data-stu-id="162f0-141">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>

<span data-ttu-id="162f0-142">Por ejemplo, el enlace de datos requiere una aplicación para poder asignar los nombres de propiedad a las funciones.</span><span class="sxs-lookup"><span data-stu-id="162f0-142">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="162f0-143">En .NET para aplicaciones de la Tienda Windows, Common Language Runtime utiliza automáticamente la reflexión para proporcionar esta capacidad para tipos administrados y tipos nativos disponibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="162f0-143">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="162f0-144">En .NET Native, el compilador incluye automáticamente los metadatos de los tipos a los que se enlazan los datos.</span><span class="sxs-lookup"><span data-stu-id="162f0-144">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>

<span data-ttu-id="162f0-145">El compilador .NET Native también puede controlar tipos genéricos usados comúnmente como <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602> , que funcionan sin necesidad de ninguna sugerencia ni Directiva.</span><span class="sxs-lookup"><span data-stu-id="162f0-145">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="162f0-146">La palabra clave [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) también se admite dentro de ciertos límites.</span><span class="sxs-lookup"><span data-stu-id="162f0-146">The [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) keyword is also supported within certain limits.</span></span>

> [!NOTE]
> <span data-ttu-id="162f0-147">Debe probar exhaustivamente todas las rutas de código dinámicas al migrar la aplicación a .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-147">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>

<span data-ttu-id="162f0-148">La configuración predeterminada para .NET Native es suficiente para la mayoría de los desarrolladores, pero algunos desarrolladores pueden querer ajustar sus configuraciones mediante un archivo de directivas en tiempo de ejecución (.rd.xml).</span><span class="sxs-lookup"><span data-stu-id="162f0-148">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="162f0-149">Además, en algunos casos, el compilador .NET Native no puede determinar qué metadatos deben estar disponibles para la reflexión y se basa en sugerencias, especialmente en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="162f0-149">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>

- <span data-ttu-id="162f0-150">Algunas construcciones como <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> y <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> no se pueden determinar estáticamente.</span><span class="sxs-lookup"><span data-stu-id="162f0-150">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>

- <span data-ttu-id="162f0-151">Dado que el compilador no puede determinar la creación de instancias, un tipo genérico que desee reflejar tiene que especificarse mediante directivas de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="162f0-151">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="162f0-152">Esto no es solo porque se debe incluir todo el código, sino también porque la reflexión en tipos genéricos puede formar un ciclo infinito (por ejemplo, cuando se invoca un método genérico en un tipo genérico).</span><span class="sxs-lookup"><span data-stu-id="162f0-152">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>

> [!NOTE]
> <span data-ttu-id="162f0-153">Las directivas de tiempo de ejecución se definen en un archivo de directivas de tiempo de ejecución (.rd.xml).</span><span class="sxs-lookup"><span data-stu-id="162f0-153">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="162f0-154">Para obtener información general sobre el uso de este archivo, vea [Getting Started](getting-started-with-net-native.md) (Introducción).</span><span class="sxs-lookup"><span data-stu-id="162f0-154">For general information about using this file, see [Getting Started](getting-started-with-net-native.md).</span></span> <span data-ttu-id="162f0-155">Para obtener información sobre las directivas de tiempo de ejecución, vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="162f0-155">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>

<span data-ttu-id="162f0-156">.NET Native también incluye herramientas de generación de perfiles que ayudan al desarrollador a determinar qué tipos fuera del conjunto predeterminado deben admitir la reflexión.</span><span class="sxs-lookup"><span data-stu-id="162f0-156">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a><span data-ttu-id="162f0-157">Otras diferencias relacionadas con la reflexión</span><span class="sxs-lookup"><span data-stu-id="162f0-157">Other reflection-related differences</span></span>

<span data-ttu-id="162f0-158">Hay varias diferencias relacionadas con la reflexión en el comportamiento entre .NET para aplicaciones de la tienda Windows y .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-158">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>

<span data-ttu-id="162f0-159">En .NET Native:</span><span class="sxs-lookup"><span data-stu-id="162f0-159">In .NET Native:</span></span>

- <span data-ttu-id="162f0-160">No se admite la reflexión privada sobre los tipos y miembros de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="162f0-160">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="162f0-161">Sin embargo, puede reflejar sobre sus propios tipos y miembros privados, así como sobre los tipos y miembros de bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="162f0-161">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>

- <span data-ttu-id="162f0-162">La propiedad <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> devuelve correctamente `false` para un objeto <xref:System.Reflection.ParameterInfo> que representa un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="162f0-162">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="162f0-163">En .NET para aplicaciones de la Tienda Windows, devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="162f0-163">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="162f0-164">El lenguaje intermedio (IL) no admite esto directamente y se deja la interpretación en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="162f0-164">Intermediate language (IL) doesn't support this directly, and interpretation is left to the language.</span></span>

- <span data-ttu-id="162f0-165">Los miembros públicos de las estructuras <xref:System.RuntimeFieldHandle> y <xref:System.RuntimeMethodHandle> no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="162f0-165">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="162f0-166">Estos tipos solo son compatibles con LINQ, árboles de expresión e inicialización de matrices estáticas.</span><span class="sxs-lookup"><span data-stu-id="162f0-166">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>

- <span data-ttu-id="162f0-167"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> y <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> incluyen miembros ocultos en clases base y, por tanto, se pueden invalidar sin necesidad de hacerlo de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="162f0-167"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="162f0-168">Esto también es así para otros métodos [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) .</span><span class="sxs-lookup"><span data-stu-id="162f0-168">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) methods.</span></span>

- <span data-ttu-id="162f0-169"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> y <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> no producen errores al intentar crear ciertas combinaciones (por ejemplo, una matriz de `byref` objetos).</span><span class="sxs-lookup"><span data-stu-id="162f0-169"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of `byref` objects).</span></span>

- <span data-ttu-id="162f0-170">No se puede utilizar la reflexión para invocar a los miembros que tienen parámetros de puntero.</span><span class="sxs-lookup"><span data-stu-id="162f0-170">You can't use reflection to invoke members that have pointer parameters.</span></span>

- <span data-ttu-id="162f0-171">No se puede utilizar la reflexión para obtener o establecer un campo de puntero.</span><span class="sxs-lookup"><span data-stu-id="162f0-171">You can't use reflection to get or set a pointer field.</span></span>

- <span data-ttu-id="162f0-172">Cuando el número de argumentos es incorrecto y el tipo de uno de los argumentos es incorrecto, .NET Native produce una excepción <xref:System.ArgumentException> en lugar de un <xref:System.Reflection.TargetParameterCountException> .</span><span class="sxs-lookup"><span data-stu-id="162f0-172">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>

- <span data-ttu-id="162f0-173">Por lo general, no se admite la serialización binaria de excepciones.</span><span class="sxs-lookup"><span data-stu-id="162f0-173">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="162f0-174">Como resultado, se pueden agregar objetos no serializables al diccionario <xref:System.Exception.Data%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="162f0-174">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="162f0-175">Escenarios no compatibles e interfaces API</span><span class="sxs-lookup"><span data-stu-id="162f0-175">Unsupported scenarios and APIs</span></span>

<span data-ttu-id="162f0-176">En las secciones siguientes se enumeran varios escenarios e interfaces API no compatibles con el desarrollo general, la interoperabilidad y las tecnologías como HTTPClient y Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="162f0-176">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>

- [<span data-ttu-id="162f0-177">Desarrollo general</span><span class="sxs-lookup"><span data-stu-id="162f0-177">General development</span></span>](#General)

- [<span data-ttu-id="162f0-178">HttpClient</span><span class="sxs-lookup"><span data-stu-id="162f0-178">HttpClient</span></span>](#HttpClient)

- [<span data-ttu-id="162f0-179">Interop</span><span class="sxs-lookup"><span data-stu-id="162f0-179">Interop</span></span>](#Interop)

- [<span data-ttu-id="162f0-180">Interfaces API no compatibles</span><span class="sxs-lookup"><span data-stu-id="162f0-180">Unsupported APIs</span></span>](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a><span data-ttu-id="162f0-181">Diferencias de desarrollo generales</span><span class="sxs-lookup"><span data-stu-id="162f0-181">General development differences</span></span>

<span data-ttu-id="162f0-182">**Tipos de valor**</span><span class="sxs-lookup"><span data-stu-id="162f0-182">**Value types**</span></span>

- <span data-ttu-id="162f0-183">Si invalida los métodos <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> y <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> para un tipo de valor, no llame a las implementaciones de la clase base.</span><span class="sxs-lookup"><span data-stu-id="162f0-183">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="162f0-184">En .NET para aplicaciones de la Tienda Windows, estos métodos se basan en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="162f0-184">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="162f0-185">En tiempo de compilación, .NET Native genera una implementación que no se basa en la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="162f0-185">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="162f0-186">Esto significa que si no se invalidan estos dos métodos, funcionarán según lo esperado, ya que .NET Native genera la implementación en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="162f0-186">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="162f0-187">Sin embargo, si se invalidan estos métodos, pero se llama a la implementación de la clase base, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="162f0-187">However, overriding these methods but calling the base class implementation results in an exception.</span></span>

- <span data-ttu-id="162f0-188">No se admiten tipos de valor mayores de 1 megabyte.</span><span class="sxs-lookup"><span data-stu-id="162f0-188">Value types larger than 1 megabyte aren't supported.</span></span>

- <span data-ttu-id="162f0-189">Los tipos de valor no pueden tener un constructor sin parámetros en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-189">Value types can't have a parameterless constructor in .NET Native.</span></span> <span data-ttu-id="162f0-190">(C# y Visual Basic prohíben los constructores sin parámetros en los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="162f0-190">(C# and Visual Basic prohibit parameterless constructors on value types.</span></span> <span data-ttu-id="162f0-191">pero estos pueden crearse en IL).</span><span class="sxs-lookup"><span data-stu-id="162f0-191">However, these can be created in IL.)</span></span>

<span data-ttu-id="162f0-192">**Matrices**</span><span class="sxs-lookup"><span data-stu-id="162f0-192">**Arrays**</span></span>

- <span data-ttu-id="162f0-193">No se admiten matrices con límite inferior distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="162f0-193">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="162f0-194">Normalmente, estas matrices se crean mediante una llamada a la sobrecarga <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="162f0-194">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

- <span data-ttu-id="162f0-195">No se admite la creación dinámica de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="162f0-195">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="162f0-196">Estas matrices se crean normalmente mediante una llamada a una sobrecarga del método <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> que incluye un parámetro `lengths` , o mediante una llamada al método <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="162f0-196">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="162f0-197">No se admiten matrices multidimensionales que tengan cuatro o más dimensiones; es decir, que el valor de su propiedad <xref:System.Array.Rank%2A?displayProperty=nameWithType> sea de cuatro o más.</span><span class="sxs-lookup"><span data-stu-id="162f0-197">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="162f0-198">En su lugar, use [matrices escalonadas](../../csharp/programming-guide/arrays/jagged-arrays.md) (una matriz de matrices).</span><span class="sxs-lookup"><span data-stu-id="162f0-198">Use [jagged arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="162f0-199">Por ejemplo, `array[x,y,z]` no es válido, pero `array[x][y][z]` sí lo es.</span><span class="sxs-lookup"><span data-stu-id="162f0-199">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>

- <span data-ttu-id="162f0-200">No se admite varianza en matrices multidimensionales, ya que causa una excepción <xref:System.InvalidCastException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="162f0-200">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>

<span data-ttu-id="162f0-201">**Genéricos**</span><span class="sxs-lookup"><span data-stu-id="162f0-201">**Generics**</span></span>

- <span data-ttu-id="162f0-202">La expansión infinita de tipos genéricos produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="162f0-202">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="162f0-203">Por ejemplo, este código produce un error al compilar:</span><span class="sxs-lookup"><span data-stu-id="162f0-203">For example, this code fails to compile:</span></span>

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

<span data-ttu-id="162f0-204">**Punteros**</span><span class="sxs-lookup"><span data-stu-id="162f0-204">**Pointers**</span></span>

- <span data-ttu-id="162f0-205">No se admiten las matrices de punteros.</span><span class="sxs-lookup"><span data-stu-id="162f0-205">Arrays of pointers aren't supported.</span></span>

- <span data-ttu-id="162f0-206">No se puede utilizar la reflexión para obtener o establecer un campo de puntero.</span><span class="sxs-lookup"><span data-stu-id="162f0-206">You can't use reflection to get or set a pointer field.</span></span>

<span data-ttu-id="162f0-207">**Serialización**</span><span class="sxs-lookup"><span data-stu-id="162f0-207">**Serialization**</span></span>

<span data-ttu-id="162f0-208">No se admite el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> .</span><span class="sxs-lookup"><span data-stu-id="162f0-208">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="162f0-209">En su lugar, use el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="162f0-209">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>

<span data-ttu-id="162f0-210">**Recursos**</span><span class="sxs-lookup"><span data-stu-id="162f0-210">**Resources**</span></span>

<span data-ttu-id="162f0-211">No se admite el uso de recursos localizados con la clase <xref:System.Diagnostics.Tracing.EventSource> .</span><span class="sxs-lookup"><span data-stu-id="162f0-211">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="162f0-212">La propiedad <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> no define los recursos localizados.</span><span class="sxs-lookup"><span data-stu-id="162f0-212">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>

<span data-ttu-id="162f0-213">**Delegados**</span><span class="sxs-lookup"><span data-stu-id="162f0-213">**Delegates**</span></span>

<span data-ttu-id="162f0-214">No se admite`Delegate.BeginInvoke` ni `Delegate.EndInvoke` .</span><span class="sxs-lookup"><span data-stu-id="162f0-214">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>

<span data-ttu-id="162f0-215">**Otras API**</span><span class="sxs-lookup"><span data-stu-id="162f0-215">**Miscellaneous APIs**</span></span>

- <span data-ttu-id="162f0-216">La propiedad [TypeInfo. GUID](xref:System.Type.GUID) produce una <xref:System.PlatformNotSupportedException> excepción si <xref:System.Runtime.InteropServices.GuidAttribute> no se aplica un atributo al tipo.</span><span class="sxs-lookup"><span data-stu-id="162f0-216">The [TypeInfo.GUID](xref:System.Type.GUID) property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="162f0-217">El GUID se utiliza principalmente para la compatibilidad con COM.</span><span class="sxs-lookup"><span data-stu-id="162f0-217">The GUID is used primarily for COM support.</span></span>

- <span data-ttu-id="162f0-218">El <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> método analiza correctamente las cadenas que contienen fechas cortas en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-218">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="162f0-219">Sin embargo, no mantiene la compatibilidad con los cambios en el análisis de fecha y hora que se describen en los artículos [KB2803771](https://support.microsoft.com/kb/2803771) y [KB2803755](https://support.microsoft.com/kb/2803755)de Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="162f0-219">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>

- <span data-ttu-id="162f0-220"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")`se redondea correctamente en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-220"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="162f0-221">En algunas versiones de CLR, la cadena resultante se trunca en lugar de redondearse.</span><span class="sxs-lookup"><span data-stu-id="162f0-221">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a><span data-ttu-id="162f0-222">Diferencias de HttpClient</span><span class="sxs-lookup"><span data-stu-id="162f0-222">HttpClient differences</span></span>

<span data-ttu-id="162f0-223">En .NET Native, la <xref:System.Net.Http.HttpClientHandler> clase usa internamente WinInet (a través de la <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase) en lugar de las <xref:System.Net.WebRequest> <xref:System.Net.WebResponse> clases y usadas en las aplicaciones estándar de .net para la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="162f0-223">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="162f0-224">WinINet no admite todas las opciones de configuración que admite la clase <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="162f0-224">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="162f0-225">Como resultado:</span><span class="sxs-lookup"><span data-stu-id="162f0-225">As a result:</span></span>

- <span data-ttu-id="162f0-226">Algunas de las propiedades de la funcionalidad de <xref:System.Net.Http.HttpClientHandler> devuelven `false` en .net Native, mientras que devuelven `true` en las aplicaciones estándar de .net para la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="162f0-226">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>

- <span data-ttu-id="162f0-227">Algunos de los descriptores de acceso de la propiedad de configuración `get` siempre devuelven un valor fijo en .net Native que es diferente del valor configurable predeterminado en .net para aplicaciones de la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="162f0-227">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>

<span data-ttu-id="162f0-228">En las subsecciones siguientes se tratan algunas otras diferencias de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="162f0-228">Some additional behavior differences are covered in the following subsections.</span></span>

<span data-ttu-id="162f0-229">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="162f0-229">**Proxy**</span></span>

<span data-ttu-id="162f0-230">La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase no admite la configuración o invalidación del proxy en función de cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="162f0-230">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="162f0-231">Esto significa que todas las solicitudes de .NET Native usar el servidor proxy configurado por el sistema o ningún servidor proxy, dependiendo del valor de la <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="162f0-231">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="162f0-232">En .NET para aplicaciones de la Tienda Windows, el servidor proxy se define mediante la propiedad <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="162f0-232">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="162f0-233">En .NET Native, si <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> se establece en un valor distinto de, se `null` produce una <xref:System.PlatformNotSupportedException> excepción.</span><span class="sxs-lookup"><span data-stu-id="162f0-233">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="162f0-234">La <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> propiedad devuelve `false` en .net Native, mientras que devuelve `true` en el .NET Framework estándar para las aplicaciones de la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="162f0-234">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>

<span data-ttu-id="162f0-235">**Redireccionamiento automático**</span><span class="sxs-lookup"><span data-stu-id="162f0-235">**Automatic redirection**</span></span>

<span data-ttu-id="162f0-236">La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase no permite configurar el número máximo de redirecciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="162f0-236">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="162f0-237">El valor predeterminado de la propiedad <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> es de 50 en las aplicaciones estándar de .NET para la Tienda Windows y se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="162f0-237">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="162f0-238">En .NET Native, el valor de esta propiedad es 10 y, al intentar modificarlo, se produce una <xref:System.PlatformNotSupportedException> excepción.</span><span class="sxs-lookup"><span data-stu-id="162f0-238">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="162f0-239">La <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> propiedad devuelve `false` en .net Native, mientras que devuelve `true` en .net para aplicaciones de la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="162f0-239">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>

<span data-ttu-id="162f0-240">**Descompresión automática**</span><span class="sxs-lookup"><span data-stu-id="162f0-240">**Automatic decompression**</span></span>

<span data-ttu-id="162f0-241">.NET para aplicaciones de la Tienda Windows permite establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> en <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>, o en <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="162f0-241">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="162f0-242">.NET Native solo admite <xref:System.Net.DecompressionMethods.Deflate> junto con <xref:System.Net.DecompressionMethods.GZip> , o <xref:System.Net.DecompressionMethods.None> .</span><span class="sxs-lookup"><span data-stu-id="162f0-242">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="162f0-243">Si se intenta establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> en <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> , la propiedad se establece, de forma silenciosa, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="162f0-243">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>

<span data-ttu-id="162f0-244">**Cookies**</span><span class="sxs-lookup"><span data-stu-id="162f0-244">**Cookies**</span></span>

<span data-ttu-id="162f0-245">La administración de cookies se realiza simultáneamente mediante <xref:System.Net.Http.HttpClient> y WinINet.</span><span class="sxs-lookup"><span data-stu-id="162f0-245">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="162f0-246">Las cookies de <xref:System.Net.CookieContainer> se combinan con las cookies de la caché de cookies de WinINet.</span><span class="sxs-lookup"><span data-stu-id="162f0-246">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="162f0-247">Si se elimina una cookie de <xref:System.Net.CookieContainer> , se evita que <xref:System.Net.Http.HttpClient> envíe la cookie, pero si WinINet ya ha visto la cookie y el usuario no ha eliminado las cookies, WinINet la envía.</span><span class="sxs-lookup"><span data-stu-id="162f0-247">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="162f0-248">No es posible eliminar una cookie de WinINet mediante programación con las API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="162f0-248">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="162f0-249">Si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> en `false` , solo se consigue que <xref:System.Net.Http.HttpClient> deje de enviar cookies; puede que WinINet siga incluyendo sus cookies en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="162f0-249">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>

<span data-ttu-id="162f0-250">**Credenciales**</span><span class="sxs-lookup"><span data-stu-id="162f0-250">**Credentials**</span></span>

<span data-ttu-id="162f0-251">En .NET para aplicaciones de la Tienda Windows, las propiedades <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> trabajan de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="162f0-251">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="162f0-252">Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> acepta cualquier objeto que implemente la interfaz <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="162f0-252">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="162f0-253">En .NET Native, si se establece la <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> propiedad en, `true` la <xref:System.Net.Http.HttpClientHandler.Credentials%2A> propiedad se convierte en `null` .</span><span class="sxs-lookup"><span data-stu-id="162f0-253">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="162f0-254">Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> solo se puede establecer en `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o en un objeto de tipo <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="162f0-254">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="162f0-255">Si se asigna cualquier otro objeto <xref:System.Net.ICredentials> (el más conocido es <xref:System.Net.CredentialCache>) a la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> , se produce una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="162f0-255">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="162f0-256">**Otras características no compatibles o no configurables**</span><span class="sxs-lookup"><span data-stu-id="162f0-256">**Other unsupported or unconfigurable features**</span></span>

<span data-ttu-id="162f0-257">En .NET Native:</span><span class="sxs-lookup"><span data-stu-id="162f0-257">In .NET Native:</span></span>

- <span data-ttu-id="162f0-258">El valor de la propiedad <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> es siempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="162f0-258">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="162f0-259">En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="162f0-259">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>

- <span data-ttu-id="162f0-260">La propiedad <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> no es configurable.</span><span class="sxs-lookup"><span data-stu-id="162f0-260">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>

- <span data-ttu-id="162f0-261">La propiedad <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> es siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="162f0-261">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="162f0-262">En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="162f0-262">In .NET for Windows Store apps, the default is `false`.</span></span>

- <span data-ttu-id="162f0-263">El encabezado `SetCookie2` de las respuestas se omite como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="162f0-263">The `SetCookie2` header in responses is ignored as obsolete.</span></span>

<a name="Interop"></a>

### <a name="interop-differences"></a><span data-ttu-id="162f0-264">Diferencias de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="162f0-264">Interop differences</span></span>

 <span data-ttu-id="162f0-265">**Interfaces API desusadas**</span><span class="sxs-lookup"><span data-stu-id="162f0-265">**Deprecated APIs**</span></span>

 <span data-ttu-id="162f0-266">Hay una serie de interfaces API poco utilizadas para la interoperabilidad con código administrado que están desusadas.</span><span class="sxs-lookup"><span data-stu-id="162f0-266">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="162f0-267">Cuando se usa con .NET Native, estas API pueden producir <xref:System.NotImplementedException> una <xref:System.PlatformNotSupportedException> excepción o, o producir un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="162f0-267">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="162f0-268">En .NET para aplicaciones de la Tienda Windows, estas API se marcan como obsoletas, aunque al llamarlas se genera una advertencia del compilador en lugar de un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="162f0-268">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>

 <span data-ttu-id="162f0-269">Las API desusadas para el `VARIANT` cálculo de referencias incluyen:</span><span class="sxs-lookup"><span data-stu-id="162f0-269">Deprecated APIs for `VARIANT` marshaling include:</span></span>

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <span data-ttu-id="162f0-270"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> se admite, pero produce una excepción en algunos escenarios, como cuando se usa con [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) o `byref` variantes.</span><span class="sxs-lookup"><span data-stu-id="162f0-270"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or `byref` variants.</span></span>

 <span data-ttu-id="162f0-271">Las API desusadas para la compatibilidad con [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) incluyen:</span><span class="sxs-lookup"><span data-stu-id="162f0-271">Deprecated APIs for [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support include:</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

<span data-ttu-id="162f0-272">Las API en desuso para eventos COM clásicos incluyen:</span><span class="sxs-lookup"><span data-stu-id="162f0-272">Deprecated APIs for classic COM events include:</span></span>

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

<span data-ttu-id="162f0-273">Las API en desuso en la <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interfaz, que no se admiten en .net Native, incluyen:</span><span class="sxs-lookup"><span data-stu-id="162f0-273">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native, include:</span></span>

- <span data-ttu-id="162f0-274"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="162f0-274"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="162f0-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="162f0-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="162f0-276"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="162f0-276"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

<span data-ttu-id="162f0-277">Otras características de interoperabilidad no compatibles incluyen:</span><span class="sxs-lookup"><span data-stu-id="162f0-277">Other unsupported interop features include:</span></span>

- <span data-ttu-id="162f0-278"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="162f0-278"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="162f0-279"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="162f0-279"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 <span data-ttu-id="162f0-280">API de serialización de uso poco frecuente:</span><span class="sxs-lookup"><span data-stu-id="162f0-280">Rarely used marshaling APIs:</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 <span data-ttu-id="162f0-281">**Compatibilidad con la invocación de plataforma y la interoperabilidad COM**</span><span class="sxs-lookup"><span data-stu-id="162f0-281">**Platform invoke and COM interop compatibility**</span></span>

 <span data-ttu-id="162f0-282">La mayoría de los escenarios de invocación de plataforma e interoperabilidad COM todavía se admiten en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-282">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="162f0-283">En particular, se admite toda la interoperabilidad con las API de Windows en tiempo de ejecución (WinRT) y todo el cálculo de referencias necesarias para Windows en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="162f0-283">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="162f0-284">Esto incluye compatibilidad de cálculo de referencias para:</span><span class="sxs-lookup"><span data-stu-id="162f0-284">This includes marshaling support for:</span></span>

- <span data-ttu-id="162f0-285">Matrices (incluido <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="162f0-285">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>

- `BStr`

- <span data-ttu-id="162f0-286">Delegados</span><span class="sxs-lookup"><span data-stu-id="162f0-286">Delegates</span></span>

- <span data-ttu-id="162f0-287">Cadenas (Unicode, ANSI y HSTRING)</span><span class="sxs-lookup"><span data-stu-id="162f0-287">Strings (Unicode, ANSI, and HSTRING)</span></span>

- <span data-ttu-id="162f0-288">Structs (`byref` y `byval`)</span><span class="sxs-lookup"><span data-stu-id="162f0-288">Structs (`byref` and `byval`)</span></span>

- <span data-ttu-id="162f0-289">Uniones</span><span class="sxs-lookup"><span data-stu-id="162f0-289">Unions</span></span>

- <span data-ttu-id="162f0-290">Identificadores de Win32</span><span class="sxs-lookup"><span data-stu-id="162f0-290">Win32 handles</span></span>

- <span data-ttu-id="162f0-291">Todas las construcciones de WinRT</span><span class="sxs-lookup"><span data-stu-id="162f0-291">All WinRT constructs</span></span>

- <span data-ttu-id="162f0-292">Compatibilidad parcial para calcular referencias de tipos de variante.</span><span class="sxs-lookup"><span data-stu-id="162f0-292">Partial support for marshaling variant types.</span></span> <span data-ttu-id="162f0-293">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="162f0-293">The following are supported:</span></span>

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [<span data-ttu-id="162f0-294">IUnknown</span><span class="sxs-lookup"><span data-stu-id="162f0-294">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

<span data-ttu-id="162f0-295">Sin embargo, .NET Native no admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="162f0-295">However, .NET Native doesn't support the following:</span></span>

- <span data-ttu-id="162f0-296">Uso de eventos COM clásicos</span><span class="sxs-lookup"><span data-stu-id="162f0-296">Using classic COM events</span></span>

- <span data-ttu-id="162f0-297">Implementación de la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> en un tipo administrado</span><span class="sxs-lookup"><span data-stu-id="162f0-297">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>

- <span data-ttu-id="162f0-298">Implementación de la interfaz [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) en un tipo administrado a través del atributo <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="162f0-298">Implementing the [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="162f0-299">Sin embargo, no puede llamar a objetos COM a través de `IDispatch` y el objeto administrado no puede implementar `IDispatch` .</span><span class="sxs-lookup"><span data-stu-id="162f0-299">However, you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>

<span data-ttu-id="162f0-300">No se admite el uso de la reflexión para invocar un método de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="162f0-300">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="162f0-301">Puede evitar esta limitación si encapsula la llamada de método en otro método y utiliza la reflexión para llamar en su lugar al contenedor.</span><span class="sxs-lookup"><span data-stu-id="162f0-301">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="162f0-302">Otras diferencias de las API de .NET para aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="162f0-302">Other differences from .NET APIs for Windows Store apps</span></span>

<span data-ttu-id="162f0-303">En esta sección se enumeran las API restantes que no se admiten en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-303">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="162f0-304">El conjunto más grande de las API no compatibles son las API de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="162f0-304">The largest set of the unsupported APIs is the Windows Communication Foundation (WCF) APIs.</span></span>

<span data-ttu-id="162f0-305">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="162f0-305">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>

<span data-ttu-id="162f0-306">Los tipos de los <xref:System.ComponentModel.DataAnnotations> <xref:System.ComponentModel.DataAnnotations.Schema> espacios de nombres y no se admiten en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-306">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="162f0-307">Entre ellos se incluyen los siguientes tipos que están presentes en .NET para aplicaciones de la tienda Windows para Windows 8:</span><span class="sxs-lookup"><span data-stu-id="162f0-307">These include the following types that are present in .NET for Windows Store apps for Windows 8:</span></span>

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 <span data-ttu-id="162f0-308">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="162f0-308">**Visual Basic**</span></span>

<span data-ttu-id="162f0-309">Visual Basic no se admite actualmente en .NET Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-309">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="162f0-310">Los siguientes tipos de los <xref:Microsoft.VisualBasic> <xref:Microsoft.VisualBasic.CompilerServices> espacios de nombres y no están disponibles en .net Native:</span><span class="sxs-lookup"><span data-stu-id="162f0-310">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

<span data-ttu-id="162f0-311">**Contexto de reflexión (espacio de nombres System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="162f0-311">**Reflection Context (System.Reflection.Context namespace)**</span></span>

<span data-ttu-id="162f0-312">La <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> clase no se admite en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-312">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>

<span data-ttu-id="162f0-313">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="162f0-313">**RTC (System.Net.Http.Rtc)**</span></span>

<span data-ttu-id="162f0-314">La `System.Net.Http.RtcRequestFactory` clase no se admite en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-314">The `System.Net.Http.RtcRequestFactory` class isn't supported in .NET Native.</span></span>

<span data-ttu-id="162f0-315">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="162f0-315">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>

<span data-ttu-id="162f0-316">Los tipos de los [espacios de nombres System. ServiceModel. \*](xref:System.ServiceModel) no se admiten en .net Native.</span><span class="sxs-lookup"><span data-stu-id="162f0-316">The types in the [System.ServiceModel.\* namespaces](xref:System.ServiceModel) aren't supported in .NET Native.</span></span> <span data-ttu-id="162f0-317">Entre ellos se incluyen los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="162f0-317">These include the following types:</span></span>

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a><span data-ttu-id="162f0-318">Diferencias en los serializadores</span><span class="sxs-lookup"><span data-stu-id="162f0-318">Differences in serializers</span></span>

<span data-ttu-id="162f0-319">Las siguientes diferencias conciernen a la serialización y deserialización con las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="162f0-319">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>

- <span data-ttu-id="162f0-320">En .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no se puede serializar o deserializar una clase derivada que tiene un miembro de clase base cuyo tipo no es un tipo de serialización raíz.</span><span class="sxs-lookup"><span data-stu-id="162f0-320">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="162f0-321">Por ejemplo, en el siguiente código, si se intenta serializar o deserializar `Y` , se genera un error:</span><span class="sxs-lookup"><span data-stu-id="162f0-321">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  <span data-ttu-id="162f0-322">El tipo `InnerType` es desconocido para el serializador, dado que los miembros de la clase base no se recorren durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="162f0-322">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>

- <span data-ttu-id="162f0-323"><xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no pueden serializar una clase o estructura que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="162f0-323"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="162f0-324">Por ejemplo, los siguientes tipos no se producen error al serializar o deserializar:</span><span class="sxs-lookup"><span data-stu-id="162f0-324">For example, the following types fail to serialize or deserialize:</span></span>

- <span data-ttu-id="162f0-325"><xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar el valor del objeto siguiente, puesto que desconoce el tipo exacto del objeto que se va a serializar:</span><span class="sxs-lookup"><span data-stu-id="162f0-325"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>

- <span data-ttu-id="162f0-326"><xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar o deserializar si el tipo del objeto serializado es <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="162f0-326"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>

- <span data-ttu-id="162f0-327">Todos los serializadores (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer>) producen error al general código de serialización para el tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o para un tipo que contenga <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="162f0-327">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="162f0-328">En su lugar, muestran errores en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="162f0-328">They display build-time errors instead.</span></span>

- <span data-ttu-id="162f0-329">No se garantiza que los siguientes constructores de los tipos de serialización funcionen del modo esperado:</span><span class="sxs-lookup"><span data-stu-id="162f0-329">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <span data-ttu-id="162f0-330"><xref:System.Xml.Serialization.XmlSerializer> produce un error al general código para un tipo que tiene métodos con cualquiera de los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="162f0-330"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <span data-ttu-id="162f0-331"><xref:System.Xml.Serialization.XmlSerializer> no aceptan la interfaz de serialización personalizada <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="162f0-331"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="162f0-332">Si tiene una clase que implementa esta interfaz, <xref:System.Xml.Serialization.XmlSerializer> considera el tipo como un tipo de objeto CLR estándar (POCO) y solo serializa sus propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="162f0-332">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>

- <span data-ttu-id="162f0-333">Serializar un objeto sin formato <xref:System.Exception> no funciona bien con <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="162f0-333">Serializing a plain <xref:System.Exception> object doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<a name="VS"></a>

## <a name="visual-studio-differences"></a><span data-ttu-id="162f0-334">Diferencias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="162f0-334">Visual Studio differences</span></span>

<span data-ttu-id="162f0-335">**Excepciones y depuración**</span><span class="sxs-lookup"><span data-stu-id="162f0-335">**Exceptions and debugging**</span></span>

<span data-ttu-id="162f0-336">Cuando se ejecutan aplicaciones compiladas mediante .NET Native en el depurador, las excepciones de primera oportunidad están habilitadas para los siguientes tipos de excepción:</span><span class="sxs-lookup"><span data-stu-id="162f0-336">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

<span data-ttu-id="162f0-337">**Compilar aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="162f0-337">**Building apps**</span></span>

<span data-ttu-id="162f0-338">Use las herramientas de compilación x86 que se utilizan de manera predeterminada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="162f0-338">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="162f0-339">No recomendamos el uso de las herramientas de MSBuild AMD64, ya que podrían crear problemas de compilación. Estas herramientas se encuentran en C:\Archivos de programa (x86)\MSBuild\12.0\bin\amd64.</span><span class="sxs-lookup"><span data-stu-id="162f0-339">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>

<span data-ttu-id="162f0-340">**Generadores de perfiles**</span><span class="sxs-lookup"><span data-stu-id="162f0-340">**Profilers**</span></span>

- <span data-ttu-id="162f0-341">El generador de perfiles de CPU de Visual Studio CPU y el generador de perfiles de memoria de XAML no muestran correctamente Just-My-Code (solo mi código).</span><span class="sxs-lookup"><span data-stu-id="162f0-341">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>

- <span data-ttu-id="162f0-342">El generador de perfiles de memoria de XAML no muestra con precisión los datos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="162f0-342">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>

- <span data-ttu-id="162f0-343">El generador de perfiles de CPU no identifica correctamente los módulos y muestra nombres de función prefijados.</span><span class="sxs-lookup"><span data-stu-id="162f0-343">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>

<span data-ttu-id="162f0-344">**Proyectos de biblioteca de prueba unitaria**</span><span class="sxs-lookup"><span data-stu-id="162f0-344">**Unit Test Library projects**</span></span>

<span data-ttu-id="162f0-345">No se admite la habilitación de .NET Native en una biblioteca de pruebas unitarias para un proyecto de aplicaciones de la tienda Windows y hace que el proyecto no se compile.</span><span class="sxs-lookup"><span data-stu-id="162f0-345">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>

## <a name="see-also"></a><span data-ttu-id="162f0-346">Vea también</span><span class="sxs-lookup"><span data-stu-id="162f0-346">See also</span></span>

- [<span data-ttu-id="162f0-347">Introducción</span><span class="sxs-lookup"><span data-stu-id="162f0-347">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="162f0-348">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="162f0-348">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- <span data-ttu-id="162f0-349">[Información general de .NET para aplicaciones de la tienda Windows](/previous-versions/windows/apps/br230302(v=vs.140))</span><span class="sxs-lookup"><span data-stu-id="162f0-349">[.NET For Windows Store apps overview](/previous-versions/windows/apps/br230302(v=vs.140))</span></span>
- [<span data-ttu-id="162f0-350">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="162f0-350">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
