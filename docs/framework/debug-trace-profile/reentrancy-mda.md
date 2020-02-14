---
title: MDA de reentrada
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
ms.openlocfilehash: 8f1621090079c030e3c055a417ed9bcad882bf78
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217236"
---
# <a name="reentrancy-mda"></a>MDA de reentrada
El Asistente para la depuración administrada (MDA) `reentrancy` se activa cuando se realiza un intento de realizar la transición de código nativo a código administrado en casos donde no se realizó un cambio anterior desde código administrado a código nativo a través de una transición ordenada.  
  
## <a name="symptoms"></a>Síntomas  
 El montón de objetos está dañado o se producen otros errores graves al realizar la transición de código nativo a código administrado.  
  
 Los subprocesos que cambian entre código nativo y administrado en cualquier dirección deben realizar una transición ordenada. Pero ciertos puntos de extensibilidad de bajo nivel en el sistema operativo, por ejemplo el controlador de excepciones orientado, permiten pasar de código administrado a código nativo sin realizar una transición ordenada.  Estos modificadores están bajo el control del sistema operativo, en lugar de bajo el control de Common Language Runtime (CLR).  Cualquier código nativo que se ejecute dentro de estos puntos de extensibilidad debe evitar realizar llamadas a código administrado.  
  
## <a name="cause"></a>Causa  
 Se ha activado un punto de extensibilidad de bajo nivel del sistema operativo, como el controlador de excepciones orientado, mientras se ejecuta código administrado.  El código de aplicación que se invoca a través de ese punto de extensibilidad está intentando devolver la llamada al código administrado.  
  
 Este problema siempre está causado por código de aplicación.  
  
## <a name="resolution"></a>Solución  
 Examine el seguimiento de la pila para el subproceso que ha activado este MDA.  El subproceso está intentando llamar de forma no autorizada al código administrado.  El seguimiento de la pila debe mostrar el código de aplicación que usa este punto de extensibilidad, el código del sistema operativo que proporciona este punto de extensibilidad y el código administrado que el punto de extensibilidad ha interrumpido.  
  
 Por ejemplo, verá que el MDA se activa en un intento de llamar a código administrado desde dentro de un controlador de excepciones orientado.  En la pila verá el código de control de excepciones del sistema operativo y algún código administrado que desencadena una excepción como <xref:System.DivideByZeroException> o <xref:System.AccessViolationException>.  
  
 En este ejemplo, la solución correcta consiste en implementar el controlador de excepciones orientado completamente en código no administrado.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 El MDA informa de que se ha intentado una reentrada ilegal.  Examine la pila del subproceso para determinar por qué sucede esto y cómo corregir el problema. A continuación se incluye la salida del ejemplo.  
  
```output
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código de ejemplo hace que se inicie una excepción <xref:System.AccessViolationException>.  En versiones de Windows que admiten el control de excepciones orientado, esto hará que se llame al controlador de excepciones orientado.  Si el MDA `reentrancy` está habilitado, se activará durante el intento de llamada a `MyHandler` desde el código de soporte de control de excepciones orientado del sistema operativo.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
