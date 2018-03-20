---
title: ref (Referencia de C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 427045317e9d7d0fe3435a486b9f761908ab5e78
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="ref-c-reference"></a>ref (Referencia de C#)

La palabra clave `ref` indica un valor que se ha pasado mediante referencia. Se usa en tres contextos diferentes: 

- En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia. Vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference) para obtener más información.

- En una firma del método, para devolver un valor al autor de la llamada mediante referencia. Para obtener más información, vea [Valores devueltos de referencia](#reference-return-values).

- En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar. Vea [Variables locales de tipo ref](#ref-locals) para obtener más información.

## <a name="passing-an-argument-by-reference"></a>Pasar un argumento mediante referencia

Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor. El efecto de pasar por referencia es que cualquier cambio del argumento en el método llamado se refleja en el método de llamada. Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hace ahora referencia al nuevo objeto cuando el método devuelve.

> [!NOTE]
>  No confunda el concepto de pasar por referencia con el concepto de tipos de referencia. Estos dos conceptos no son lo mismo. Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia. No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.  

Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

Un argumento que se pasa a un parámetro `ref` o `in` debe inicializarse antes de pasarlo. En esto difiere de los parámetros [out](out-parameter-modifier.md), cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos.

Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref`, `in` o `out`. Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out` o `in`, se produce un error de compilador. El código siguiente, por ejemplo, no se compila.  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
En cambio, los métodos pueden sobrecargarse cuando un método tiene un parámetro `ref`, `in` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.  
  
 Las propiedades no son variables. Son métodos y no se pueden pasar a parámetros `ref`.  
  
 Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out ](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:  
  
- Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
- Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  

## <a name="passing-an-argument-by-reference-an-example"></a>Pasar un argumento mediante referencia: un ejemplo

En los ejemplos anteriores se pasan tipos de valor mediante referencia. También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia. Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada. La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia. Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada. En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.   
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Valores devueltos de referencia

Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada. Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto que contiene el método. 

Un valor devuelto de referencia se define mediante la palabra clave `ref`:

- En la firma del método. Por ejemplo, la siguiente firma del método indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> mediante referencia.

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- Entre el token `return` y la variable devuelta en una instrucción `return` en el método. Por ejemplo:
 
   ```csharp
   return ref DecimalArray[0];
   ``` 

Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals). 

Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).

## <a name="ref-locals"></a>Variables locales de tipo ref

Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`.  Una variable local de tipo ref debe inicializarse y asignarse a un valor devuelto de tipo ref. Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.

Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia. 

Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

Tenga en cuenta que la palabra clave `ref` debe usarse en ambos lugares, o el compilador genera un error CS8172, "No se puede inicializar una variable por referencia con un valor". 
 
## <a name="a-ref-returns-and-ref-locals-example"></a>Un ejemplo de valores devueltos y variables locales de tipo ref

En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`. También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`. Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
