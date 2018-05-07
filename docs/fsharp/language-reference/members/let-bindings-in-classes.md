---
title: Enlaces let en clases (F#)
description: "Obtenga información acerca de cómo definir campos privados y funciones privadas para las clases de F # mediante enlaces 'let' en la definición de clase."
ms.date: 05/16/2016
ms.openlocfilehash: 1c17fe0edec14c28c9bdde86d0a2acb7c886cdf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="let-bindings-in-classes"></a>Enlaces let en clases

Puede definir campos privados y funciones privadas para las clases de F # mediante `let` enlaces en la definición de clase.


## <a name="syntax"></a>Sintaxis

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Comentarios
La sintaxis anterior aparece después de las declaraciones de encabezado y la herencia de clase pero antes de las definiciones de miembros. La sintaxis es similar al de `let` enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase. Un `let` enlace crea un campo privado o una función; para exponer los datos o funciones públicamente, declaran una propiedad o un método de miembro.

A `let` el enlace que no es estático se denomina una instancia `let` enlace. Instancia `let` enlaces ejecutan cuando se crean los objetos. Estática `let` enlaces forman parte del inicializador estático de la clase, que se garantiza que se ejecutará antes de que el tipo se usa por primera vez.

El código dentro de la instancia `let` enlaces puedan utilizar los parámetros del constructor primario.

No se permiten los atributos y modificadores de accesibilidad en `let` enlaces en clases.

Los ejemplos de código siguientes muestran varios tipos de `let` enlaces en clases.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

La salida es la siguiente.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Maneras alternativas de crear campos
También puede usar el `val` palabra clave que se va a crear un campo privado. Cuando se usa el `val` palabra clave, el campo no tiene un valor cuando se crea el objeto, pero en su lugar se inicializa con un valor predeterminado. Para obtener más información, consulte [campos explícitos: val (palabra clave)](explicit-fields-the-val-keyword.md).

También puede definir campos privados en una clase con una definición de miembro y agregando la palabra clave `private` a la definición. Esto puede ser útil si espera que cambie la accesibilidad de un miembro sin volver a escribir el código. Para más información, vea [Access Control](../access-control.md) (Control de acceso).

## <a name="see-also"></a>Vea también
[Miembros](index.md)

[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)

[`let` Enlaces](../functions/let-bindings.md)
