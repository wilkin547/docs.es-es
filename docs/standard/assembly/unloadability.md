---
title: Uso y depuración de la descargabilidad de ensamblado en .NET Core
description: Obtenga información sobre cómo usar AssemblyLoadContext recopilable para cargar y descargar ensamblados administrados y cómo depurar los problemas que impiden que la descarga se realice correctamente.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 52cd864393342e2bc31f872b9d09cb484c2c8463
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972496"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="c9613-103">Uso y depuración de la descargabilidad de ensamblado en .NET Core</span><span class="sxs-lookup"><span data-stu-id="c9613-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="c9613-104">A partir de .NET Core 3.0, se admite la capacidad de cargar y posteriormente descargar un conjunto de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c9613-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="c9613-105">Para este fin, en .NET Framework se usaban dominios de aplicación personalizados, pero .NET Core solo admite un dominio de aplicación predeterminado único.</span><span class="sxs-lookup"><span data-stu-id="c9613-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="c9613-106">.NET Core 3.0 y versiones posteriores admiten la descargabilidad a través de <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="c9613-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="c9613-107">Puede cargar un conjunto de ensamblados en un `AssemblyLoadContext` recopilable, ejecutar métodos en ellos o simplemente inspeccionarlos mediante reflexión y, por último, descargar el `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="c9613-108">Esa acción descarga los ensamblados cargados en ese `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="c9613-109">Cabe destacar una diferencia entre la descarga mediante `AssemblyLoadContext` y mediante AppDomains.</span><span class="sxs-lookup"><span data-stu-id="c9613-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="c9613-110">Con AppDomains, se fuerza la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="c9613-111">En el momento de la descarga, se anulan todos los subprocesos que se ejecutan en la instancia de AppDomain de destino, se destruyen los objetos COM administrados creados en la AppDomain de destino, etc. Con `AssemblyLoadContext`, la descarga es “cooperativa”.</span><span class="sxs-lookup"><span data-stu-id="c9613-111">At unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative."</span></span> <span data-ttu-id="c9613-112">La llamada al método <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> simplemente inicia la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="c9613-113">La descarga finaliza una vez que:</span><span class="sxs-lookup"><span data-stu-id="c9613-113">The unloading finishes after:</span></span>

