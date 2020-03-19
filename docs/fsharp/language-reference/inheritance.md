---
title: Herencia
description: Obtenga información sobre cómo especificar las relaciones de herencia de F- mediante la palabra clave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401134"
---
# <a name="inheritance"></a>Herencia

La herencia se utiliza para modelar la relación "is-a", o subtipando, en la programación orientada a objetos.

## <a name="specifying-inheritance-relationships"></a>Especificación de relaciones de herencia

Las relaciones de `inherit` herencia se especifican mediante la palabra clave en una declaración de clase. La forma sintáctica básica se muestra en el ejemplo siguiente.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una clase puede tener como máximo una clase base directa. Si no especifica una clase base `inherit` mediante la palabra clave, `System.Object`la clase hereda implícitamente de .

## <a name="inherited-members"></a>Miembros heredados

Si una clase hereda de otra clase, los métodos y miembros de la clase base están disponibles para los usuarios de la clase derivada como si fueran miembros directos de la clase derivada.

Cualquier let enlaces y constructor parámetros son privados a una clase y, por lo tanto, no se puede tener acceso desde las clases derivadas.

La `base` palabra clave está disponible en clases derivadas y hace referencia a la instancia de clase base. Se utiliza como el autoidentificador.

## <a name="virtual-methods-and-overrides"></a>Métodos virtuales y modificaciones

Los métodos virtuales (y las propiedades) funcionan de forma algo diferente en F - en comparación con otros lenguajes .NET. Para declarar un nuevo miembro `abstract` virtual, utilice la palabra clave. Esto se hace independientemente de si se proporciona una implementación predeterminada para ese método. Por lo tanto, una definición completa de un método virtual en una clase base sigue este patrón:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Y en una clase derivada, una invalidación de este método virtual sigue este patrón:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Si omite la implementación predeterminada en la clase base, la clase base se convierte en una clase abstracta.

En el ejemplo de código siguiente se `function1` muestra la declaración de un nuevo método virtual en una clase base y cómo reemplazarlo en una clase derivada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Constructores y herencia

El constructor de la clase base debe llamarse en la clase derivada. Los argumentos del constructor de la clase `inherit` base aparecen en la lista de argumentos de la cláusula. Los valores que se utilizan deben determinarse a partir de los argumentos proporcionados al constructor de clase derivada.

El código siguiente muestra una clase base y una clase derivada, donde la clase derivada llama al constructor de la clase base en la cláusula inherit:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

En el caso de varios constructores, se puede usar el código siguiente. La primera línea de los constructores `inherit` de clase según lo éstos `val` es la cláusula y los campos aparecen como campos explícitos que se declaran con la palabra clave. Para obtener más información, consulte [Campos explícitos: `val` La palabra clave](./members/explicit-fields-the-val-keyword.md).

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

En los casos en que se requiere una modificación menor de un tipo, considere la posibilidad de usar una expresión de objeto como alternativa a la herencia. En el ejemplo siguiente se muestra el uso de una expresión de objeto como alternativa a la creación de un nuevo tipo derivado:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Para obtener más información acerca de las expresiones de objeto, vea [Expresiones de objeto](object-expressions.md).

Al crear jerarquías de objetos, considere la posibilidad de usar una unión discriminada en lugar de una herencia. Las uniones discriminadas también pueden modelar un comportamiento variado de diferentes objetos que comparten un tipo general común. Una sola unión discriminada a menudo puede eliminar la necesidad de un número de clases derivadas que son variaciones menores entre sí. Para obtener información sobre las uniones discriminadas, consulte [Uniones discriminadas](discriminated-unions.md).

## <a name="see-also"></a>Consulte también

- [Expresiones de objeto](object-expressions.md)
- [Referencia del lenguaje f](index.md)
