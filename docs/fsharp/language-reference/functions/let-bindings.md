---
title: Enlaces let
description: Obtenga información sobre cómo usar F# un enlace ' Let ', que asocia un identificador con un valor o una función.
ms.date: 05/16/2016
ms.openlocfilehash: 654631c7d1c48d8737e6098c98efee54cfdd91be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630638"
---
# <a name="let-bindings"></a>Enlaces let

Un *enlace* asocia un identificador con un valor o una función. La `let` palabra clave se usa para enlazar un nombre a un valor o una función.

## <a name="syntax"></a>Sintaxis

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Comentarios

La `let` palabra clave se usa en expresiones de enlace para definir valores o valores de función para uno o más nombres. La forma más sencilla de la `let` expresión enlaza un nombre a un valor simple, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Si separa la expresión del identificador usando una nueva línea, debe aplicar sangría a cada línea de la expresión, como en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

En lugar de simplemente un nombre, se puede especificar un patrón que contenga nombres, por ejemplo, una tupla, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

El *cuerpo-expresión* es la expresión en la que se usan los nombres. La expresión de cuerpo aparece en su propia línea, con la sangría que se alinea exactamente con el primer carácter de `let` la palabra clave:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Un `let` enlace puede aparecer en el nivel de módulo, en la definición de un tipo de clase o en ámbitos locales, como en una definición de función. No `let` es necesario que un enlace en el nivel superior de un módulo o de un tipo de clase tenga una expresión de cuerpo, sino que en otros niveles de ámbito, se requiere la expresión del cuerpo. Los nombres enlazados se pueden usar después del punto de definición, pero no en ningún momento `let` antes de que aparezca el enlace, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Enlaces de función

Los enlaces de función siguen las reglas de los enlaces de valor, excepto que los enlaces de función incluyen el nombre de la función y los parámetros, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

En general, los parámetros son patrones, como un patrón de tupla:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Una `let` expresión de enlace se evalúa como el valor de la última expresión. Por lo tanto, en el ejemplo de código siguiente, `result` el valor de se `100 * function3 (1, 2)`calcula a partir de, `300`que se evalúa como.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Para obtener más información, vea [Funciones](index.md).

## <a name="type-annotations"></a>Anotaciones de tipo

Puede especificar los tipos para los parámetros incluyendo dos puntos (:) seguido de un nombre de tipo, todo entre paréntesis. También puede especificar el tipo del valor devuelto anexando los dos puntos y el tipo después del último parámetro. Las anotaciones de tipo completo para `function1`, con enteros como tipos de parámetro, serían como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Cuando no hay ningún parámetro de tipo explícito, se usa la inferencia de tipos para determinar los tipos de parámetros de las funciones. Esto puede incluir la generalización automática del tipo de un parámetro para que sea genérico.

Para obtener más información, vea [generalización automática](../generics/automatic-generalization.md) e inferencia de [tipos](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Enlaces let en clases

Un `let` enlace puede aparecer en un tipo de clase, pero no en un tipo de estructura o de registro. Para usar un enlace Let en un tipo de clase, la clase debe tener un constructor Primary. Los parámetros de constructor deben aparecer después del nombre de tipo en la definición de clase. Un `let` enlace en un tipo de clase define los campos privados y los miembros de ese tipo de clase `do` y, junto con los enlaces del tipo, crea el código para el constructor principal para el tipo. En los siguientes ejemplos de código se `MyClass` muestra una clase `field1` con `field2`campos privados y.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Los ámbitos de `field1` y `field2` se limitan al tipo en el que se declaran. Para obtener más información, vea [ `let` enlaces en clases](../members/let-bindings-in-classes.md) y [clases](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parámetros de tipo en los enlaces Let

Un `let` enlace en el nivel de módulo, en un tipo o en una expresión de cálculo puede tener parámetros de tipo explícitos. Un enlace Let en una expresión, como dentro de una definición de función, no puede tener parámetros de tipo. Para más información, vea [Genéricos](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Atributos en enlaces Let

Los atributos se pueden aplicar a los enlaces `let` de nivel superior de un módulo, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Ámbito y accesibilidad de los enlaces Let

El ámbito de una entidad declarada con un enlace Let está limitado a la parte del ámbito contenedor (por ejemplo, una función, un módulo, un archivo o una clase) después de que aparezca el enlace. Por lo tanto, se puede decir que un enlace Let introduce un nombre en un ámbito. En un módulo, se puede acceder a un valor o función enlazado a los clientes de un módulo siempre que se pueda acceder al módulo, ya que los enlaces Let de un módulo se compilan en funciones públicas del módulo. Por el contrario, los enlaces Let de una clase son privados para la clase.

Normalmente, las funciones de los módulos deben calificarse con el nombre del módulo cuando se usan en el código de cliente. Por ejemplo, si un módulo `Module1` tiene una función `function1`, los usuarios especificarán `Module1.function1` que hagan referencia a la función.

Los usuarios de un módulo pueden usar una declaración de importación para hacer que las funciones de ese módulo estén disponibles para su uso sin que el nombre del módulo los califique. En el ejemplo que se acaba de mencionar, los usuarios del módulo pueden, en ese caso, abrir el módulo mediante `Module1` la declaración de importación `function1` Open y, a continuación, hacer referencia directamente a.

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

Algunos módulos tienen el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), lo que significa que las funciones que exponen deben calificarse con el nombre del módulo. Por ejemplo, el F# módulo List tiene este atributo.

Para obtener más información sobre los módulos y el control de acceso, consulte [módulos](../modules.md) y [Access Control](../access-control.md).

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
- [`let` Bindings in Classes](../members/let-bindings-in-classes.md) (Enlaces `let` en clases)
