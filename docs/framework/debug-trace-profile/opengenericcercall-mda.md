---
title: "openGenericCERCall MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), CER calls"
  - "open generic CER calls"
  - "constrained execution regions"
  - "openGenericCERCall MDA"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
  - "generics [.NET Framework], open generic CER calls"
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# openGenericCERCall MDA
El asistente para la depuración administrada `openGenericCERCall` se activa para advertir de que se está procesando un gráfico de un área de ejecución restringida \(CER\) con variables de tipo genérico en el método raíz en la compilación JIT o en el tiempo de generación de imagen nativa, y al menos una de las variables de tipo genérico es un tipo de referencia a objeto.  
  
## Síntomas  
 El código de la CER no se ejecuta cuando se anula un subproceso o cuando se descarga un dominio de aplicación.  
  
## Motivo  
 En tiempo de compilación JIT, la creación de una instancia que contiene un tipo de referencia a objeto sólo es representativa porque el código resultante es compartido y cada una de las variables de tipo de referencia a objeto podrían ser de cualquier tipo de referencia a objeto.  Esto puede impedir la preparación por adelantado de algunos recursos en tiempo de ejecución.  
  
 En concreto, los métodos con variables de tipo genérico pueden asignar lentamente recursos en segundo plano.  Éstas se denominan entradas del diccionario genéricas.  Por ejemplo, para la instrucción `List<T> list = new List<T>();` en la que `T` es una variable de tipo genérico, el motor en tiempo de ejecución debe consultar y posiblemente realizar la creación exacta de instancias en tiempo de ejecución, por ejemplo, `List<Object>, List<String>`, `` y así sucesivamente.  Esto puede producir errores por una variedad de motivos que escapan al control del desarrollador, como que no haya memoria suficiente.  
  
 Este MDA sólo se debería activar en tiempo de compilación JIT, no cuando hay una creación de instancias exacta.  
  
 Cuando se activa este MDA, los posibles síntomas son que las CER no funcionan a causa de la creación de instancias incorrecta.  De hecho, el tiempo de ejecución no ha intentado implementar una CER en las circunstancias que hicieron que se activara el MDA.  Por tanto, si el desarrollador utiliza una creación de instancias compartida de la CER, no se detectan los errores de compilación JIT, los errores de carga de tipos genéricos o las anulaciones de subprocesos dentro del área de la CER deseada.  
  
## Resolución  
 No utilice variables de tipo genérico que son del tipo de referencia a objeto para los métodos que pueden contener una CER.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 Lo siguiente es un ejemplo de resultado de este MDA.  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 No se ejecuta el código CER.  
  
```  
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
  
## Vea también  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)