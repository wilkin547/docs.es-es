---
title: Enlaces let
description: Aprenda a usar un F# 'let' enlace, que asocia un identificador a un valor o una función.
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612678"
---
# <a name="let-bindings"></a>Enlaces let

Un *enlace* asocia un identificador a un valor o una función. Usa el `let` palabra clave para enlazar un nombre a un valor o una función.

## <a name="syntax"></a>Sintaxis

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Comentarios

El `let` palabra clave se usa en expresiones para definir los valores o valores de función para uno o más nombres de enlace. La forma más sencilla de la `let` expresión enlaza un nombre a un valor simple, como se indica a continuación.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Si la expresión del identificador de independientes mediante el uso de una nueva línea, debe aplicar sangría a cada línea de la expresión, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

En lugar de simplemente un nombre, se puede especificar un patrón que contiene los nombres, por ejemplo, una tupla, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

El *cuerpo de expresión* es la expresión en la que se usan los nombres. La expresión de cuerpo aparece en su propia línea, con una sangría a la línea exactamente con el primer carácter en el `let` palabra clave:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Un `let` enlace puede aparecer en el nivel de módulo, en la definición de un tipo de clase o en ámbitos locales, como se muestra en una definición de función. Un `let` enlace en el nivel en un módulo o en un tipo de clase superior no es necesario tener una expresión de cuerpo, pero en otros niveles de ámbito, se requiere la expresión de cuerpo. Los nombres enlazados son utilizables después del punto de definición, pero no en cualquier momento antes de la `let` enlace aparece, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Enlaces de función

Enlaces de función siguen las reglas para los enlaces de valor, excepto en que los enlaces de función incluyen el nombre de función y los parámetros, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

En general, los parámetros son patrones, como un modelo de tupla:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Un `let` enlazar la expresión se evalúa como el valor de la última expresión. Por lo tanto, en el ejemplo de código siguiente, el valor de `result` se calcula a partir `100 * function3 (1, 2)`, que se evalúa como `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Para obtener más información, vea [Funciones](index.md).

## <a name="type-annotations"></a>Anotaciones de tipo

Puede especificar tipos de parámetros mediante la inclusión de dos puntos (:) seguido por un nombre de tipo, escribir entre paréntesis. También puede especificar el tipo de valor devuelto anexando el signo de dos puntos y el tipo después del último parámetro. Las anotaciones de tipo completo de `function1`, con números enteros como tipos de parámetro, sería como sigue.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Cuando no hay ningún parámetro de tipo explícito, se usa la inferencia de tipos para determinar los tipos de parámetros de funciones. Esto puede incluir la generalización automática del tipo de un parámetro para ser genérico.

Para obtener más información, consulte [generalización automática](../generics/automatic-generalization.md) y [inferencia](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Enlaces let en clases

Un `let` enlace puede aparecer en un tipo de clase, pero no en una estructura o un tipo de registro. Para utilizar un enlace let en un tipo de clase, la clase debe tener un constructor primario. Los parámetros del constructor deben aparecer después del nombre de tipo en la definición de clase. Un `let` enlace en un tipo de clase define los campos privados y los miembros de ese tipo de clase y, junto con `do` formularios de enlaces en el tipo, el código para el constructor principal para el tipo. Los ejemplos de código siguiente muestran una clase `MyClass` con campos privados `field1` y `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Los ámbitos de `field1` y `field2` están limitados al tipo en el que se declaran. Para obtener más información, consulte [ `let` Bindings in Classes](../members/let-bindings-in-classes.md) y [clases](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parámetros de tipo en los enlaces let

Un `let` enlace en el nivel de módulo, en un tipo o en una expresión de cálculo puede tener parámetros de tipo explícito. Un enlace let en una expresión, como dentro de una definición de función, no puede tener parámetros de tipo. Para más información, vea [Genéricos](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Atributos en los enlaces let

Los atributos se pueden aplicar al nivel superior `let` enlaces en un módulo, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Ámbito y la accesibilidad de los enlaces Let

Se limita a la parte de la que contiene el ámbito de una entidad declarada con un enlace permiten definir el ámbito (por ejemplo, una función, módulo, archivo o clase) después de que aparezca el enlace. Por lo tanto, puede decir que un enlace let introduce un nombre en un ámbito. En un módulo, un valor enlazado a let o una función es accesible a los clientes de un módulo siempre que el módulo sea accesible, puesto que los enlaces let en un módulo se compilan en funciones públicas del módulo. Por el contrario, los enlaces let en una clase son privados para la clase.

Normalmente, las funciones de módulos deben calificarse con el nombre del módulo cuando se usa código de cliente. Por ejemplo, si un módulo `Module1` tiene una función `function1`, debería especificar los usuarios `Module1.function1` para hacer referencia a la función.

Los usuarios de un módulo pueden usar una declaración de importación para hacer que las funciones dentro de ese módulo disponibles para su uso sin que se está calificado con el nombre del módulo. En el ejemplo que acabo de mencionar, los usuarios del módulo en ese caso pueden abrir el módulo mediante la apertura de la declaración de importación `Module1` y después hacer referencia a `function1` directamente.

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

Algunos módulos tienen el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), lo que significa que las funciones que exponen se deben calificar con el nombre del módulo. Por ejemplo, el F# List (módulo) tiene este atributo.

Para obtener más información sobre los módulos y control de acceso, consulte [módulos](../modules.md) y [Control de acceso](../access-control.md).

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
- [`let` Bindings in Classes](../members/let-bindings-in-classes.md) (Enlaces `let` en clases)