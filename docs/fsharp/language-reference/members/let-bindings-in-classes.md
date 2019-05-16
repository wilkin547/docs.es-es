---
title: Enlaces let en clases
description: Obtenga información sobre cómo definir los campos privados y funciones privadas para F# clases mediante el uso de 'let' enlaces en la definición de clase.
ms.date: 05/16/2016
ms.openlocfilehash: 29f843e3e065837a53fd5eb26c79088bc0778c76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645173"
---
# <a name="let-bindings-in-classes"></a>Enlaces let en clases

Puede definir campos privados y funciones privadas para F# clases mediante el uso de `let` enlaces en la definición de clase.

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

También puede usar el `val` palabra clave para crear un campo privado. Cuando se usa el `val` palabra clave, el campo no tiene un valor cuando se crea el objeto, pero en su lugar se inicializa con un valor predeterminado. Para obtener más información, consulte [campos explícitos: Val (palabra clave)](explicit-fields-the-val-keyword.md).

También puede definir los campos privados en una clase mediante una definición de miembro y agregar la palabra clave `private` a la definición. Esto puede ser útil si piensa cambiar la accesibilidad de un miembro sin tener que reescribir el código. Para más información, vea [Access Control](../access-control.md) (Control de acceso).

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
- [`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)
- [`let` enlaces](../functions/let-bindings.md)
