---
title: Genéricos (F#)
description: 'Obtenga información sobre cómo usar F # funciones genéricas y tipos, que le permiten escribir código que funciona con una variedad de tipos sin repetir el código.'
ms.date: 05/16/2016
ms.openlocfilehash: fc061f19c6c7fa737f7ca05aae83fd42c0010b37
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "44084967"
---
# <a name="generics"></a>Genéricos

Los valores de función, los métodos, las propiedades y los tipos agregados de F#, como las clases, los registros y las uniones discriminadas, pueden ser *genéricos*. Las construcciones genéricas contienen al menos un parámetro de tipo que, por lo general, proporciona el usuario de la construcción genérica. Las funciones y los tipos genéricos permiten escribir código que funciona con una variedad de tipos sin repetir el código para cada tipo. Convertir el código en genérico puede ser sencillo en F#, porque a menudo se infiere implícitamente el código para que sea genérico por la inferencia de tipos del compilador y los mecanismos de generalización automáticos.

## <a name="syntax"></a>Sintaxis

```fsharp
// Explicitly generic function.
let function-name<type-parameters> parameter-list =
function-body

// Explicitly generic method.
[ static ] member object-identifer.method-name<type-parameters> parameter-list [ return-type ] =
method-body

// Explicitly generic class, record, interface, structure,
// or discriminated union.
type type-name<type-parameters> type-definition
```

## <a name="remarks"></a>Comentarios

La declaración explícita de una función o tipo genérico es muy parecida a la de una función o tipo no genérico, excepto en la especificación (y uso) de los parámetros de tipos, en corchetes angulares después del nombre de la función o el tipo.

Las declaraciones a menudo son implícitamente genéricas. Si no se especifica completamente el tipo de cada parámetro que se usa para componer una función o un tipo, el compilador intenta inferir el tipo de cada parámetro, valor y variable del código que se escribe. Para más información, vea [Inferencia de tipos](../type-inference.md). Si el código del tipo o función no limita de otro modo los tipos de los parámetros, la función o el tipo son implícitamente genéricos. Este proceso se denomina *generalización automática*. Existen algunas limitaciones en la generalización automática. Por ejemplo, si el compilador de F# no puede inferir los tipos de una construcción genérica, informa sobre un error que hace referencia a una restricción denominada *restricción de valor*. En ese caso, puede que sea necesario agregar algunas anotaciones de tipo. Para más información sobre la generalización automática y la restricción de valor, y cómo cambiar el código para resolver el problema, vea [Generalización automática](automatic-generalization.md).

En la sintaxis anterior, *parámetros de tipo* es una lista separada por comas de parámetros que representan tipos desconocidos, cada uno de los cuales comienza por una comilla simple, opcionalmente con una cláusula de restricción que limita aún más los tipos que se pueden usar para ese tipo de parámetro. Para obtener información sobre la sintaxis de las cláusulas de restricción de varios tipos y otra información sobre restricciones, vea [Restricciones](constraints.md).

La *definición de tipos* de la sintaxis es la misma que la definición de tipos de un tipo no genérico. Incluye los parámetros del constructor para un tipo de clase, una cláusula `as` opcional, el símbolo igual, los campos de registro, la cláusula `inherit`, las opciones para una unión discriminada, enlaces `let` y `do`, definiciones de miembros y todo lo que se permite en una definición de tipos no genéricos.

Los demás elementos de la sintaxis son los mismos que los de los tipos y funciones no genéricos. Por ejemplo, *identificador de objeto* es un identificador que representa el objeto contenedor.

Las propiedades, campos y constructores no pueden ser más genéricos que el tipo envolvente. Además, los valores de un módulo no pueden ser genéricos.

## <a name="implicitly-generic-constructs"></a>Construcciones genéricas implícitas

Cuando el compilador de F# infiere los tipos del código, trata automáticamente todas las funciones que pueden ser genéricas como tales. Si se especifica un tipo explícitamente, como un tipo de parámetro, se impide la generalización automática.

En el ejemplo de código siguiente, `makeList` es genérico aunque no se ha declarado como tal y sus parámetros tampoco.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1700.fs)]

