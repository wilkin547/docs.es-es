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
ms.openlocfilehash: 228226d90e70d296681e48ffe85dada8eb18209a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247374"
---
# <a name="jitcompilationstart-mda"></a>MDA de jitCompilationStart

El Asistente para la depuración administrada (MDA) `jitCompilationStart` se activa para informar del momento en el que el compilador Just-In-Time (JIT) empieza a compilar una función.  
  
## <a name="symptoms"></a>Síntomas  

 El tamaño del espacio de trabajo aumenta para un programa que ya está en formato de imagen nativa, porque mscorjit.dll se carga en el proceso.  
  
## <a name="cause"></a>Causa  

No todos los ensamblados de los que depende el programa se han generado en formato nativo o un ensamblado no se ha registrado correctamente.  

## <a name="resolution"></a>Solución  

 La habilitación de este MDA le permite identificar la función que se va a compilar con JIT. Asegúrese de que el ensamblado que contiene la función se genera en formato nativo y se registra correctamente.
  
## <a name="effect-on-the-runtime"></a>Efecto en el tiempo de ejecución  

 Este MDA registra un mensaje justo antes de que un método se compile con JIT, por lo que habilitar este MDA tiene un impacto significativo en el rendimiento. Si un método está alineado, este MDA no generará un mensaje independiente.  
  
## <a name="output"></a>Resultados  

 En el ejemplo de código siguiente se muestran los resultados del ejemplo. En este caso, el resultado muestra que, en la prueba del ensamblado, el método "m" de la clase "ns2.CO" se compiló JIT.  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a>Configuración  

 En el archivo de configuración siguiente se muestra una variedad de filtros que se pueden emplear para filtrar qué métodos se notifican cuando se compilan con JIT por primera vez. Puede especificar que se notifiquen todos los métodos estableciendo el valor del atributo name en \* .  
  
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
  
## <a name="example"></a>Ejemplo  

 El ejemplo de código siguiente está pensado para usarse con el archivo de configuración anterior.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
