---
title: Enlaces do en clases
description: Aprenda a usar un F# 'do' enlace en una definición de clase, que realiza acciones cuando se construye el objeto o cuando se usa el tipo por primera vez.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddf2b5ca458d0950c2e07bf2c37c205877e2173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904597"
---
# <a name="do-bindings-in-classes"></a>Enlaces do en clases

Un `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para una variable static `do` enlace, cuando se usa el tipo en primer lugar.

## <a name="syntax"></a>Sintaxis

```fsharp
[static] do expression
```

## <a name="remarks"></a>Comentarios

Un `do` enlace aparece junto con, o después de `let` enlaces, pero antes de las definiciones de miembros en una definición de clase. Aunque el `do` es opcional para la palabra clave `do` enlaces en el nivel de módulo, no es opcional para `do` enlaces en una definición de clase.

Para la construcción de todos los objetos de cualquier dado el tipo, no estático `do` enlaces y no static `let` enlaces se ejecutan en el orden en que aparecen en la definición de clase. Varios `do` enlaces pueden producirse en un tipo. No estático `let` enlaces y que no sea estático `do` enlaces se convierten en el cuerpo del constructor principal. El código en el que no sea estático `do` sección de enlaces puede hacer referencia a los parámetros del constructor principal y los valores o funciones que se definen en el `let` sección de enlaces.

No estáticos `do` enlaces pueden tener acceso a los miembros de la clase como la clase tiene un identificador propio que se define mediante una `as` palabra clave en la clase de encabezado y siempre y cuando todos los usos de esos miembros se califican con el identificador propio para la clase.

Porque `let` enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros se comportan según lo previsto, `do` enlaces normalmente se colocan después `let` enlaces por lo que el código en el `do` enlace puede ejecutar con un objeto totalmente inicializado. Si el código intenta usar a un miembro antes de completar la inicialización, se produce una excepción InvalidOperationException.

Estática `do` enlaces pueden hacer referencia a miembros estáticos o campos de la envolvente clase pero no miembros o campos de instancia. Estática `do` enlaces pasan a formar parte del inicializador estático para la clase, que siempre se ejecutará antes de la clase se usa por primera vez.

Se omiten los atributos para `do` enlaces de tipos. Si un atributo no es necesario para el código que se ejecuta en un `do` de enlace, que debe aplicarse al constructor principal.

En el código siguiente, una clase tiene un estático `do` enlace y un nestatické `do` enlace. El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en el `let` enlaces para la clase. También se definen dos propiedades. Todos ellos están en el ámbito en el que no sea estático `do` sección de enlaces, tal como se muestra en la línea que imprime todos esos valores.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

La salida es la siguiente.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
- [Clases](../classes.md)
- [Constructores](constructors.md)
- [`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)
- [`do` enlaces](../functions/do-Bindings.md)