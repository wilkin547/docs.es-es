---
title: Enlaces do en clases (F#)
description: "Obtenga información acerca de cómo usar un 'do' enlace en una definición de clase, que lleva a cabo acciones cuando se construye el objeto o cuando se utiliza primero el tipo de F #."
ms.date: 05/16/2016
ms.openlocfilehash: 779b33c44b1518135f4c7f270173ec8124fec101
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565196"
---
# <a name="do-bindings-in-classes"></a>Enlaces do en clases

A `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para una variable static `do` enlace, cuando se usa el tipo en primer lugar.


## <a name="syntax"></a>Sintaxis

```fsharp
[static] do expression
```

## <a name="remarks"></a>Comentarios
A `do` enlace aparece junto con o después de `let` enlaces pero antes de las definiciones de miembro en una definición de clase. Aunque la `do` palabra clave es opcional para `do` enlaces en el nivel de módulo, no es opcional para `do` enlaces en una definición de clase.

Para la construcción de todos los objetos de cualquier tipo, no estático determinado `do` enlaces y no estático `let` enlaces se ejecutan en el orden en que aparecen en la definición de clase. Varios `do` enlaces pueden producirse en un tipo. No estático `let` enlaces y no estático `do` enlaces se convierten en el cuerpo del constructor primario. El código de no estático `do` sección de enlaces puede hacer referencia a los parámetros del constructor primario y los valores o funciones que se definen en la `let` sección de enlaces.

No estáticos `do` enlaces pueden tener acceso a los miembros de la clase siempre y cuando la clase tiene un identificador propio que se define mediante una `as` palabra clave en la clase de encabezado y, a continuación, siempre y cuando todos los usos de esos miembros se califican con el identificador propio para la clase.

Porque `let` enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros se comportan según lo esperado, `do` enlaces normalmente se colocan después `let` enlaces para que el código en el `do` can de enlace ejecutar con un objeto totalmente inicializado. Si el código intenta utilizar a un miembro antes de que finalice la inicialización, se produce una excepción InvalidOperationException.

Estática `do` enlaces pueden hacer referencia a miembros estáticos o campos de los clase pero no los miembros o campos de instancia. Estática `do` enlaces pasan a formar parte del inicializador estático de la clase, que se garantiza que se ejecutará antes de que se usa la clase por primera vez.

Se omiten los atributos para `do` los enlaces de tipos. Si un atributo no es necesario para el código que se ejecuta en un `do` de enlace, se debe aplicar al constructor primario.

En el código siguiente, una clase tiene una variable static `do` enlace y no estático `do` enlace. El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en el `let` enlaces para la clase. También se definen dos propiedades. Todas ellas están en ámbito no estático `do` sección de enlaces, tal y como se muestra en la línea que imprime todos esos valores.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

La salida es la siguiente.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Vea también
[Miembros](index.md)

[Clases](../classes.md)

[Constructores](constructors.md)

[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)

[`do` Enlaces](../functions/do-Bindings.md)
