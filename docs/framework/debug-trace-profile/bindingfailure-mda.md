---
title: MDA de bindingFailure
description: Obtenga información sobre el Asistente para la depuración administrada (MDA) de bindingFailure, que se activa cuando un ensamblado no se carga en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
ms.openlocfilehash: 98c7947c7e5d2a1f0af8c26744d3b292ed8cb4c4
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415633"
---
# <a name="bindingfailure-mda"></a><span data-ttu-id="e67c3-103">MDA de bindingFailure</span><span class="sxs-lookup"><span data-stu-id="e67c3-103">bindingFailure MDA</span></span>

<span data-ttu-id="e67c3-104">El asistente para la depuración administrada (MDA) `bindingFailure` se activa cuando no se puede cargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-104">The `bindingFailure` managed debugging assistant (MDA) is activated when an assembly fails to load.</span></span>

## <a name="symptoms"></a><span data-ttu-id="e67c3-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e67c3-105">Symptoms</span></span>

<span data-ttu-id="e67c3-106">El código ha intentado cargar un ensamblado con una referencia estática o uno de los métodos del cargador, como <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e67c3-106">Code has attempted to load an assembly using a static reference or one of the loader methods, such as <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e67c3-107">No se ha cargado el ensamblado y se ha producido una excepción <xref:System.IO.FileNotFoundException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="e67c3-107">The assembly is not loaded and a <xref:System.IO.FileNotFoundException> or <xref:System.IO.FileLoadException> exception is thrown.</span></span>

## <a name="cause"></a><span data-ttu-id="e67c3-108">Causa</span><span class="sxs-lookup"><span data-stu-id="e67c3-108">Cause</span></span>

<span data-ttu-id="e67c3-109">Si el tiempo de ejecución no puede cargar un ensamblado, se produce un error de enlace.</span><span class="sxs-lookup"><span data-stu-id="e67c3-109">A binding failure occurs when the runtime is unable to load an assembly.</span></span> <span data-ttu-id="e67c3-110">Un error de enlace podría deberse a una de las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="e67c3-110">A binding failure might be the result of one of the following situations:</span></span>

- <span data-ttu-id="e67c3-111">Common Language Runtime (CLR) no encuentra el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-111">The common language runtime (CLR) cannot find the requested assembly.</span></span> <span data-ttu-id="e67c3-112">Hay muchas razones por las que esto puede suceder, por ejemplo, que el ensamblado no esté instalado o que la aplicación no esté configurada correctamente para encontrar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-112">There are many reasons this can occur, such as the assembly not being installed or the application not being correctly configured to find the assembly.</span></span>

- <span data-ttu-id="e67c3-113">Un problema habitual es cuando se pasa un tipo a otro dominio de aplicación, lo que exige que CLR cargue el ensamblado que contiene ese tipo en el otro dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e67c3-113">A common problem scenario is passing a type to another application domain, which requires the CLR to load the assembly containing that type in the other application domain.</span></span> <span data-ttu-id="e67c3-114">Es posible que el tiempo de ejecución no pueda cargar el ensamblado si el otro dominio de aplicación está configurado de forma diferente al dominio de aplicación original.</span><span class="sxs-lookup"><span data-stu-id="e67c3-114">It may not be possible for the runtime to load the assembly if the other application domain is configured differently from the original application domain.</span></span> <span data-ttu-id="e67c3-115">Por ejemplo, los dos dominios de aplicación pueden tener diferentes valores de propiedad <xref:System.AppDomain.BaseDirectory%2A>.</span><span class="sxs-lookup"><span data-stu-id="e67c3-115">For example, the two application domains might have different <xref:System.AppDomain.BaseDirectory%2A> property values.</span></span>

- <span data-ttu-id="e67c3-116">El ensamblado solicitado está dañado o no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-116">The requested assembly is corrupted or is not an assembly.</span></span>

- <span data-ttu-id="e67c3-117">El código que intenta cargar el ensamblado no tiene los permisos de seguridad de acceso de código correctos para cargar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e67c3-117">The code attempting to load the assembly does not have the correct code access security permissions to load assemblies.</span></span>

- <span data-ttu-id="e67c3-118">Las credenciales de usuario no proporcionan los permisos necesarios para leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="e67c3-118">The user credentials do not provide the required permissions to read the file.</span></span>

## <a name="resolution"></a><span data-ttu-id="e67c3-119">Solución</span><span class="sxs-lookup"><span data-stu-id="e67c3-119">Resolution</span></span>

<span data-ttu-id="e67c3-120">El primer paso es determinar por qué CLR no ha podido enlazar con el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-120">The first step is to determine why the CLR could not bind to the requested assembly.</span></span> <span data-ttu-id="e67c3-121">Hay muchas razones por las que el tiempo de ejecución puede no haber encontrado o cargado el ensamblado solicitado, como los escenarios de la sección Causa.</span><span class="sxs-lookup"><span data-stu-id="e67c3-121">There are many reasons why the runtime might not have found or been able load the requested assembly, such as the scenarios listed in the Cause section.</span></span> <span data-ttu-id="e67c3-122">Para eliminar la causa del error de enlace, se recomiendan las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e67c3-122">The following actions are recommended to eliminate the cause of the binding failure:</span></span>

