---
title: Herencia
description: Obtenga información sobre cómo especificar F# relaciones de herencia con la palabra clave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: 2fad2ddafbc0174903d3d24be3ce5412f7e1f9ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641818"
---
# <a name="inheritance"></a>Herencia

La herencia se usa para modelar la relación "es un", o los subtipos en la programación orientada a objetos.

## <a name="specifying-inheritance-relationships"></a>Especificar relaciones de herencia

Especificar relaciones de herencia mediante el `inherit` palabra clave en una declaración de clase. El formulario sintáctico básico se muestra en el ejemplo siguiente.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una clase puede tener a lo sumo una clase base directa. Si no especifica una clase base mediante el uso de la `inherit` palabra clave, la clase hereda de forma implícita de `System.Object`.

## <a name="inherited-members"></a>Miembros heredados

Si una clase hereda de otra clase, los métodos y miembros de la clase base están disponibles para los usuarios de la clase derivada como si fueran miembros directos de la clase derivada.

Todos los enlaces let y los parámetros del constructor son privados para una clase y, por lo tanto, no es accesible desde las clases derivadas.

La palabra clave `base` está disponible en las clases derivadas y hace referencia a la instancia de la clase base. Se usa como identificador de la automática.

## <a name="virtual-methods-and-overrides"></a>Métodos virtuales y reemplazos

Los métodos virtuales (y propiedades) funcionan de forma ligeramente diferente en F# en comparación con otros lenguajes. NET. Para declarar un nuevo miembro virtual, utilice el `abstract` palabra clave. Para ello, independientemente de si se proporciona una implementación predeterminada para ese método. Por lo tanto, una definición completa de un método virtual en una clase base sigue este patrón:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Y en una clase derivada, una invalidación de este método virtual sigue este patrón:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Si se omite la implementación predeterminada de la clase base, la clase base se convierte en una clase abstracta.

El ejemplo de código siguiente muestra la declaración de un nuevo método virtual `function1` en una clase base y cómo reemplazarla en una clase derivada.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Constructores y herencia

Debe llamarse al constructor de la clase base en la clase derivada. Los argumentos para el constructor de clase base aparecen en la lista de argumentos en la `inherit` cláusula. Los valores que se usan deben determinarse a partir de los argumentos proporcionados al constructor de clase derivada.

El código siguiente muestra una clase base y una clase derivada, donde la clase derivada llama al constructor de clase base en la cláusula heredar:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

En el caso de varios constructores, se puede usar el código siguiente. La primera línea de los constructores de clase derivada es la `inherit` cláusula y los campos aparecen como campos explícitos que se declaran con la `val` palabra clave. Para obtener más información, consulte [campos explícitos: El `val` palabra clave](members/explicit-fields-the-val-keyword.md).

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

En casos donde se requiere una modificación menor de un tipo, considere el uso de una expresión de objeto como una alternativa a la herencia. El ejemplo siguiente muestra el uso de una expresión de objeto como una alternativa para crear un nuevo tipo derivado:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Para obtener más información sobre las expresiones de objeto, vea [expresiones de objeto](object-expressions.md).

Al crear las jerarquías de objetos, considere la posibilidad de usar una unión discriminada en lugar de herencia. Las uniones discriminadas también pueden modelar un comportamiento variado de diferentes objetos que comparten un tipo global común. Una unión discriminada única a menudo puede eliminar la necesidad de un número de clases derivadas que son pequeñas variaciones entre sí. Para obtener información sobre las uniones discriminadas, vea [uniones discriminadas](discriminated-unions.md).

## <a name="see-also"></a>Vea también

- [Expresiones de objeto](object-expressions.md)
- [Referencia del lenguaje F#](index.md)
