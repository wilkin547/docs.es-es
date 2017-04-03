---
title: "Modificador del parámetro out (Referencia de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: af1f16016053d3c1b3cae34ff0cb6a3ce8cee9e7
ms.lasthandoff: 03/13/2017

---
# <a name="out-parameter-modifier-c-reference"></a>Modificador del parámetro out (Referencia de C#)
La palabra clave `out` hace que los argumentos se pasen por referencia. Esto es como la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla. Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`. Por ejemplo:  
  
 [!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante. Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](../../../csharp/language-reference/keywords/out-generic-modifier.md).
  
 Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método. En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.  
  
 Aunque las palabras clave `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación. Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` y el otro toma un argumento `out`. Por ejemplo, el código siguiente, no se compilará:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
En cambio, la sobrecarga es legal si un método toma un argumento `ref` o `out` y el otro no usa ninguno, como se muestra aquí:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.  
  
 Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Las palabras clave `ref` y `out` no pueden usarse para los siguientes tipos de métodos:  
  
-   Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  

## <a name="declaring-out-arguments"></a>Declarar argumentos `out`   

 Declarar un método con argumentos `out` resulta útil cuando quiere que devuelva varios valores. En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método. Tenga en cuenta que el tercer argumento se asigna a null. Esto permite que los métodos devuelvan valores opcionalmente.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 El [patrón Try](https://docs.microsoft.com/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) implica la devolución de `bool` para indicar si una operación se ha realizado correcta o incorrectamente, y la devolución del valor que ha generado la operación en un argumento `out`. Varios métodos de análisis, como el método @System.DateTime.TryParse(System.String,@System.DateTime), usan este patrón.
   
## <a name="calling-a-method-with-an-out-argument"></a>Llamar a un método con un argumento `out`

En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`. En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,@System.Int32), que intenta convertir una cadena en un número.

 [!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

A partir de C# 7, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente. Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria. El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,@System.Int32).

 [!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`. También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.

 [!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)
