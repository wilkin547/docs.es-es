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
ms.openlocfilehash: 7492a4c0547680a6ace85a5f7c98567770f5575a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181780"
---
# <a name="opengenericcercall-mda"></a>MDA de openGenericCERCall

El asistente para la depuración administrada `openGenericCERCall` se activa para advertir que se está procesando un gráfico de región de ejecución restringida (CER) con variables de tipo genérico en el método raíz en la compilación JIT o en tiempo de generación de imágenes nativas y al menos una de las variables de tipo genérico es un tipo de referencia de objeto.

## <a name="symptoms"></a>Síntomas

El código de la CER no se ejecuta cuando se anula un subproceso o se descarga un dominio de aplicación.

## <a name="cause"></a>Causa

En tiempo de compilación JIT, una instancia que contiene un tipo de referencia de objeto solo es representativa porque el código resultante es compartido, y cada una de las variables de tipo de referencia de objeto puede ser cualquier tipo de referencia de objeto. Esto puede impedir la preparación de algunos recursos de tiempo de ejecución antes de tiempo.

En concreto, los métodos con variables de tipo genérico pueden asignar lentamente recursos en segundo plano. Estas se denominan entradas de diccionario genéricas. Por ejemplo, para `List<T> list = new List<T>();` `T` la instrucción donde es una variable de tipo genérico, el tiempo de `List<Object>, List<String>`ejecución debe buscar y posiblemente crear la creación de instancias exacta en tiempo de ejecución, por ejemplo, , etc. Esto puede producir un error por diferentes motivos que se escapan al control del desarrollador, como memoria insuficiente.

Solo se debería activar este MDA en tiempo de compilación JIT, no cuando hay una creación de instancias exactas.

Cuando se activa este MDA, los posibles síntomas son que las CER no están habilitadas para la creación de instancias incorrectas. De hecho, el tiempo de ejecución no ha intentado implementar una CER en las circunstancias que provocaron que se activara el MDA. Por tanto, si el desarrollador usa una instancia compartida de la CER, no se detectan los errores de compilación de JIT, los errores de carga de tipos genéricos o las anulaciones de subprocesos dentro de la CER deseada.

## <a name="resolution"></a>Solución

No use variables de tipo genérico que son del tipo de referencia de objeto para los métodos que puede contener una CER.

## <a name="effect-on-the-runtime"></a>Efecto en el Runtime

Este MDA no tiene ningún efecto en el CLR.

## <a name="output"></a>Output

A continuación se muestra un ejemplo de salida de este MDA:
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a>Configuración

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a>Ejemplo

No se ejecuta el código de la CER.

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

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnóstico de errores con asistentes para la depuración administrada](diagnosing-errors-with-managed-debugging-assistants.md)
