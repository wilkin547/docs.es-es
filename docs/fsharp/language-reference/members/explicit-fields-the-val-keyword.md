---
title: 'Campos explícitos: palabra clave val'
description: "Obtenga información sobre la palabra clave ' Val ' de F #, que se usa para declarar una ubicación para almacenar un valor en un tipo de clase o estructura sin inicializar el tipo."
ms.date: 08/15/2020
ms.openlocfilehash: 9f5599a241f27b234eeacf48327b4ccbc46ed38c
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811787"
---
# <a name="explicit-fields-the-val-keyword"></a>Campos explícitos: palabra clave val

La palabra clave `val` se usa para declarar una ubicación para almacenar un valor en un tipo de clase o estructura sin inicializarlo. Las ubicaciones de almacenamiento declaradas de esta manera se denominan *campos explícitos*. Otra manera de usar la palabra clave `val` es conjuntamente con la palabra clave `member` para declarar una propiedad implementada automáticamente. Para obtener más información sobre las propiedades implementadas automáticamente, vea [propiedades](properties.md).

## <a name="syntax"></a>Sintaxis

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Comentarios

La forma más habitual de definir campos en un tipo de clase o estructura es usar un enlace `let`. Sin embargo, los enlaces `let` deben inicializarse como parte del constructor de clase, lo que no siempre es posible, necesario o deseable. Puede usar la palabra clave `val` cuando quiera un campo que no se haya inicializado.

Los campos explícitos pueden ser estáticos o no estáticos. El *modificador de acceso* puede ser `public` , `private` o `internal` . De forma predeterminada, los campos explícitos son públicos. Esto difiere de los enlaces `let` de las clases, que siempre son privados.

El atributo [DefaultValue](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-defaultvalueattribute.html) es necesario en los campos explícitos de los tipos de clase que tienen un constructor primario. Este atributo especifica que el campo se inicializa en cero. El tipo del campo debe admitir la inicialización en cero. Los tipos que admiten la inicialización en cero son los siguientes:

- Un tipo primitivo que tenga un valor de cero.
- Un tipo que admita un valor nulo, ya sea como valor normal, como valor anormal o como representación de un valor. Esto incluye clases, tuplas, registros, funciones, interfaces, tipos de referencia .NET, el tipo `unit` y tipos de unión discriminada.
- Un tipo de valor. NET.
- Una estructura cuyos campos admitan el valor cero predeterminado.

Por ejemplo, un campo inmutable denominado `someField` tiene un campo de respaldo en la representación compilada de .NET con el nombre `someField@` y el usuario accede al valor almacenado con una propiedad denominada `someField`.

Para un campo mutable, la representación compilada de .NET es un campo .NET.

> [!WARNING]
> El espacio de nombres .NET Framework `System.ComponentModel` contiene un atributo con el mismo nombre. Para obtener más información sobre el atributo, vea <xref:System.ComponentModel.DefaultValueAttribute>.

El código siguiente muestra el uso de campos explícitos y, para la comparación, un `let` de enlace en una clase que tiene un constructor primario. Tenga en cuenta que el campo enlazado a `let``myInt1` es privado. Si se hace referencia al campo enlazado a `let``myInt1` desde un método de miembro, el identificador propio `this` no es necesario. Pero si hace referencia a los campos explícitos `myInt2` y `myString`, se requiere el identificador propio.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

La salida es como sigue:

```console
11 12 abc
30 def
```

En el código siguiente se muestra el uso de campos explícitos en una clase que no tiene constructor primario. En este caso, el atributo `DefaultValue` no es necesario, pero todos los campos deben estar inicializados en los constructores definidos para el tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

La salida es `35 22`.

En el código siguiente se muestra el uso de campos explícitos en una estructura. Dado que una estructura es un tipo de valor, tiene automáticamente un constructor sin parámetros que establece los valores de sus campos en cero. Por lo tanto, el atributo `DefaultValue` no es necesario.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

La salida es `11 xyz`.

Tenga **cuidado**, si va a inicializar la estructura con `mutable` campos sin `mutable` palabra clave, las asignaciones funcionarán en una copia de la estructura que se descartará justo después de la asignación. Por lo tanto, la estructura no cambiará.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6704.fs)]

Los campos explícitos no están pensados para un uso rutinario. En general, siempre que sea posible debe usar un enlace `let` en una clase en lugar de un campo explícito. Los campos explícitos son útiles en determinados escenarios de interoperabilidad, como cuando se necesita definir una estructura que se usará en una llamada de invocación a una plataforma API nativa o en escenarios de interoperabilidad COM. Para obtener más información, vea [funciones externas](../functions/external-functions.md). Otra situación en la que podría ser necesario un campo explícito es cuando se trabaja con un generador de código F # que emite clases sin un constructor primario. Los campos explícitos también son útiles para las variables de subproceso estático o construcciones similares. Para obtener más información, vea `System.ThreadStaticAttribute`.

Cuando las palabras clave `member val` aparecen juntas en una definición de tipo, se trata de la definición de una propiedad implementada automáticamente. Para obtener más información, consulta [Propiedades](properties.md).

## <a name="see-also"></a>Consulte también

- [Propiedades](properties.md)
- [Miembros](index.md)
- [`let` Enlaces en clases](let-bindings-in-classes.md)
