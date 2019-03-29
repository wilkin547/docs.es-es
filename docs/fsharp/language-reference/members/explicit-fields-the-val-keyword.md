---
title: 'Campos explícitos: Val (palabra clave)'
description: Obtenga información sobre la F# palabra clave 'val', que se utiliza para declarar una ubicación para almacenar un valor en un tipo de clase o estructura sin inicializar el tipo.
ms.date: 05/16/2016
ms.openlocfilehash: 6557514f13a9e86c7f367713775535db79e99a0c
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634016"
---
# <a name="explicit-fields-the-val-keyword"></a>Campos explícitos: Val (palabra clave)

La palabra clave `val` se usa para declarar una ubicación para almacenar un valor en un tipo de clase o estructura sin inicializarlo. Ubicaciones de almacenamiento que se declaran de esta manera se denominan *campos explícitos*. Otra manera de usar la palabra clave `val` es conjuntamente con la palabra clave `member` para declarar una propiedad implementada automáticamente. Para obtener más información sobre las propiedades autoimplementadas, vea [propiedades](properties.md).

## <a name="syntax"></a>Sintaxis

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Comentarios

La forma más habitual de definir campos en un tipo de clase o estructura es usar un enlace `let`. Sin embargo, los enlaces `let` deben inicializarse como parte del constructor de clase, lo que no siempre es posible, necesario o deseable. Puede usar la palabra clave `val` cuando quiera un campo que no se haya inicializado.

Los campos explícitos pueden ser estáticos o no estáticos. El *modificador de acceso* puede ser `public`, `private`, o `internal`. De forma predeterminada, los campos explícitos son públicos. Esto difiere de los enlaces `let` de las clases, que siempre son privados.

El [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) atributo es necesario en los campos explícitos en tipos de clase que tienen un constructor primario. Este atributo especifica que el campo se inicializa en cero. El tipo del campo debe admitir la inicialización en cero. Los tipos que admiten la inicialización en cero son los siguientes:

- Un tipo primitivo que tenga un valor de cero.

- Un tipo que admita un valor nulo, ya sea como valor normal, como valor anormal o como representación de un valor. Esto incluye clases, tuplas, registros, funciones, interfaces, tipos de referencia .NET, el tipo `unit` y tipos de unión discriminada.

- Un tipo de valor. NET.

- Una estructura cuyos campos admitan el valor cero predeterminado.

Por ejemplo, un campo inmutable denominado `someField` tiene un campo de respaldo en la representación compilada de .NET con el nombre `someField@` y el usuario accede al valor almacenado con una propiedad denominada `someField`.

Para un campo mutable, la representación compilada de .NET es un campo .NET.

>[!WARNING]
>El espacio de nombres de .NET Framework `System.ComponentModel` contiene un atributo que tiene el mismo nombre. Para obtener más información sobre el atributo, vea `System.ComponentModel.DefaultValueAttribute`.

El código siguiente muestra el uso de campos explícitos y, para la comparación, un `let` de enlace en una clase que tiene un constructor primario. Tenga en cuenta que el campo enlazado a `let``myInt1` es privado. Si se hace referencia al campo enlazado a `let``myInt1` desde un método de miembro, el identificador propio `this` no es necesario. Pero si hace referencia a los campos explícitos `myInt2` y `myString`, se requiere el identificador propio.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

La salida es la siguiente:

```
11 12 abc
30 def
```

En el código siguiente se muestra el uso de campos explícitos en una clase que no tiene constructor primario. En este caso, el atributo `DefaultValue` no es necesario, pero todos los campos deben estar inicializados en los constructores definidos para el tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

El resultado es `35 22`

En el código siguiente se muestra el uso de campos explícitos en una estructura. Como una estructura es un tipo de valor, automáticamente tiene un constructor predeterminado que establece los valores de sus campos en cero. Por lo tanto, el atributo `DefaultValue` no es necesario.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

El resultado es `11 xyz`

**Tenga en cuenta**, si va a inicializar la estructura con `mutable` campos sin `mutable` palabra clave, las asignaciones de funcionará en una copia de la estructura que se descartarán justo después de la asignación. Por lo tanto, no cambiará su estructura.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6704.fs)]

Los campos explícitos no están pensados para un uso rutinario. En general, siempre que sea posible debe usar un enlace `let` en una clase en lugar de un campo explícito. Los campos explícitos son útiles en determinados escenarios de interoperabilidad, como cuando se necesita definir una estructura que se usará en una llamada de invocación a una plataforma API nativa o en escenarios de interoperabilidad COM. Para obtener más información, consulte [funciones externas](../functions/external-functions.md). Otra situación en la que podría ser necesario un campo explícito es cuando se trabaja con un generador de código F # que emite clases sin un constructor primario. Los campos explícitos también son útiles para las variables de subproceso estático o construcciones similares. Para obtener más información, consulta `System.ThreadStaticAttribute`.

Cuando las palabras clave `member val` aparecen juntas en una definición de tipo, se trata de la definición de una propiedad implementada automáticamente. Para obtener más información, consulta [Propiedades](properties.md).

## <a name="see-also"></a>Vea también

- [Propiedades](properties.md)
- [Miembros](index.md)
- [`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)
