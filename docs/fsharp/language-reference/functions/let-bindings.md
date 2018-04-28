---
title: Enlaces let (F#)
description: "Obtenga información acerca de cómo usar un 'let' enlace, que asocia un identificador a un valor o una función de F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 2abc4e05f9f2977501f01f745062e2e7cd611f68
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings"></a>Enlaces let

A *enlace* asocia un identificador a un valor o una función. Usa el `let` palabra clave que se va a enlazar un nombre a un valor o una función.

## <a name="syntax"></a>Sintaxis

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Comentarios

El `let` palabra clave se utiliza en expresiones para definir valores o valores de función para uno o más nombres de enlace. La forma más sencilla de la `let` expresión enlaza un nombre a un valor simple, como se indica a continuación.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Si se separa la expresión del identificador mediante una línea nueva, debe aplicar sangría a cada línea de la expresión, como en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

En lugar de simplemente un nombre, se puede especificar un patrón que contiene los nombres, por ejemplo, una tupla, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

El *cuerpo de la expresión* es la expresión en la que se utilizan los nombres. La expresión de cuerpo aparece en su propia línea, con una sangría a la línea exactamente con el primer carácter de la `let` palabra clave:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Un `let` enlace puede aparecer en el nivel de módulo, en la definición de un tipo de clase o en ámbitos locales, como se muestra en una definición de función. Un `let` enlace en el nivel en un módulo o en un tipo de clase superior no es necesario tener una expresión de cuerpo, pero en otros niveles de ámbito, se requiere la expresión del cuerpo. Los nombres enlazados son utilizables después del punto de definición, pero no en cualquier momento antes de la `let` aparece el enlace, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a>Enlaces de función

Enlaces de función siguen las reglas para los enlaces de valor, salvo que los enlaces de función incluyen el nombre de función y los parámetros, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

En general, los parámetros son patrones, como un tupla (modelo):

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Un `let` enlace expresión se evalúa como el valor de la última expresión. Por lo tanto, en el ejemplo de código siguiente, el valor de `result` se calcula a partir `100 * function3 (1, 2)`, que se evalúa como `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Para obtener más información, vea [Funciones](index.md).

## <a name="type-annotations"></a>Anotaciones de tipo

Puede especificar tipos para los parámetros mediante la inclusión de un signo de dos puntos (:) seguido por un nombre de tipo, encerrado entre paréntesis. También puede especificar el tipo del valor devuelto anexando el signo de dos puntos y el tipo después del último parámetro. Las anotaciones de tipo completo para `function1`, con enteros como tipos de parámetro, sería como sigue.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Cuando no hay ningún parámetro de tipo explícito, se utiliza la inferencia de tipos para determinar los tipos de parámetros de funciones. Esto puede incluir la generalización automática del tipo de un parámetro para ser genérico.

Para obtener más información, consulte [generalización automática](../generics/automatic-generalization.md) y [inferencia de tipo](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Enlaces let en clases

Un `let` enlace puede aparecer en un tipo de clase pero no en una estructura o un tipo de registro. Para utilizar un enlace let en un tipo de clase, la clase debe tener un constructor primario. Parámetros de constructor deben aparecer después del nombre de tipo en la definición de clase. A `let` enlace en un tipo de clase define los campos privados y los miembros de ese tipo de clase y, junto con `do` enlaces en el tipo, forma el código para el constructor primario para el tipo. Los ejemplos de código siguientes muestran una clase `MyClass` con campos privados `field1` y `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Los ámbitos de `field1` y `field2` se limitan al tipo en el que se declaran. Para obtener más información, consulte [ `let` enlaces en clases](../members/let-bindings-in-classes.md) y [clases](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parámetros de tipo en los enlaces let

Un `let` enlace en el nivel de módulo, en un tipo o en una expresión de cálculo puede tener parámetros de tipo explícito. Un enlace let en una expresión, como en una definición de función, no puede tener parámetros de tipo. Para más información, vea [Genéricos](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Atributos en los enlaces let

Atributos pueden aplicarse al nivel superior `let` enlaces en un módulo, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a>Ámbito y la accesibilidad de los enlaces Let

El ámbito de una entidad declarada con un enlace que se limita a la parte de la que contiene el ámbito (por ejemplo, una función, módulo, archivo o clase) después de que aparezca el enlace. Por lo tanto, puede considerarse que un enlace que introduce un nombre en un ámbito. En un módulo, una función o el valor de límite permiten es accesible para los clientes de un módulo siempre que el módulo sea accesible, puesto que los enlaces let en un módulo se compilan en funciones públicas del módulo. Por el contrario, los enlaces let en una clase son privados para la clase.

Normalmente, las funciones de módulos deben calificarse con el nombre del módulo cuando se usa un código de cliente. Por ejemplo, si un módulo `Module1` tiene una función `function1`, debería especificar los usuarios `Module1.function1` para hacer referencia a la función.

Los usuarios de un módulo pueden utilizar una declaración de importación para que las funciones dentro de ese módulo estén disponibles para su uso sin está calificada por el nombre del módulo. En el ejemplo que se acaban de mencionar, los usuarios del módulo en ese caso pueden abrir el módulo mediante la declaración de importación open `Module1` y después hacer referencia a `function1` directamente.

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

Algunos módulos tienen el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), lo que significa que las funciones que exponen se deben calificar con el nombre del módulo. Por ejemplo, el módulo de F # lista tiene este atributo.

Para obtener más información sobre módulos y control de acceso, consulte [módulos](../modules.md) y [el Control de acceso](../access-control.md).

## <a name="see-also"></a>Vea también

[Funciones](index.md)

[`let` Bindings in Classes](../members/let-bindings-in-classes.md) (Enlaces `let` en clases)
