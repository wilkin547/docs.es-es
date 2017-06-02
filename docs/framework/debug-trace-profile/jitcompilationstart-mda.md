---
title: "jitCompilationStart MDA | Microsoft Docs"
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
  - "JIT compilation"
  - "MDAs (managed debugging assistants), JIT compilation"
  - "JitCompilationStart MDA"
  - "managed debugging assistants (MDAs), JIT compilation"
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# jitCompilationStart MDA
El asistente para la depuración administrada \(MDA\) `jitCompilationStart` se activa para informar del momento en que el compilador de Just\-In\-Time \(JIT\) empieza a compilar una función.  
  
## Síntomas  
 El tamaño del espacio de trabajo aumenta para un programa que ya está en formato de imagen nativa, porque se carga el archivo .dll en el proceso.  
  
## Motivo  
 No todos los ensamblados de los que depende el programa se han generado en formato nativo; y aquéllos que lo han hecho, no siempre se han registrado correctamente.  
  
## Resolución  
 Habilitar este asistente para la depuración administrada permite determinar qué función va a ser compilado por JIT.  Determine si el ensamblado que contiene la función se genera en formato nativo y se registra adecuadamente.  
  
## Efecto en el Runtime  
 Este asistente para la depuración administrada registra un mensaje justo antes de que un método sea compilado por JIT, por lo que habilitarlo supone un impacto significativo en el rendimiento.  Tenga en cuenta que si hay un método en línea, este MDA no generará ningún mensaje independiente.  
  
## Resultados  
 En el ejemplo de código siguiente se muestra el resultado del ejemplo.  En este caso, el resultado muestra que en el ensamblado Test el método "m" en la clase "ns2.CO" fue compilado por JIT.  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## Configuration  
 El archivo de configuración siguiente muestra la gama de filtros que se puede utilizar para filtrar los métodos de los que se informa al ser compilados por JIT por primera vez.  Se puede especificar que se informe sobre todos los métodos estableciendo el valor del atributo de nombre como \*.  
  
```  
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
  
## Ejemplo  
 El ejemplo de código siguiente está diseñado para ser utilizado con el archivo de configuración anterior.  
  
```  
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
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)