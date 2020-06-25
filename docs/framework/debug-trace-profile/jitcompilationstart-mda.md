---
title: Asistente para la depuración administrada de jitCompilationStart (MDA)
description: El Asistente para la depuración administrada (MDA) jitCompilationStart informa cuando el compilador Just-in-Time (JIT) comienza a compilar una función de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: 13e20c1a940b7bfa777245ba35f3cc1b003d15b2
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325532"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="dc48b-103">MDA de jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="dc48b-103">jitCompilationStart MDA</span></span>

<span data-ttu-id="dc48b-104">El Asistente para la depuración administrada (MDA) `jitCompilationStart` se activa para informar del momento en el que el compilador Just-In-Time (JIT) empieza a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="dc48b-104">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dc48b-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="dc48b-105">Symptoms</span></span>  
 <span data-ttu-id="dc48b-106">El tamaño del espacio de trabajo aumenta para un programa que ya está en formato de imagen nativa, porque mscorjit.dll se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dc48b-106">The working set size increases for a program that's already in native image format, because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dc48b-107">Causa</span><span class="sxs-lookup"><span data-stu-id="dc48b-107">Cause</span></span>  
<span data-ttu-id="dc48b-108">No todos los ensamblados de los que depende el programa se han generado en formato nativo o un ensamblado no se ha registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc48b-108">Not all the assemblies the program depends on have been generated into native format, or an assembly is not registered correctly.</span></span>  

## <a name="resolution"></a><span data-ttu-id="dc48b-109">Solución</span><span class="sxs-lookup"><span data-stu-id="dc48b-109">Resolution</span></span>  
 <span data-ttu-id="dc48b-110">La habilitación de este MDA le permite identificar la función que se va a compilar con JIT.</span><span class="sxs-lookup"><span data-stu-id="dc48b-110">Enabling this MDA allows you to identify which function is being JIT-compiled.</span></span> <span data-ttu-id="dc48b-111">Asegúrese de que el ensamblado que contiene la función se genera en formato nativo y se registra correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc48b-111">Make sure that the assembly that contains the function is generated to native format and properly registered.</span></span>
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dc48b-112">Efecto en el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dc48b-112">Effect on the runtime</span></span>  
 <span data-ttu-id="dc48b-113">Este MDA registra un mensaje justo antes de que un método se compile con JIT, por lo que habilitar este MDA tiene un impacto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dc48b-113">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="dc48b-114">Si un método está alineado, este MDA no generará un mensaje independiente.</span><span class="sxs-lookup"><span data-stu-id="dc48b-114">If a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dc48b-115">Resultados</span><span class="sxs-lookup"><span data-stu-id="dc48b-115">Output</span></span>  
 <span data-ttu-id="dc48b-116">En el ejemplo de código siguiente se muestran los resultados del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dc48b-116">The following code sample shows sample output.</span></span> <span data-ttu-id="dc48b-117">En este caso, el resultado muestra que, en la prueba del ensamblado, el método "m" de la clase "ns2.CO" se compiló JIT.</span><span class="sxs-lookup"><span data-stu-id="dc48b-117">In this case, the output shows that, in assembly Test, the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="dc48b-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="dc48b-118">Configuration</span></span>  
 <span data-ttu-id="dc48b-119">En el archivo de configuración siguiente se muestra una variedad de filtros que se pueden emplear para filtrar qué métodos se notifican cuando se compilan con JIT por primera vez.</span><span class="sxs-lookup"><span data-stu-id="dc48b-119">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="dc48b-120">Puede especificar que se notifiquen todos los métodos estableciendo el valor del atributo name en \* .</span><span class="sxs-lookup"><span data-stu-id="dc48b-120">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="dc48b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc48b-121">Example</span></span>  
 <span data-ttu-id="dc48b-122">El ejemplo de código siguiente está pensado para usarse con el archivo de configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="dc48b-122">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc48b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc48b-123">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dc48b-124">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="dc48b-124">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dc48b-125">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="dc48b-125">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
