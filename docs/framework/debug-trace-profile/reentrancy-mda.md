---
title: MDA de reentrada
description: Revise el MDA de reentrada, que se puede activar si el montón del objeto está dañado o se producen otros errores graves al realizar la transición de código nativo a código administrado.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
ms.openlocfilehash: f666e505b8382b0bec8dcfdb34c775850e46c429
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803110"
---
# <a name="reentrancy-mda"></a><span data-ttu-id="d8172-103">MDA de reentrada</span><span class="sxs-lookup"><span data-stu-id="d8172-103">reentrancy MDA</span></span>
<span data-ttu-id="d8172-104">El Asistente para la depuración administrada (MDA) `reentrancy` se activa cuando se realiza un intento de realizar la transición de código nativo a código administrado en casos donde no se realizó un cambio anterior desde código administrado a código nativo a través de una transición ordenada.</span><span class="sxs-lookup"><span data-stu-id="d8172-104">The `reentrancy` managed debugging assistant (MDA) is activated when an attempt is made to transition from native to managed code in cases where a prior switch from managed to native code was not performed through an orderly transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d8172-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d8172-105">Symptoms</span></span>  
 <span data-ttu-id="d8172-106">El montón de objetos está dañado o se producen otros errores graves al realizar la transición de código nativo a código administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-106">The object heap is corrupted or other serious errors are occurring when transitioning from native to managed code.</span></span>  
  
 <span data-ttu-id="d8172-107">Los subprocesos que cambian entre código nativo y administrado en cualquier dirección deben realizar una transición ordenada.</span><span class="sxs-lookup"><span data-stu-id="d8172-107">Threads that switch between native and managed code in either direction must perform an orderly transition.</span></span> <span data-ttu-id="d8172-108">Pero ciertos puntos de extensibilidad de bajo nivel en el sistema operativo, por ejemplo el controlador de excepciones orientado, permiten pasar de código administrado a código nativo sin realizar una transición ordenada.</span><span class="sxs-lookup"><span data-stu-id="d8172-108">However, certain low-level extensibility points in the operating system, such as the vectored exception handler, allow switches from managed to native code without performing an orderly transition.</span></span>  <span data-ttu-id="d8172-109">Estos modificadores están bajo el control del sistema operativo, en lugar de bajo el control de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d8172-109">These switches are under operating system control, rather than under common language runtime (CLR) control.</span></span>  <span data-ttu-id="d8172-110">Cualquier código nativo que se ejecute dentro de estos puntos de extensibilidad debe evitar realizar llamadas a código administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-110">Any native code that executes inside these extensibility points must avoid calling back into managed code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d8172-111">Causa</span><span class="sxs-lookup"><span data-stu-id="d8172-111">Cause</span></span>  
 <span data-ttu-id="d8172-112">Se ha activado un punto de extensibilidad de bajo nivel del sistema operativo, como el controlador de excepciones orientado, mientras se ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-112">A low-level operating system extensibility point, such as the vectored exception handler, has activated while executing managed code.</span></span>  <span data-ttu-id="d8172-113">El código de aplicación que se invoca a través de ese punto de extensibilidad está intentando devolver la llamada al código administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-113">The application code that is invoked through that extensibility point is attempting to call back into managed code.</span></span>  
  
 <span data-ttu-id="d8172-114">Este problema siempre está causado por código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8172-114">This problem is always caused by application code.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d8172-115">Resolución</span><span class="sxs-lookup"><span data-stu-id="d8172-115">Resolution</span></span>  
 <span data-ttu-id="d8172-116">Examine el seguimiento de la pila para el subproceso que ha activado este MDA.</span><span class="sxs-lookup"><span data-stu-id="d8172-116">Examine the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="d8172-117">El subproceso está intentando llamar de forma no autorizada al código administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-117">The thread is attempting to illegally call into managed code.</span></span>  <span data-ttu-id="d8172-118">El seguimiento de la pila debe mostrar el código de aplicación que usa este punto de extensibilidad, el código del sistema operativo que proporciona este punto de extensibilidad y el código administrado que el punto de extensibilidad ha interrumpido.</span><span class="sxs-lookup"><span data-stu-id="d8172-118">The stack trace should reveal the application code using this extensibility point, the operating system code that provides this extensibility point, and the managed code that was interrupted by the extensibility point.</span></span>  
  
 <span data-ttu-id="d8172-119">Por ejemplo, verá que el MDA se activa en un intento de llamar a código administrado desde dentro de un controlador de excepciones orientado.</span><span class="sxs-lookup"><span data-stu-id="d8172-119">For example, you will see the MDA activated in an attempt to call managed code from inside a vectored exception handler.</span></span>  <span data-ttu-id="d8172-120">En la pila verá el código de control de excepciones del sistema operativo y algún código administrado que desencadena una excepción como <xref:System.DivideByZeroException> o <xref:System.AccessViolationException>.</span><span class="sxs-lookup"><span data-stu-id="d8172-120">On the stack you will see the operating system exception handling code and some managed code triggering an exception such as a <xref:System.DivideByZeroException> or an <xref:System.AccessViolationException>.</span></span>  
  
 <span data-ttu-id="d8172-121">En este ejemplo, la solución correcta consiste en implementar el controlador de excepciones orientado completamente en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d8172-121">In this example, the correct resolution is to implement the vectored exception handler completely in unmanaged code.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d8172-122">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="d8172-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="d8172-123">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="d8172-123">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d8172-124">Output</span><span class="sxs-lookup"><span data-stu-id="d8172-124">Output</span></span>  
 <span data-ttu-id="d8172-125">El MDA informa de que se ha intentado una reentrada ilegal.</span><span class="sxs-lookup"><span data-stu-id="d8172-125">The MDA reports that illegal reentrancy is being attempted.</span></span>  <span data-ttu-id="d8172-126">Examine la pila del subproceso para determinar por qué sucede esto y cómo corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="d8172-126">Examine the thread's stack to determine why this is happening and how to correct the problem.</span></span> <span data-ttu-id="d8172-127">A continuación se incluye la salida del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d8172-127">The following is sample output.</span></span>  
  
```output
Additional Information: Attempting to call into managed code without
transitioning out first.  Do not attempt to run managed code inside
low-level native extensibility points. Managed Debugging Assistant
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a><span data-ttu-id="d8172-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="d8172-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="d8172-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8172-129">Example</span></span>  
 <span data-ttu-id="d8172-130">El siguiente código de ejemplo hace que se inicie una excepción <xref:System.AccessViolationException>.</span><span class="sxs-lookup"><span data-stu-id="d8172-130">The following code example causes an <xref:System.AccessViolationException> to be thrown.</span></span>  <span data-ttu-id="d8172-131">En versiones de Windows que admiten el control de excepciones orientado, esto hará que se llame al controlador de excepciones orientado.</span><span class="sxs-lookup"><span data-stu-id="d8172-131">On versions of Windows that support vectored exception handling, this will cause the managed vectored exception handler to be called.</span></span>  <span data-ttu-id="d8172-132">Si el MDA `reentrancy` está habilitado, se activará durante el intento de llamada a `MyHandler` desde el código de soporte de control de excepciones orientado del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d8172-132">If the `reentrancy` MDA is enabled, the MDA will activate during the attempted call to `MyHandler` from the operating system's vectored exception handling support code.</span></span>  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try
        {  
            // Dispatch on null should AV.  
            Reenter r = null;
            r.Run();  
        }
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8172-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8172-133">See also</span></span>

- [<span data-ttu-id="d8172-134">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="d8172-134">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
