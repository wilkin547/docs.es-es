---
title: Enlaces let en clases (F#)
description: "Obtenga información sobre cómo definir los campos privados y funciones privadas para las clases de F # mediante el uso de enlaces 'let' en la definición de clase."
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866798"
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

La sintaxis anterior aparece después de las declaraciones de encabezado y la herencia de clase, pero antes de las definiciones de miembros. La sintaxis es similar de `let` enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito que está limitado a la clase. Un `let` enlace crea un campo privado o una función; para exponer los datos o funciones públicamente, declaran una propiedad o un método de miembro.

Un `let` el enlace que no es estático se llama a una instancia `let` enlace. Instancia `let` enlaces ejecutan cuando se crean los objetos. Estática `let` enlaces forman parte del inicializador estático de la clase, que siempre se ejecutará antes de que el tipo se usa por primera vez.

El código dentro de la instancia `let` enlaces pueden usar los parámetros del constructor principal.

No se permiten los atributos y modificadores de accesibilidad en `let` enlaces en clases.

Los ejemplos de código siguientes muestran varios tipos de `let` enlaces en clases.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

La salida es la siguiente.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Maneras alternativas de crear campos

También puede usar el `val` palabra clave para crear un campo privado. Cuando se usa el `val` palabra clave, el campo no tiene un valor cuando se crea el objeto, pero en su lugar se inicializa con un valor predeterminado. Para obtener más información, consulte [campos explícitos: val (palabra clave)](explicit-fields-the-val-keyword.md).

También puede definir los campos privados en una clase mediante una definición de miembro y agregar la palabra clave `private` a la definición. Esto puede ser útil si piensa cambiar la accesibilidad de un miembro sin tener que reescribir el código. Para más información, vea [Access Control](../access-control.md) (Control de acceso).

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
- [`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)
- [`let` enlaces](../functions/let-bindings.md)
