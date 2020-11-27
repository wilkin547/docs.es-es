---
title: MDA de callbackOnCollectedDelegate
description: Revise el Asistente para la depuración administrada (MDA) de callbackOnCollectedDelegate en .NET, que se invoca si se produce una devolución de llamada después de que el delegado se recolecta como elemento no utilizado.
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
ms.openlocfilehash: 1d95d01fb1e5a49ca055717ef4701b6f46394df3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265237"
---
# <a name="callbackoncollecteddelegate-mda"></a>MDA de callbackOnCollectedDelegate

El Asistente para la depuración administrada (MDA) `callbackOnCollectedDelegate` se activa si se serializa un delegado desde código administrado a no administrado como un puntero de función y se coloca una devolución de llamada en dicho puntero después de que el delegado haya sido recolectado como elemento no utilizado.  
  
## <a name="symptoms"></a>Síntomas  

 Al intentar llamar al código administrado mediante punteros de función obtenidos de delegados administrados, se producen infracciones de acceso. Estos errores no son errores de Common Language Runtime (CLR) aunque pueden parecerlo porque la infracción de acceso se produce en el código de CLR.  
  
 El error no es constante; a veces, la llamada al puntero de función se realiza correctamente y otras veces no. El error podría producirse solo en condiciones de mucha carga o después de un número aleatorio de intentos.  
  
## <a name="cause"></a>Causa  

 El delegado a partir del cual se creó el puntero de función y se expuso al código no administrado se recolectó como elemento no utilizado. Cuando el componente no administrado intenta llamar al puntero de función, genera una infracción de acceso.  
  
 El error parece aleatorio porque depende de cuándo se produce la recolección de elementos no utilizados. Si un delegado es candidato para la recolección, la recolección de elementos no utilizados puede producirse después de la devolución de llamada y la llamada se realiza correctamente. En otras ocasiones, la recolección de elementos no utilizados se produce antes de la devolución de llamada, la devolución de llamada genera una infracción de acceso y el programa se detiene.  
  
 La probabilidad del error depende del tiempo entre la serialización del delegado y la devolución de llamada en el puntero de función, así como de la frecuencia de las recolecciones de elementos no utilizados. El error será esporádico si el tiempo entre la serialización del delegado y la devolución de llamada posterior es breve. Este suele ser el caso cuando el método no administrado que recibe el puntero de función no guarda el puntero de función para su uso posterior y, en su lugar, realiza una devolución de llamada al puntero de función inmediatamente para completar la operación antes de la devolución. De forma similar, se producen más recolecciones de elementos no utilizados cuando un sistema tiene mucha carga, lo que aumenta las probabilidades de que se produzca una recolección de elementos no utilizados antes de la devolución de llamada.  
  
## <a name="resolution"></a>Solución  

 Una vez calculadas las referencias de un delegado como un puntero de función no administrada, el recolector de elementos no utilizados no puede controlar su vigencia. En su lugar, el código debe mantener una referencia al delegado durante la vigencia del puntero de función no administrado. Pero para poder hacerlo, primero debe identificar qué delegado se ha recolectado. Cuando el MDA se activa, proporciona el nombre del tipo del delegado. Use este nombre para buscar en el código la invocación de plataforma o las firmas COM que pasan el delegado al código no administrado. El delegado que produce el error pasa por uno de estos sitios de llamada. También puede habilitar el MDA `gcUnmanagedToManaged` para aplicar una recolección de elementos no utilizados antes de cada devolución de llamada a CLR. Esto eliminará la incertidumbre provocada por la recolección de elementos no utilizados porque garantiza que siempre se producirá una recolección de elementos no utilizados antes de la devolución de llamada. Una vez que sepa qué delegado se ha recolectado, cambie el código para mantener una referencia a dicho delegado en la parte administrada durante la vigencia del puntero de función no administrado cuyas referencias se han calculado.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Cuando las referencias de los delegados se calculan como punteros de función, CLR asigna un código thunk que realiza la transición de no administrado a administrado. El código no administrado llama a este código thunk antes de invocar en última instancia al delegado administrado. Si el MDA `callbackOnCollectedDelegate` no está habilitado, el código no administrado de cálculo de referencias se elimina al recopilar el delegado. Si el MDA `callbackOnCollectedDelegate` está habilitado, el código no administrado de serialización no se elimina inmediatamente al recopilar el delegado. En su lugar, se mantienen activas las últimas 1.000 instancias de forma predeterminada y se cambian para activar el MDA cuando se le llama. El código thunk se borra después de recopilar 1.001 delegados con referencias calculadas.  
  
## <a name="output"></a>Resultados  

 El MDA notifica el nombre de tipo del delegado que se recopiló antes de intentar una devolución de llamada en su puntero de función no administrado.  
  
## <a name="configuration"></a>Configuración  

 El ejemplo siguiente muestra las opciones de configuración de la aplicación. Establece el número de fragmentos de código thunk que el MDA mantiene activo, hasta 1.500. El valor predeterminado de `listSize` es 1.000, el mínimo es 50 y el máximo es 2.000.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra una situación que puede activar este MDA:  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
- [gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)