- <span data-ttu-id="c9613-114">Ningún subproceso tiene métodos de los ensamblados cargados en el `AssemblyLoadContext` en sus pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c9613-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="c9613-115">Ninguno de los elementos siguientes hace referencia a los tipos de los ensamblados cargados en el `AssemblyLoadContext`, a las instancias de esos tipos ni a los ensamblados mismos fuera del `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="c9613-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="c9613-116">Referencias fuera del `AssemblyLoadContext`, excepto las referencias parciales (<xref:System.WeakReference> o <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="c9613-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="c9613-117">Identificadores de GC seguros (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="c9613-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="c9613-118">o <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) desde dentro y fuera del `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="use-collectible-assemblyloadcontext"></a><span data-ttu-id="c9613-119">Uso de un AssemblyLoadContext recopilable</span><span class="sxs-lookup"><span data-stu-id="c9613-119">Use collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c9613-120">En esta sección se incluye un tutorial detallado paso a paso que muestra una manera sencilla de cargar una aplicación de .NET Core en un `AssemblyLoadContext` recopilable, ejecutar su punto de entrada y, luego, descargarlo.</span><span class="sxs-lookup"><span data-stu-id="c9613-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="c9613-121">Puede encontrar un ejemplo completo en [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span><span class="sxs-lookup"><span data-stu-id="c9613-121">You can find a complete sample at [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="c9613-122">Creación de un AssemblyLoadContext recopilable</span><span class="sxs-lookup"><span data-stu-id="c9613-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c9613-123">Debe derivar la clase del <xref:System.Runtime.Loader.AssemblyLoadContext> y sobrecargar su método <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9613-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c9613-124">Ese método resuelve las referencias a todos los ensamblados que son dependencias de los ensamblados cargados en ese `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="c9613-125">El código siguiente es un ejemplo del `AssemblyLoadContext` personalizado más sencillo:</span><span class="sxs-lookup"><span data-stu-id="c9613-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="c9613-126">Como puede ver, el método `Load` devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="c9613-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="c9613-127">Esto significa que todos los ensamblados de dependencias se cargan en el contexto predeterminado y el contexto nuevo solo incluye los ensamblados que se cargaron explícitamente en él.</span><span class="sxs-lookup"><span data-stu-id="c9613-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="c9613-128">Si quiere cargar algunas o todas las dependencias también en el `AssemblyLoadContext`, puede usar `AssemblyDependencyResolver` en el método `Load`.</span><span class="sxs-lookup"><span data-stu-id="c9613-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="c9613-129">`AssemblyDependencyResolver` resuelve los nombres de ensamblado en rutas de acceso absoluto a archivos de ensamblado con el archivo *.deps.json* contenido en el directorio del ensamblado principal cargado en el contexto y mediante archivos de ensamblado en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="c9613-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="c9613-130">Uso de un AssemblyLoadContext recopilable personalizado</span><span class="sxs-lookup"><span data-stu-id="c9613-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c9613-131">En esta sección se presupone que se usa la versión más sencilla del `TestAssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="c9613-132">Puede crear una instancia del `AssemblyLoadContext` personalizado y cargar en él un ensamblado como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c9613-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="c9613-133">Para cada uno de los ensamblados a los que hace referencia el ensamblado cargado, se llama al método `TestAssemblyLoadContext.Load` para que el `TestAssemblyLoadContext` pueda decidir desde dónde obtener el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9613-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="c9613-134">En nuestro caso, devuelve `null` para indicar que se debe cargar en el contexto predeterminado desde las ubicaciones que el runtime usa para cargar los ensamblados de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c9613-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="c9613-135">Ahora que se cargó un ensamblado, puede ejecutar un método desde él.</span><span class="sxs-lookup"><span data-stu-id="c9613-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="c9613-136">Ejecute el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="c9613-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="c9613-137">Una vez que el método `Main` devuelve algún resultado, puede iniciar la descarga ya sea llamando al método `Unload` en el `AssemblyLoadContext` personalizado o deshaciéndose de la referencia que hace al `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="c9613-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="c9613-138">Esto es suficiente para descargar el ensamblado de prueba.</span><span class="sxs-lookup"><span data-stu-id="c9613-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="c9613-139">Para que las referencias de ranura de pila (ya sean variables locales reales o introducidas por JIT) no puedan mantener activos los objetos `TestAssemblyLoadContext`, `Assembly` y `MethodInfo` (el `Assembly.EntryPoint`), pongamos todos los elementos en un método no insertable independiente.</span><span class="sxs-lookup"><span data-stu-id="c9613-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="c9613-140">Eso podría mantener activo al `TestAssemblyLoadContext` e impedir la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="c9613-141">Además, devuelva una referencia parcial al `AssemblyLoadContext` para que pueda usarlo más adelante para detectar la finalización de la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="c9613-142">Ahora puede ejecutar esta función para cargar, ejecutar y descargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9613-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="c9613-143">Sin embargo, la descarga no se completa de inmediato.</span><span class="sxs-lookup"><span data-stu-id="c9613-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="c9613-144">Como se mencionó anteriormente, se basa en el GC para recopilar todos los objetos desde el ensamblado de prueba.</span><span class="sxs-lookup"><span data-stu-id="c9613-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="c9613-145">En muchos casos, no es necesario esperar a que se complete la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="c9613-146">Sin embargo, hay casos en los que resulta útil saber que la descarga se completó.</span><span class="sxs-lookup"><span data-stu-id="c9613-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="c9613-147">Por ejemplo, es posible que quiera eliminar el archivo de ensamblado que se cargó en el `AssemblyLoadContext` personalizado del disco.</span><span class="sxs-lookup"><span data-stu-id="c9613-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="c9613-148">En tal caso, se puede usar el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9613-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="c9613-149">Desencadena un GC y espera a los finalizadores pendientes en un bucle hasta que la referencia parcial al `AssemblyLoadContext` personalizado se establece en `null`, lo que indica que se recopiló el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="c9613-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="c9613-150">Tenga en cuenta que, en la mayoría de los casos, solo se requiere un paso a través del bucle.</span><span class="sxs-lookup"><span data-stu-id="c9613-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="c9613-151">Sin embargo, en casos más complejos en los que los objetos creados por el código que se ejecutan en el `AssemblyLoadContext` tienen finalizadores, es posible que se necesiten más pasos.</span><span class="sxs-lookup"><span data-stu-id="c9613-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="c9613-152">El evento de descarga</span><span class="sxs-lookup"><span data-stu-id="c9613-152">The Unloading event</span></span>

<span data-ttu-id="c9613-153">En algunos casos, puede ser necesario que el código cargado en un `AssemblyLoadContext` personalizado realice una limpieza cuando se inicie la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="c9613-154">Por ejemplo, es posible que tenga que detener subprocesos, limpiar algunos identificadores de GC seguros, etc. En esos casos, se puede usar el evento `Unloading`.</span><span class="sxs-lookup"><span data-stu-id="c9613-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="c9613-155">Es posible enlazar a este evento un controlador que realice la limpieza necesaria.</span><span class="sxs-lookup"><span data-stu-id="c9613-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="c9613-156">Solución de problemas de descargabilidad</span><span class="sxs-lookup"><span data-stu-id="c9613-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="c9613-157">Debido a la naturaleza cooperativa de la descarga, resulta fácil olvidarse de que las referencias mantienen activo el contenido de un `AssemblyLoadContext` recopilable, lo que impide la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="c9613-158">A continuación se muestra un resumen de los objetos (algunos de los cuales no son obvios) que pueden contener las referencias:</span><span class="sxs-lookup"><span data-stu-id="c9613-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="c9613-159">Referencias habituales contenidas desde fuera del `AssemblyLoadContext` recopilable, almacenadas en una ranura de pila o en un registro de procesador (variables locales de método, ya sea creadas explícitamente por el código de usuario o de manera implícita por JIT), una variable estática o un identificador de GC seguro/de anclaje, y que apuntan de manera transitiva a:</span><span class="sxs-lookup"><span data-stu-id="c9613-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="c9613-160">Un ensamblado cargado en el `AssemblyLoadContext` recopilable.</span><span class="sxs-lookup"><span data-stu-id="c9613-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="c9613-161">Un tipo de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9613-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="c9613-162">Una instancia de un tipo de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9613-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="c9613-163">Subprocesos que ejecutan código de un ensamblado cargado en el `AssemblyLoadContext` recopilable.</span><span class="sxs-lookup"><span data-stu-id="c9613-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="c9613-164">Instancias de tipos de `AssemblyLoadContext` no recopilables personalizados que se crearon dentro del `AssemblyLoadContext` recopilable.</span><span class="sxs-lookup"><span data-stu-id="c9613-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="c9613-165">Instancias de <xref:System.Threading.RegisteredWaitHandle> pendientes con devoluciones de llamada establecidas en métodos en el `AssemblyLoadContext` personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9613-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="c9613-166">Sugerencias para encontrar una ranura de pila o registro de procesador como raíz de un objeto:</span><span class="sxs-lookup"><span data-stu-id="c9613-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="c9613-167">Pasar los resultados de una llamada de función directamente a otra función puede crear una raíz incluso si no hay ninguna variable local creada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c9613-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="c9613-168">Si había disponible una referencia a un objeto en cualquier punto de un método, es posible que JIT haya decidido mantener la referencia en una ranura de pila/registro de procesador durante el tiempo que quiera en la función actual.</span><span class="sxs-lookup"><span data-stu-id="c9613-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="c9613-169">Depuración de problemas de descarga</span><span class="sxs-lookup"><span data-stu-id="c9613-169">Debug unloading issues</span></span>

<span data-ttu-id="c9613-170">Depurar los problemas con la descarga puede ser un proceso tedioso.</span><span class="sxs-lookup"><span data-stu-id="c9613-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="c9613-171">Puede haber ocasiones en las que no sepa qué es lo que mantiene activo un `AssemblyLoadContext`, pero se produce un error en la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="c9613-172">La mejor herramienta para ayudarlo con eso es WinDbg (LLDB en Unix) con el complemento SOS.</span><span class="sxs-lookup"><span data-stu-id="c9613-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="c9613-173">Debe buscar qué mantiene activo a un `LoaderAllocator` perteneciente al `AssemblyLoadContext` específico.</span><span class="sxs-lookup"><span data-stu-id="c9613-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="c9613-174">Este complemento permite examinar los objetos del montón de GC, sus jerarquías y raíces.</span><span class="sxs-lookup"><span data-stu-id="c9613-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="c9613-175">Para cargar el complemento en el depurador, escriba el comando siguiente en la línea de comandos del depurador:</span><span class="sxs-lookup"><span data-stu-id="c9613-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="c9613-176">En WinDbg (parece que WinDbg lo hace de manera automática al irrumpir en la aplicación de .NET Core):</span><span class="sxs-lookup"><span data-stu-id="c9613-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="c9613-177">En LLDB:</span><span class="sxs-lookup"><span data-stu-id="c9613-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="c9613-178">Vamos a depurar un programa de ejemplo que tiene problemas con la descarga.</span><span class="sxs-lookup"><span data-stu-id="c9613-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="c9613-179">El código de origen se incluye a continuación.</span><span class="sxs-lookup"><span data-stu-id="c9613-179">Source code is included below.</span></span> <span data-ttu-id="c9613-180">Cuando lo ejecuta en WinDbg, el programa irrumpe en el depurador justo después de intentar comprobar que la descarga se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9613-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="c9613-181">Luego, puede empezar a buscar a los culpables.</span><span class="sxs-lookup"><span data-stu-id="c9613-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="c9613-182">Tenga en cuenta que si realiza la depuración con LLDB en Unix, los comandos de SOS de los ejemplos siguientes no tienen `!` delante de ellos.</span><span class="sxs-lookup"><span data-stu-id="c9613-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="c9613-183">Este comando vuelca todos los objetos con un nombre de tipo que contiene `LoaderAllocator` que se encuentran en el montón de GC.</span><span class="sxs-lookup"><span data-stu-id="c9613-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="c9613-184">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9613-184">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="c9613-185">En la parte "Statistics:" (Estadísticas) que aparece abajo, compruebe el `MT` (`MethodTable`) que pertenece al `System.Reflection.LoaderAllocator`, que es el objeto que nos interesa.</span><span class="sxs-lookup"><span data-stu-id="c9613-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="c9613-186">Luego, en la lista que aparece al principio, busque la entrada con el `MT` que coincide con ese y obtenga la dirección del objeto mismo.</span><span class="sxs-lookup"><span data-stu-id="c9613-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="c9613-187">En nuestro caso, se trata de "000002b78000ce40".</span><span class="sxs-lookup"><span data-stu-id="c9613-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="c9613-188">Ahora que sabemos la dirección del objeto `LoaderAllocator`, podemos usar otro comando para encontrar sus raíces de GC.</span><span class="sxs-lookup"><span data-stu-id="c9613-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="c9613-189">Este comando vuelca la cadena de referencias de objeto que llevan a la instancia `LoaderAllocator`.</span><span class="sxs-lookup"><span data-stu-id="c9613-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="c9613-190">La lista empieza con la raíz, que es la entidad que mantiene activo el `LoaderAllocator` y, por lo tanto, es la parte fundamental del problema que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="c9613-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="c9613-191">La raíz puede ser una ranura de pila, un registro de procesador, un identificador de GC o una variable estática.</span><span class="sxs-lookup"><span data-stu-id="c9613-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="c9613-192">Este es un ejemplo de la salida del comando `gcroot`:</span><span class="sxs-lookup"><span data-stu-id="c9613-192">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="c9613-193">Ahora debe averiguar dónde se encuentra la raíz para poder corregirla.</span><span class="sxs-lookup"><span data-stu-id="c9613-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="c9613-194">El caso más sencillo es cuando la raíz es una ranura de pila o un registro de procesador.</span><span class="sxs-lookup"><span data-stu-id="c9613-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="c9613-195">En ese caso, `gcroot` muestra el nombre de la función cuyo marco contiene la raíz y el subproceso que ejecuta esa función.</span><span class="sxs-lookup"><span data-stu-id="c9613-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="c9613-196">El caso difícil es cuando la raíz es una variable estática o un identificador de GC.</span><span class="sxs-lookup"><span data-stu-id="c9613-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="c9613-197">En el ejemplo anterior, la primera raíz es una variable local de tipo `System.Reflection.RuntimeMethodInfo` almacenada en el marco de la función `example.Program.Main(System.String[])` en la dirección `rbp-20` (`rbp` es el registro de procesador `rbp` y -20 es un desplazamiento hexadecimal a partir de ese registro).</span><span class="sxs-lookup"><span data-stu-id="c9613-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="c9613-198">La segunda raíz es un `GCHandle` normal (seguro) que contiene una referencia a una instancia de la clase `test.Test`.</span><span class="sxs-lookup"><span data-stu-id="c9613-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="c9613-199">La tercera raíz es un `GCHandle` anclado.</span><span class="sxs-lookup"><span data-stu-id="c9613-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="c9613-200">En realidad, se trata de una variable estática.</span><span class="sxs-lookup"><span data-stu-id="c9613-200">This one is actually a static variable.</span></span> <span data-ttu-id="c9613-201">Lamentablemente, no hay forma de saberlo.</span><span class="sxs-lookup"><span data-stu-id="c9613-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="c9613-202">Las variables estáticas para tipos de referencia se almacenan en una matriz de objetos administrada en estructuras internas de runtime.</span><span class="sxs-lookup"><span data-stu-id="c9613-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="c9613-203">Otro caso que puede impedir la descarga de un `AssemblyLoadContext` es cuando un subproceso tiene un marco de un método proveniente de un ensamblado cargado en el `AssemblyLoadContext` en su pila.</span><span class="sxs-lookup"><span data-stu-id="c9613-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="c9613-204">Puede comprobarlo si vuelca las pilas de llamadas administradas de todos los subprocesos:</span><span class="sxs-lookup"><span data-stu-id="c9613-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="c9613-205">El comando siguiente "aplicar a todos los subprocesos el comando `!clrstack`".</span><span class="sxs-lookup"><span data-stu-id="c9613-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="c9613-206">Luego se muestra la salida de ese comando para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9613-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="c9613-207">Lamentablemente, LLDB en Unix no tiene forma de aplicar un comando a todos los subprocesos, por lo que deberá recurrir a cambiar de manera manual los subprocesos y repetir el comando `clrstack`.</span><span class="sxs-lookup"><span data-stu-id="c9613-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="c9613-208">Omita todos los subprocesos en los que el depurador indique "Unable to walk the managed stack" (No se puede recorrer la pila administrada).</span><span class="sxs-lookup"><span data-stu-id="c9613-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

<span data-ttu-id="c9613-209">Como puede ver, el último subproceso tiene `test.Program.ThreadProc()`.</span><span class="sxs-lookup"><span data-stu-id="c9613-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="c9613-210">Esta es una función del ensamblado cargado en el `AssemblyLoadContext`, por lo que mantiene activo al `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c9613-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="c9613-211">Origen de ejemplo con problemas de descargabilidad</span><span class="sxs-lookup"><span data-stu-id="c9613-211">Example source with unloadability issues</span></span>

<span data-ttu-id="c9613-212">El código siguiente se usa en el ejemplo de depuración anterior.</span><span class="sxs-lookup"><span data-stu-id="c9613-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="c9613-213">Programa de prueba principal</span><span class="sxs-lookup"><span data-stu-id="c9613-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="c9613-214">Programa cargado en TestAssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="c9613-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="c9613-215">El código siguiente presenta el *test.dll* que se pasa al método `ExecuteAndUnload` en el programa de prueba principal.</span><span class="sxs-lookup"><span data-stu-id="c9613-215">The following code represents the *test.dll* passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
