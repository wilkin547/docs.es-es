---
title: Enlaces let en clases
description: Obtenga información sobre cómo definir los campos privados y las F# funciones privadas para las clases mediante los enlaces ' Let ' en la definición de clase.
ms.date: 05/16/2016
ms.openlocfilehash: 0086d3a91f85395c2bd0555f978c5d951c363357
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627487"
---
# <a name="let-bindings-in-classes"></a>Enlaces let en clases

Puede definir campos privados y funciones privadas para F# las clases mediante el `let` uso de enlaces en la definición de clase.

## <a name="syntax"></a>Sintaxis

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Comentarios

La sintaxis anterior aparece después del encabezado de clase y las declaraciones de herencia, pero antes de cualquier definición de miembro. La sintaxis es similar a la `let` de los enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase. Un `let` enlace crea un campo o una función privados; para exponer datos o funciones públicamente, declare una propiedad o un método de miembro.

Un `let` enlace que no es estático se denomina enlace de `let` instancia. Los `let` enlaces de instancia se ejecutan cuando se crean los objetos. Los `let` enlaces estáticos forman parte del inicializador estático de la clase, que se garantiza que se ejecuta antes de que se use por primera vez el tipo.

El código incluido en `let` los enlaces de instancia puede usar los parámetros del constructor principal.

Los atributos y los modificadores de accesibilidad no `let` se permiten en los enlaces de clases.

En los siguientes ejemplos de código se muestran `let` varios tipos de enlaces en las clases.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

La salida es la siguiente.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Maneras alternativas de crear campos

También puede usar la `val` palabra clave para crear un campo privado. Cuando se usa `val` la palabra clave, el campo no recibe un valor cuando se crea el objeto, sino que se inicializa con un valor predeterminado. Para obtener más información, [vea campos explícitos: Palabra clave](explicit-fields-the-val-keyword.md)Val.

También puede definir campos privados en una clase utilizando una definición de miembro y agregando la palabra `private` clave a la definición. Esto puede ser útil si espera cambiar la accesibilidad de un miembro sin reescribir el código. Para más información, vea [Access Control](../access-control.md) (Control de acceso).

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
- [`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)
- [`let`Enlaces](../functions/let-bindings.md)
