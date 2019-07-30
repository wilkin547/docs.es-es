---
title: Enlaces do en clases
description: Obtenga información sobre cómo usar F# un enlace ' do ' en una definición de clase, que realiza acciones cuando se construye el objeto o cuando se usa el tipo por primera vez.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627587"
---
# <a name="do-bindings-in-classes"></a>Enlaces do en clases

Un `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para un `do` enlace estático, cuando se usa por primera vez el tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
[static] do expression
```

## <a name="remarks"></a>Comentarios

Un `do` enlace aparece junto con los enlaces `let` o después, pero antes de las definiciones de miembro en una definición de clase. Aunque la `do` palabra clave es opcional `do` para los enlaces en el nivel de módulo, no es opcional `do` para los enlaces en una definición de clase.

Para la construcción de cada objeto de un tipo determinado, los enlaces no `do` estáticos y los enlaces no `let` estáticos se ejecutan en el orden en que aparecen en la definición de clase. Pueden `do` producirse varios enlaces en un tipo. Los enlaces no estáticos `let` y los enlaces no estáticos `do` se convierten en el cuerpo del constructor principal. El código de la sección de enlaces `do` no estáticos puede hacer referencia a los parámetros del constructor principal y a los valores o funciones que `let` se definen en la sección de enlaces.

Los enlaces no `do` estáticos pueden tener acceso a los miembros de la clase siempre que la clase tenga un identificador propio definido por una `as` palabra clave en el encabezado de la clase, y siempre y cuando todos los usos de esos miembros estén calificados con el propio identificador de la clase.

Dado `let` que los enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros `do` se comportan según lo `let` esperado, los enlaces normalmente se colocan después de los enlaces para que el `do` código del enlace pueda Ejecute con un objeto completamente inicializado. Si el código intenta utilizar un miembro antes de que se complete la inicialización, se genera una excepción InvalidOperationException.

Los `do` enlaces estáticos pueden hacer referencia a los miembros o campos estáticos de la clase envolvente, pero no a los miembros o campos de instancia. Los `do` enlaces estáticos forman parte del inicializador estático de la clase, que se garantiza que se ejecuta antes de que se use por primera vez la clase.

Los atributos se omiten para `do` los enlaces de los tipos. Si se requiere un atributo para el código que se ejecuta en `do` un enlace, debe aplicarse al constructor principal.

En el código siguiente, una clase tiene un enlace `do` estático y un enlace no estático `do` . El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en los `let` enlaces de la clase. También se definen dos propiedades. Todos se encuentran en el ámbito de la sección de enlaces `do` no estáticos, como se muestra en la línea que imprime todos esos valores.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

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
- [`do`Enlaces](../functions/do-Bindings.md)