- <span data-ttu-id="e67c3-123">Determine la causa con los datos proporcionados por el MDA `bindingFailure`:</span><span class="sxs-lookup"><span data-stu-id="e67c3-123">Determine the cause by using the data provided by the `bindingFailure` MDA:</span></span>

  - <span data-ttu-id="e67c3-124">Ejecute [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) para leer los registros de errores generados por el enlazador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e67c3-124">Run the [Fuslogvw.exe (Assembly Binding Log Viewer)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to read the error logs produced by the assembly binder.</span></span>

  - <span data-ttu-id="e67c3-125">Determine si el ensamblado se encuentra en la ubicación solicitada.</span><span class="sxs-lookup"><span data-stu-id="e67c3-125">Determine if the assembly is at the location requested.</span></span> <span data-ttu-id="e67c3-126">En el caso de los métodos <xref:System.Reflection.Assembly.LoadFrom%2A> y <xref:System.Reflection.Assembly.LoadFile%2A>, la ubicación solicitada se puede determinar fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e67c3-126">In the case of the <xref:System.Reflection.Assembly.LoadFrom%2A> and <xref:System.Reflection.Assembly.LoadFile%2A> methods, the requested location can be easily determined.</span></span> <span data-ttu-id="e67c3-127">En el caso del método <xref:System.Reflection.Assembly.Load%2A>, que enlaza con la identidad del ensamblado, debe buscar ensamblados que coincidan con esa identidad en la ruta de acceso de sondeo de la propiedad <xref:System.AppDomain.BaseDirectory%2A> del dominio de aplicación y la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e67c3-127">In the case of the <xref:System.Reflection.Assembly.Load%2A> method, which binds using the assembly identity, you must look for assemblies that match that identity in the application domain's <xref:System.AppDomain.BaseDirectory%2A> property probe path and the global assembly cache.</span></span>

- <span data-ttu-id="e67c3-128">Resuelva la causa en función de la determinación anterior.</span><span class="sxs-lookup"><span data-stu-id="e67c3-128">Resolve the cause based on the preceding determination.</span></span> <span data-ttu-id="e67c3-129">Las opciones de resolución posibles son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e67c3-129">Possible resolution options are the following:</span></span>

  - <span data-ttu-id="e67c3-130">Instale el ensamblado solicitado en la caché global de ensamblados y llame al método</span><span class="sxs-lookup"><span data-stu-id="e67c3-130">Install the requested assembly in the global assembly cache and call the.</span></span> <span data-ttu-id="e67c3-131"><xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por identidad.</span><span class="sxs-lookup"><span data-stu-id="e67c3-131"><xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>

  - <span data-ttu-id="e67c3-132">Copie el ensamblado solicitado en el directorio de la aplicación y llame al método <xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por identidad.</span><span class="sxs-lookup"><span data-stu-id="e67c3-132">Copy the requested assembly into the application directory and call the <xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>

  - <span data-ttu-id="e67c3-133">Vuelva a configurar el dominio de aplicación en el que se produjo el error de enlace para que incluya la ruta de acceso del ensamblado al cambiar la propiedad <xref:System.AppDomain.BaseDirectory%2A> o agregar rutas de acceso de sondeo privadas.</span><span class="sxs-lookup"><span data-stu-id="e67c3-133">Reconfigure the application domain in which the binding failure occurred to include the assembly path by either changing the <xref:System.AppDomain.BaseDirectory%2A> property or adding private probing paths.</span></span>

  - <span data-ttu-id="e67c3-134">Cambie la lista de control de acceso del archivo para permitir que el usuario que ha iniciado sesión lea el archivo.</span><span class="sxs-lookup"><span data-stu-id="e67c3-134">Change the access control list for the file to allow the logged-on user to read the file.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="e67c3-135">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="e67c3-135">Effect on the Runtime</span></span>

<span data-ttu-id="e67c3-136">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="e67c3-136">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="e67c3-137">Solo notifica datos sobre errores de enlace.</span><span class="sxs-lookup"><span data-stu-id="e67c3-137">It only reports data about binding failures.</span></span>

## <a name="output"></a><span data-ttu-id="e67c3-138">Output</span><span class="sxs-lookup"><span data-stu-id="e67c3-138">Output</span></span>

<span data-ttu-id="e67c3-139">El MDA notifica qué ensamblado no se ha podido cargar, incluida la ruta de acceso solicitada o el nombre para mostrar, el contexto de enlace, el dominio de aplicación en el que se ha solicitado la carga y el motivo del error.</span><span class="sxs-lookup"><span data-stu-id="e67c3-139">The MDA reports the assembly that failed to load, including the requested path and/or display name, the binding context, the application domain in which the load was requested, and the reason for the failure.</span></span>

<span data-ttu-id="e67c3-140">El nombre para mostrar o la ruta de acceso solicitada pueden estar en blanco si estos datos no estaban a disposición de CLR.</span><span class="sxs-lookup"><span data-stu-id="e67c3-140">The display name or requested path may be blank if that data was not available to the CLR.</span></span> <span data-ttu-id="e67c3-141">Si la llamada errónea era al método <xref:System.Reflection.Assembly.Load%2A>, es probable que el tiempo de ejecución no pudiera determinar el nombre para mostrar del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e67c3-141">If the call that failed was to the <xref:System.Reflection.Assembly.Load%2A> method, it is likely the runtime could not determine the display name for the assembly.</span></span>

## <a name="configuration"></a><span data-ttu-id="e67c3-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="e67c3-142">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <bindingFailure />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="e67c3-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e67c3-143">Example</span></span>

<span data-ttu-id="e67c3-144">En el ejemplo de código siguiente se muestra una situación que puede activar este MDA:</span><span class="sxs-lookup"><span data-stu-id="e67c3-144">The following code example demonstrates a situation that can activate this MDA:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Reflection;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // This call attempts to load a nonexistent assembly.
            // The call will throw a System.IO.FileNotFound exception
            // and cause the activation of the bindingFailure MDA
            // if it is registered.
            Assembly.Load("NonExistentAssembly");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e67c3-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e67c3-145">See also</span></span>

- [<span data-ttu-id="e67c3-146">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="e67c3-146">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
