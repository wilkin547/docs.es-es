---
title: Herencia
description: Obtenga información sobre cómo F# especificar las relaciones de herencia mediante la palabra clave ' inherit '.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627666"
---
# <a name="inheritance"></a>Herencia

La herencia se usa para modelar la relación "es-a", o subescribir, en la programación orientada a objetos.

## <a name="specifying-inheritance-relationships"></a>Especificar relaciones de herencia

Las relaciones de herencia se especifican `inherit` mediante la palabra clave en una declaración de clase. En el ejemplo siguiente se muestra la forma sintáctica básica.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una clase puede tener como máximo una clase base directa. Si no especifica una clase base mediante la `inherit` palabra clave, la clase hereda implícitamente de. `System.Object`

## <a name="inherited-members"></a>Miembros heredados

Si una clase hereda de otra clase, los métodos y miembros de la clase base están disponibles para los usuarios de la clase derivada como si fueran miembros directos de la clase derivada.

Los enlaces Let y los parámetros de constructor son privados para una clase y, por tanto, no se puede tener acceso a ellos desde clases derivadas.

La palabra `base` clave está disponible en las clases derivadas y hace referencia a la instancia de la clase base. Se usa como el identificador automático.

## <a name="virtual-methods-and-overrides"></a>Métodos virtuales e invalidaciones

Los métodos virtuales (y las propiedades) funcionan de F# manera ligeramente diferente en en comparación con otros lenguajes de .net. Para declarar un nuevo miembro virtual, use la `abstract` palabra clave. Esto se hace independientemente de si se proporciona una implementación predeterminada para ese método. Por lo tanto, una definición completa de un método virtual en una clase base sigue este patrón:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Y en una clase derivada, una invalidación de este método virtual sigue este patrón:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Si se omite la implementación predeterminada en la clase base, la clase base se convierte en una clase abstracta.

En el ejemplo de código siguiente se muestra la declaración de un nuevo `function1` método virtual en una clase base y cómo invalidarlo en una clase derivada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Constructores y herencia

Se debe llamar al constructor de la clase base en la clase derivada. Los argumentos para el constructor de clase base aparecen en la lista de argumentos `inherit` de la cláusula. Los valores que se utilizan se deben determinar a partir de los argumentos proporcionados al constructor de la clase derivada.

En el código siguiente se muestra una clase base y una clase derivada, donde la clase derivada llama al constructor de clase base en la cláusula inherit:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

En el caso de varios constructores, se puede usar el código siguiente. La primera línea de los constructores de la clase derivada `inherit` es la cláusula y los campos aparecen como campos explícitos que se declaran con la `val` palabra clave. Para obtener más información, [vea campos explícitos: `val` Palabra clave](./members/explicit-fields-the-val-keyword.md).

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>Alternativas a la herencia

En los casos en los que se requiere una modificación menor de un tipo, considere la posibilidad de usar una expresión de objeto como alternativa a la herencia. En el ejemplo siguiente se muestra el uso de una expresión de objeto como alternativa a la creación de un nuevo tipo derivado:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Para obtener más información sobre las expresiones de objeto, vea [expresiones de objeto](object-expressions.md).

Al crear jerarquías de objetos, considere la posibilidad de usar una Unión discriminada en lugar de la herencia. Las uniones discriminadas también pueden modelar el comportamiento variado de objetos diferentes que comparten un tipo general común. Una sola Unión discriminada a menudo puede eliminar la necesidad de una serie de clases derivadas que son variaciones secundarias unas de otras. Para obtener información sobre las uniones discriminadas, consulte [uniones discriminadas](discriminated-unions.md).

## <a name="see-also"></a>Vea también

- [Expresiones de objeto](object-expressions.md)
- [Referencia del lenguaje F#](index.md)
