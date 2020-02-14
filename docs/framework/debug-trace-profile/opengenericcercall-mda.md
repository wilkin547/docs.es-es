---
title: MDA de openGenericCERCall
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
ms.openlocfilehash: de1735103314dfedbabe27623f579ce2c1e728af
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217276"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="d1f27-102">MDA de openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="d1f27-102">openGenericCERCall MDA</span></span>

<span data-ttu-id="d1f27-103">El asistente para la depuración administrada `openGenericCERCall` se activa para advertir que se está procesando un gráfico de región de ejecución restringida (CER) con variables de tipo genérico en el método raíz en la compilación JIT o en tiempo de generación de imágenes nativas y al menos una de las variables de tipo genérico es un tipo de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="d1f27-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="d1f27-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d1f27-104">Symptoms</span></span>

<span data-ttu-id="d1f27-105">El código de la CER no se ejecuta cuando se anula un subproceso o se descarga un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d1f27-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="d1f27-106">Causa</span><span class="sxs-lookup"><span data-stu-id="d1f27-106">Cause</span></span>

<span data-ttu-id="d1f27-107">En tiempo de compilación JIT, una instancia que contiene un tipo de referencia de objeto solo es representativa porque el código resultante es compartido, y cada una de las variables de tipo de referencia de objeto puede ser cualquier tipo de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="d1f27-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="d1f27-108">Esto puede impedir la preparación de algunos recursos de tiempo de ejecución antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d1f27-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="d1f27-109">En concreto, los métodos con variables de tipo genérico pueden asignar lentamente recursos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d1f27-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="d1f27-110">Estas se denominan entradas de diccionario genéricas.</span><span class="sxs-lookup"><span data-stu-id="d1f27-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="d1f27-111">Por ejemplo, para la instrucción `List<T> list = new List<T>();` donde `T` es una variable de tipo genérico, el tiempo de ejecución debe buscar y posiblemente crear la creación de instancias exacta en tiempo de ejecución, por ejemplo, `List<Object>, List<String>`, etc.</span><span class="sxs-lookup"><span data-stu-id="d1f27-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="d1f27-112">Esto puede producir un error por diferentes motivos que se escapan al control del desarrollador, como memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="d1f27-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="d1f27-113">Solo se debería activar este MDA en tiempo de compilación JIT, no cuando hay una creación de instancias exactas.</span><span class="sxs-lookup"><span data-stu-id="d1f27-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="d1f27-114">Cuando se activa este MDA, los posibles síntomas son que las CER no están habilitadas para la creación de instancias incorrectas.</span><span class="sxs-lookup"><span data-stu-id="d1f27-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="d1f27-115">De hecho, el tiempo de ejecución no ha intentado implementar una CER en las circunstancias que provocaron que se activara el MDA.</span><span class="sxs-lookup"><span data-stu-id="d1f27-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="d1f27-116">Por tanto, si el desarrollador usa una instancia compartida de la CER, no se detectan los errores de compilación de JIT, los errores de carga de tipos genéricos o las anulaciones de subprocesos dentro de la CER deseada.</span><span class="sxs-lookup"><span data-stu-id="d1f27-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="d1f27-117">Solución</span><span class="sxs-lookup"><span data-stu-id="d1f27-117">Resolution</span></span>

<span data-ttu-id="d1f27-118">No use variables de tipo genérico que son del tipo de referencia de objeto para los métodos que puede contener una CER.</span><span class="sxs-lookup"><span data-stu-id="d1f27-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="d1f27-119">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="d1f27-119">Effect on the Runtime</span></span>

<span data-ttu-id="d1f27-120">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="d1f27-120">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="d1f27-121">Output</span><span class="sxs-lookup"><span data-stu-id="d1f27-121">Output</span></span>

<span data-ttu-id="d1f27-122">A continuación se muestra un ejemplo de la salida de este MDA:</span><span class="sxs-lookup"><span data-stu-id="d1f27-122">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution. 
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="d1f27-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="d1f27-123">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="d1f27-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1f27-124">Example</span></span>

<span data-ttu-id="d1f27-125">No se ejecuta el código de la CER.</span><span class="sxs-lookup"><span data-stu-id="d1f27-125">The CER code is not executed.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d1f27-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1f27-126">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="d1f27-127">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="d1f27-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
