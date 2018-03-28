---
title: Modificador del parámetro in (referencia de C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b8b21e2bdc95829c831ee71f24b47986321b7d0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="in-parameter-modifier-c-reference"></a>Modificador del parámetro in (referencia de C#)

La palabra clave `in` hace que los argumentos se pasen por referencia. Es como las palabras clave [ref](ref.md) o [out](out-parameter-modifier.md), salvo que el método llamado no puede modificar los argumentos `in`. Mientras que los argumentos `ref` sí se pueden modificar, los argumentos `out` debe modificarlos el llamador, y estas modificaciones se pueden observar en el contexto de llamada.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

En el ejemplo anterior se muestra que el modificador `in` no es necesario en el sitio de llamada, sino que solo lo es en la declaración del método.

> [!NOTE] 
> Además, la palabra clave `in` puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es contravariante, parte de una instrucción `foreach` o de una cláusula `join` de una consulta de LINQ. Para obtener más información sobre el uso de la palabra clave `in` en esos contextos, vea [in](in.md), en que se proporcionan vínculos que dirigen a todos esos usos.
  
 Las variables que se han pasado como argumentos `in` deben inicializarse antes de pasarse en una llamada de método. Sin embargo, es posible que el método llamado no asigne ningún valor o modifique el argumento.  
  
 Aunque las palabras clave `in`, `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación. Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`. Por ejemplo, el código siguiente, no se compilará:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Se permiten las sobrecargas basadas en la presencia de `in`, pero ella genera una advertencia del compilador:  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

Se pueden pasar propiedades o constantes como parámetros `in` porque el método de llamada no modifica sus valores.
  
Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:  
  
- Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
  
- Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  

Normalmente, se declaran los argumentos `in` para evitar las operaciones de copia necesarias para pasar argumentos por valor. Esto es muy útil cuando los argumentos son tipos de valor, como estructuras, donde las operaciones de copia son más caras que pasar por referencia.

> [!WARNING]
>  Los parámetros `in` pueden ser todavía más caros si se usan de forma incorrecta. Es posible que el compilador no sepa si los métodos de miembro modifican el estado de la estructura. Si el compilador no puede asegurarse de que el objeto no se modifica, creará, a modo de defensa, una copia y llamará a las referencias de miembro usando esa copia. Cualquier posible modificación se realiza sobre esa copia defensiva. Las dos formas de evitar estas copias son pasar parámetros `in` como argumentos `in` o definir las estructuras como `readonly struct`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)  
 [Semántica de referencia con tipos de valor](../../../csharp/reference-semantics-with-value-types.md)