La firma de la función se infiere como `'a -> 'a -> 'a list`. Observe que en este ejemplo `a` y `b` se infieren para tener el mismo tipo. Esto se debe a que se incluyen en una lista y todos los elementos de una lista deben ser del mismo tipo.

También se puede hacer genérica una función usando la sintaxis de comillas simples en una anotación de tipo para indicar que un tipo de parámetro es un parámetro de tipo genérico. En el código siguiente, `function1` es genérico porque sus parámetros se han declarado de esta manera, como parámetros de tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1701.fs)]

## <a name="explicitly-generic-constructs"></a>Construcciones explícitamente genéricas

Para convertir una función en genérica, se declaran explícitamente sus parámetros de tipo entre corchetes angulares (`<type-parameter>`). Esto se ilustra en el código siguiente:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1703.fs)]

## <a name="using-generic-constructs"></a>Uso de construcciones genéricas

Cuando se usan funciones o métodos genéricos, no siempre es necesario especificar los argumentos de tipo. El compilador usa la inferencia de tipos para inferir los argumentos de tipo adecuados. Si la ambigüedad se mantiene, se pueden proporcionar argumentos de tipo en corchetes angulares y separarlos con comas.

En el código siguiente se muestra el uso de las funciones que se definen en las secciones anteriores.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1702.fs)]

>[!NOTE]
Hay dos maneras de hacer referencia a un tipo genérico por nombre. Por ejemplo, `list<int>` e `int list` son dos formas de hacer referencia a un tipo genérico `list` que tiene un único argumento de tipo `int`. Por convención, la segunda forma solo se usa con tipos de F# integrados como `list` y `option`. Si hay varios argumentos de tipo, normalmente se usa la sintaxis `Dictionary<int, string>`, pero también se puede usar la sintaxis `(int, string) Dictionary`.

## <a name="wildcards-as-type-arguments"></a>Caracteres comodín como argumentos de tipo

Para especificar que el compilador debe inferir un argumento de tipo, se puede usar un subrayado o símbolo comodín (`_`), en lugar de un argumento de tipo con nombre. Esto se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1704.fs)]

## <a name="constraints-in-generic-types-and-functions"></a>Restricciones en los tipos y funciones genéricos

En una definición de función o tipo genérico, solo se pueden usar las construcciones que se sabe que están disponibles en el parámetro de tipo genérico. Esto es necesario para habilitar la comprobación de las llamadas a métodos y funciones en tiempo de compilación. Si se declaran explícitamente los parámetros de tipo, se podrá aplicar una restricción explícita a un parámetro de tipo genérico para indicar al compilador que están disponibles determinados métodos y funciones. Pero si se permite que el compilador de F# infiera los tipos de parámetro genéricos, determinará las restricciones apropiadas. Para más información, vea [Restricciones](constraints.md).

## <a name="statically-resolved-type-parameters"></a>Parámetros de tipo resueltos estáticamente

Hay dos clases de parámetros de tipo que se pueden usar en programas de F#. La primera son los parámetros de tipo genérico de la naturaleza descrita en las secciones anteriores. Esta primera clase equivale a los parámetros de tipo genérico que se usan en lenguajes como Visual Basic y C#. Otra clase de parámetro de tipo es específica de F# y se denomina *parámetro de tipo resuelto estáticamente*. Para obtener información sobre estas construcciones, vea [Parámetros de tipo resueltos estáticamente](statically-resolved-type-parameters.md).

## <a name="examples"></a>Ejemplos

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1705.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje](../index.md)
- [Tipos](../fsharp-types.md)
- [Parámetros de tipo resueltos estáticamente](statically-resolved-type-parameters.md)
- [Genéricos en .NET Framework](~/docs/standard/generics/index.md)
- [Generalización automática](automatic-generalization.md)
- [Restricciones](constraints.md)
