---
title: MDA de callbackOnCollectedDelegate
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8441e1b2c623126e844d8a641d7f002aef495e9d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145889"
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="76837-102">MDA de callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="76837-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="76837-103">El Asistente para la depuración administrada (MDA) `callbackOnCollectedDelegate` se activa si se calculan las referencias de un delegado desde código administrado a no administrado como un puntero de función y se coloca una devolución de llamada en dicho puntero después de que el delegado haya sido recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="76837-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="76837-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="76837-104">Symptoms</span></span>  
 <span data-ttu-id="76837-105">Al intentar llamar al código administrado mediante punteros de función obtenidos de delegados administrados, se producen infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="76837-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="76837-106">Estos errores no son errores de Common Language Runtime (CLR) aunque pueden parecerlo porque la infracción de acceso se produce en el código de CLR.</span><span class="sxs-lookup"><span data-stu-id="76837-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="76837-107">El error no es constante; a veces, la llamada al puntero de función se realiza correctamente y otras veces no.</span><span class="sxs-lookup"><span data-stu-id="76837-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="76837-108">El error podría producirse solo en condiciones de mucha carga o después de un número aleatorio de intentos.</span><span class="sxs-lookup"><span data-stu-id="76837-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="76837-109">Motivo</span><span class="sxs-lookup"><span data-stu-id="76837-109">Cause</span></span>  
 <span data-ttu-id="76837-110">El delegado a partir del cual se creó el puntero de función y se expuso al código no administrado se recolectó como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="76837-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="76837-111">Cuando el componente no administrado intenta llamar al puntero de función, genera una infracción de acceso.</span><span class="sxs-lookup"><span data-stu-id="76837-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="76837-112">El error parece aleatorio porque depende de cuándo se produce la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="76837-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="76837-113">Si un delegado es candidato para la recolección, la recolección de elementos no utilizados puede producirse después de la devolución de llamada y la llamada se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="76837-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="76837-114">En otras ocasiones, la recolección de elementos no utilizados se produce antes de la devolución de llamada, la devolución de llamada genera una infracción de acceso y el programa se detiene.</span><span class="sxs-lookup"><span data-stu-id="76837-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="76837-115">La probabilidad del error depende del tiempo entre el cálculo de referencias del delegado y la devolución de llamada en el puntero de función, así como de la frecuencia de las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="76837-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="76837-116">El error será esporádico si el tiempo entre el cálculo de referencias del delegado y la devolución de llamada posterior es breve.</span><span class="sxs-lookup"><span data-stu-id="76837-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="76837-117">Este suele ser el caso cuando el método no administrado que recibe el puntero de función no guarda el puntero de función para su uso posterior y, en su lugar, realiza una devolución de llamada al puntero de función inmediatamente para completar la operación antes de la devolución.</span><span class="sxs-lookup"><span data-stu-id="76837-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="76837-118">De forma similar, se producen más recolecciones de elementos no utilizados cuando un sistema tiene mucha carga, lo que aumenta las probabilidades de que se produzca una recolección de elementos no utilizados antes de la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="76837-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="76837-119">Solución</span><span class="sxs-lookup"><span data-stu-id="76837-119">Resolution</span></span>  
 <span data-ttu-id="76837-120">Una vez calculadas las referencias de un delegado como un puntero de función no administrada, el recolector de elementos no utilizados no puede controlar su vigencia.</span><span class="sxs-lookup"><span data-stu-id="76837-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="76837-121">En su lugar, el código debe mantener una referencia al delegado durante la vigencia del puntero de función no administrado.</span><span class="sxs-lookup"><span data-stu-id="76837-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="76837-122">Pero para poder hacerlo, primero debe identificar qué delegado se ha recolectado.</span><span class="sxs-lookup"><span data-stu-id="76837-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="76837-123">Cuando el MDA se activa, proporciona el nombre del tipo del delegado.</span><span class="sxs-lookup"><span data-stu-id="76837-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="76837-124">Use este nombre para buscar en el código la invocación de plataforma o las firmas COM que pasan el delegado al código no administrado.</span><span class="sxs-lookup"><span data-stu-id="76837-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="76837-125">El delegado que produce el error pasa por uno de estos sitios de llamada.</span><span class="sxs-lookup"><span data-stu-id="76837-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="76837-126">También puede habilitar el MDA `gcUnmanagedToManaged` para aplicar una recolección de elementos no utilizados antes de cada devolución de llamada a CLR.</span><span class="sxs-lookup"><span data-stu-id="76837-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="76837-127">Esto eliminará la incertidumbre provocada por la recolección de elementos no utilizados porque garantiza que siempre se producirá una recolección de elementos no utilizados antes de la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="76837-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="76837-128">Una vez que sepa qué delegado se ha recolectado, cambie el código para mantener una referencia a dicho delegado en la parte administrada durante la vigencia del puntero de función no administrado cuyas referencias se han calculado.</span><span class="sxs-lookup"><span data-stu-id="76837-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="76837-129">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="76837-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="76837-130">Cuando las referencias de los delegados se calculan como punteros de función, CLR asigna un código thunk que realiza la transición de no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="76837-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="76837-131">El código no administrado llama a este código thunk antes de invocar en última instancia al delegado administrado.</span><span class="sxs-lookup"><span data-stu-id="76837-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="76837-132">Si el MDA `callbackOnCollectedDelegate` no está habilitado, el código no administrado de cálculo de referencias se elimina al recopilar el delegado.</span><span class="sxs-lookup"><span data-stu-id="76837-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="76837-133">Si el MDA `callbackOnCollectedDelegate` está habilitado, el código no administrado de cálculo de referencias no se elimina inmediatamente al recopilar el delegado.</span><span class="sxs-lookup"><span data-stu-id="76837-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="76837-134">En su lugar, se mantienen activas las últimas 1.000 instancias de forma predeterminada y se cambian para activar el MDA cuando se le llama.</span><span class="sxs-lookup"><span data-stu-id="76837-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="76837-135">El código thunk se borra después de recopilar 1.001 delegados con referencias calculadas.</span><span class="sxs-lookup"><span data-stu-id="76837-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="76837-136">Salida</span><span class="sxs-lookup"><span data-stu-id="76837-136">Output</span></span>  
 <span data-ttu-id="76837-137">El MDA notifica el nombre de tipo del delegado que se recopiló antes de intentar una devolución de llamada en su puntero de función no administrado.</span><span class="sxs-lookup"><span data-stu-id="76837-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="76837-138">Configuración</span><span class="sxs-lookup"><span data-stu-id="76837-138">Configuration</span></span>  
 <span data-ttu-id="76837-139">El ejemplo siguiente muestra las opciones de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76837-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="76837-140">Establece el número de fragmentos de código thunk que el MDA mantiene activo, hasta 1.500.</span><span class="sxs-lookup"><span data-stu-id="76837-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="76837-141">El valor predeterminado de `listSize` es 1.000, el mínimo es 50 y el máximo es 2.000.</span><span class="sxs-lookup"><span data-stu-id="76837-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="76837-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76837-142">Example</span></span>  
 <span data-ttu-id="76837-143">En el ejemplo siguiente se muestra una situación que puede activar este MDA:</span><span class="sxs-lookup"><span data-stu-id="76837-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```cpp
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}
```

```csharp
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="76837-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="76837-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="76837-145">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="76837-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="76837-146">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="76837-146">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="76837-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="76837-147">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
