---
title: "reentrancy MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "unmanaged code, debugging"
  - "transitioning threads unmanaged to managed code"
  - "reentrancy MDA"
  - "reentrancy without an orderly transition"
  - "managed debugging assistants (MDAs), reentrancy"
  - "illegal reentrancy"
  - "MDAs (managed debugging assistants), reentrancy"
  - "threading [.NET Framework], managed debugging assistants"
  - "managed code, debugging"
  - "native debugging, MDAs"
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# reentrancy MDA
El asistente para la depuración administrada \(MDA\) `reentrancy` se activa cuando se intenta realizar una transición desde código nativo a código administrado en los casos en los que no se realizó un cambio anterior a un código nativo mediante una transición ordenada.  
  
## Síntomas  
 El montón de objetos está dañado o se producen otros errores graves al realizar la transición de código nativo a código administrado.  
  
 Los subprocesos que cambian entre código nativo y administrado en cualquier dirección deben seguir una transición ordenada.  Sin embargo, determinados puntos de extensibilidad de bajo nivel del sistema operativo, como el controlador de excepciones vectorizadas, permiten pasar de código administrado a código nativo sin realizar una transición ordenada.  Estos cambios se realizan bajo el control de sistema operativo, en lugar de bajo el control de Common Language Runtime \(CLR\).  Cualquier código nativo que se ejecute dentro de estos puntos de extensibilidad debe evitar las llamadas de vuelta al código administrado.  
  
## Motivo  
 Un punto de extensibilidad de sistema operativo de bajo nivel, como el controlador de excepciones vectorizadas, se ha activado al ejecutar el código administrado.  El código de aplicación que se invoca a través de ese punto de extensibilidad está intentando llamar de vuelta al código administrado.  
  
 Este problema siempre está causado por el código de aplicación.  
  
## Resolución  
 Examine el seguimiento de la pila para conocer el subproceso que ha activado el MDA.  El subproceso está intentando llamar al código administrado de manera no válida.  El seguimiento de la pila debería mostrar el código de aplicación que utiliza este punto de extensibilidad, el código del sistema operativo que proporciona este punto de extensibilidad y el código administrado que interrumpió el punto de extensibilidad.  
  
 Por ejemplo, verá que se activa el MDA en un intento de llamar al código administrado desde dentro de un controlador de excepciones vectorizado.  En la pila verá el código de control de excepciones del sistema operativo y parte del código administrado que desencadena una excepción como por ejemplo <xref:System.DivideByZeroException> o <xref:System.AccessViolationException>.  
  
 En este ejemplo, la resolución correcta consiste en implementar completamente el controlador de excepciones vectorizado en código no administrado.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 El MDA informa de que se está intentando una reentrada no válida.  Examine la pila del subproceso para determinar por qué ocurre esto y cómo corregir el problema.  A continuación se incluyen resultados de ejemplo.  
  
```  
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el ejemplo de código siguiente hace que se inicie una excepción <xref:System.AccessViolationException>.  En versiones de Windows que admiten el control de excepciones vectorizado, esto hará que se llame al controlador de excepciones vectorizado.  Si está habilitado el MDA `reentrancy`, el MDA se activará durante el intento de llamada a `MyHandler` desde el código de compatibilidad del control de excepciones vectorizado del sistema operativo.  
  
```  
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
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)