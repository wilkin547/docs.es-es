---
title: MDA de openGenericCERCall
description: Vea el Asistente para la depuración administrada openGenericCERCall, que puede activarse si el código CER no se ejecuta cuando se anula un subproceso o cuando se descarga un dominio de aplicación.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: 4df33b0cdf9759edec47f02b3feb671d03284ec8
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803942"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="6d496-103">MDA de openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="6d496-103">openGenericCERCall MDA</span></span>

<span data-ttu-id="6d496-104">El asistente para la depuración administrada `openGenericCERCall` se activa para advertir que se está procesando un gráfico de región de ejecución restringida (CER) con variables de tipo genérico en el método raíz en la compilación JIT o en tiempo de generación de imágenes nativas y al menos una de las variables de tipo genérico es un tipo de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="6d496-104">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="6d496-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6d496-105">Symptoms</span></span>

<span data-ttu-id="6d496-106">El código de la CER no se ejecuta cuando se anula un subproceso o se descarga un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d496-106">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="6d496-107">Causa</span><span class="sxs-lookup"><span data-stu-id="6d496-107">Cause</span></span>

<span data-ttu-id="6d496-108">En tiempo de compilación JIT, una instancia que contiene un tipo de referencia de objeto solo es representativa porque el código resultante es compartido, y cada una de las variables de tipo de referencia de objeto puede ser cualquier tipo de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="6d496-108">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="6d496-109">Esto puede impedir la preparación de algunos recursos de tiempo de ejecución antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="6d496-109">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="6d496-110">En concreto, los métodos con variables de tipo genérico pueden asignar lentamente recursos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6d496-110">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="6d496-111">Estas se denominan entradas de diccionario genéricas.</span><span class="sxs-lookup"><span data-stu-id="6d496-111">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="6d496-112">Por ejemplo, para la instrucción, `List<T> list = new List<T>();` donde `T` es una variable de tipo genérico, el tiempo de ejecución debe buscarse y posiblemente crear la creación de instancias exacta en tiempo de ejecución, por ejemplo,, `List<Object>, List<String>` y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6d496-112">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="6d496-113">Esto puede producir un error por diferentes motivos que se escapan al control del desarrollador, como memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="6d496-113">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="6d496-114">Solo se debería activar este MDA en tiempo de compilación JIT, no cuando hay una creación de instancias exactas.</span><span class="sxs-lookup"><span data-stu-id="6d496-114">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="6d496-115">Cuando se activa este MDA, los posibles síntomas son que las CER no están habilitadas para la creación de instancias incorrectas.</span><span class="sxs-lookup"><span data-stu-id="6d496-115">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="6d496-116">De hecho, el tiempo de ejecución no ha intentado implementar una CER en las circunstancias que provocaron que se activara el MDA.</span><span class="sxs-lookup"><span data-stu-id="6d496-116">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="6d496-117">Por tanto, si el desarrollador usa una instancia compartida de la CER, no se detectan los errores de compilación de JIT, los errores de carga de tipos genéricos o las anulaciones de subprocesos dentro de la CER deseada.</span><span class="sxs-lookup"><span data-stu-id="6d496-117">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="6d496-118">Resolución</span><span class="sxs-lookup"><span data-stu-id="6d496-118">Resolution</span></span>

<span data-ttu-id="6d496-119">No use variables de tipo genérico que son del tipo de referencia de objeto para los métodos que puede contener una CER.</span><span class="sxs-lookup"><span data-stu-id="6d496-119">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="6d496-120">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="6d496-120">Effect on the Runtime</span></span>

<span data-ttu-id="6d496-121">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="6d496-121">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="6d496-122">Output</span><span class="sxs-lookup"><span data-stu-id="6d496-122">Output</span></span>

<span data-ttu-id="6d496-123">A continuación se muestra un ejemplo de la salida de este MDA:</span><span class="sxs-lookup"><span data-stu-id="6d496-123">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="6d496-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="6d496-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="6d496-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d496-125">Example</span></span>

<span data-ttu-id="6d496-126">No se ejecuta el código de la CER.</span><span class="sxs-lookup"><span data-stu-id="6d496-126">The CER code is not executed.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6d496-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d496-127">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="6d496-128">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="6d496-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
