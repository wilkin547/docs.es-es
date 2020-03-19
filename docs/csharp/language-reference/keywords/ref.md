---
title: ref (palabra clave) - Referencia de C#
ms.date: 03/26/2019
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 05f0bd8566851678203a3f064b96bfff7dee18b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398134"
---
# <a name="ref-c-reference"></a>ref (Referencia de C#)

La palabra clave `ref` indica un valor que se ha pasado mediante referencia. Se usa en cuatro contextos diferentes:

- En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia. Para más información, vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference).
- En una firma del método, para devolver un valor al autor de la llamada mediante referencia. Para obtener más información, consulte [Valores devueltos de referencia](#reference-return-values).
- En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar o, en general, que una variable local accede a otro valor por referencia. Para más información, vea [Variables locales de tipo ref](#ref-locals).
- En una declaración `struct` para declarar `ref struct` o `readonly ref struct`. Para más información, vea [Tipo de estructura de referencia](#ref-struct-types).

## <a name="passing-an-argument-by-reference"></a>Pasar un argumento mediante referencia

Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor. La palabra clave `ref` hace que el parámetro formal sea un alias para el argumento, que debe ser una variable. En otras palabras, cualquier operación en el parámetro se realiza en el argumento. Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hace ahora referencia al nuevo objeto cuando el método devuelve.

> [!NOTE]
> No confunda el concepto de pasar por referencia con el concepto de tipos de referencia. Estos dos conceptos no son lo mismo. Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia. No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.  

Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

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
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.  
  
 Las propiedades no son variables. Son métodos y no se pueden pasar a parámetros `ref`.  
  
 Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:  
  
- Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).  
- Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.  

## <a name="passing-an-argument-by-reference-an-example"></a>Paso de un argumento mediante referencia: Un ejemplo

En los ejemplos anteriores se pasan tipos de valor mediante referencia. También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia. Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada. La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia. Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada. En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Valores devueltos de referencia

Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada. Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto que contiene el método.

Un valor devuelto de referencia se define mediante la palabra clave `ref`:

- En la firma del método. Por ejemplo, en la firma de método siguiente se indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> por referencia.

```csharp
public ref decimal GetCurrentPrice()
```

- Entre el token `return` y la variable devuelta en una instrucción `return` en el método. Por ejemplo:

```csharp
return ref DecimalArray[0];
```

Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals).

El método llamado también puede declarar el valor devuelto como `ref readonly` para devolver el valor por referencia y exigir que el código de llamada no pueda modificar el valor devuelto. El método de llamada puede evitar copiar el valor devuelto mediante el almacenamiento del valor en una variable de tipo [ref readonly](#ref-readonly-locals).

Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).

## <a name="ref-locals"></a>Variables locales de tipo ref

Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`. Una variable local de tipo ref no se puede inicializar en un valor devuelto de tipo no ref. Es decir, el lado derecho de la inicialización debe ser una referencia. Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.

Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia.

Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

Puede acceder a un valor por referencia de la misma manera. En algunos casos, acceder a un valor por referencia aumenta el rendimiento, ya que evita una operación de copia potencialmente cara. Por ejemplo, en la instrucción siguiente se muestra cómo es posible definir un valor local de referencia que se usa para hacer referencia a un valor.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Tenga en cuenta que en ambos ejemplos la palabra clave `ref` debe usarse en ambos lugares. De lo contrario, el compilador genera el error CS8172, "No se puede inicializar una variable por referencia con un valor".

A partir C# 7.3, la variable de iteración de la instrucción `foreach` puede ser una variable ref local o ref readonly local. Para más información, vea el artículo sobre la [instrucción foreach](foreach-in.md).

A partir C# 7.3, las variables locales de tipo ref o locales de tipo ref readonly se pueden reasignar con el [operador de asignación ref](../operators/assignment-operator.md#ref-assignment-operator).

## <a name="ref-readonly-locals"></a>Variables locales de tipo ref readonly

Una variable local de tipo ref readonly se usa para hacer referencia a los valores devueltos por el método o la propiedad que tiene `ref readonly` en su firma y utiliza `return ref`. Una variable `ref readonly` combina las propiedades de una `ref` variable local con una variable `readonly`: es un alias para el almacenamiento al que se asigna y no se puede modificar.

## <a name="a-ref-returns-and-ref-locals-example"></a>Un ejemplo de valores devueltos y variables locales de tipo ref

En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`. También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`. Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a>Tipos de estructura de referencia

La incorporación del modificador `ref` a una declaración `struct` define que las instancias de ese tipo se deben asignar a la pila. En otras palabras, las instancias de estos tipos no se pueden crear nunca en el montón como un miembro de otra clase. La principal motivación para esta característica era <xref:System.Span%601> y las estructuras relacionadas.

El objetivo de mantener un tipo `ref struct` como una variable asignada a la pila presenta varias reglas que el compilador exige para todos los tipos `ref struct`.

- No puede encerrar un valor de `ref struct`. No puede asignar un tipo `ref struct` a una variable de tipo `object`, `dynamic` o cualquier tipo de interfaz.
- Los tipos `ref struct` no pueden implementar interfaces.
- No se puede declarar `ref struct` como miembro de campo de una clase o una estructura normal. Esto incluye la declaración de una propiedad implementada automáticamente, lo que crea un campo de respaldo generado por el compilador.
- No puede declarar variables locales que sean tipos `ref struct` en métodos asincrónicos. Puede declararlas en los métodos sincrónicos que devuelven tipos similares a <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> o `Task`.
- No puede declarar las variables locales de `ref struct` en iteradores.
- No puede capturar variables `ref struct` en expresiones lambda o funciones locales.

Estas restricciones aseguran que no se usará por error un valor `ref struct` de manera que pueda promoverlo al montón administrado.

Puede combinar modificadores para declarar una estructura como `readonly ref`. `readonly ref struct` combina las ventajas y las restricciones de las declaraciones `ref struct` y `readonly struct`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Escritura de código seguro y eficaz](../../write-safe-efficient-code.md)
- [Devoluciones y variables locales ref](../../programming-guide/classes-and-structs/ref-returns.md)
- [Expresión condicional ref](../operators/conditional-operator.md#conditional-ref-expression)
- [Pasar parámetros](../../programming-guide/classes-and-structs/passing-parameters.md)
- [Parámetros de métodos](method-parameters.md)
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
