---
title: 'Administración de recursos: La palabra clave use'
description: Obtenga información sobre F# la palabra clave ' use ' y la función ' Using ', que puede controlar la inicialización y liberación de los recursos.
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627258"
---
# <a name="resource-management-the-use-keyword"></a>Administración de recursos: La palabra clave use

En este tema se describe `use` la palabra `using` clave y la función, que puede controlar la inicialización y la liberación de los recursos.

## <a name="resources"></a>Recursos

El término *recurso* se utiliza en más de una manera. Sí, los recursos pueden ser datos que una aplicación utiliza, como cadenas, gráficos y similares, pero en este contexto, *los recursos* hacen referencia a recursos de software o del sistema operativo, como contextos de dispositivo gráficos, identificadores de archivo, red y base de datos. conexiones, objetos de simultaneidad, como identificadores de espera, etc. El uso de estos recursos por parte de las aplicaciones implica la adquisición del recurso desde el sistema operativo u otro proveedor de recursos, seguido de la versión posterior del recurso al grupo para que se pueda proporcionar a otra aplicación. Se producen problemas cuando las aplicaciones no liberan recursos de nuevo en el grupo común.

## <a name="managing-resources"></a>Administrar recursos

Para administrar de forma eficaz y eficaz los recursos de una aplicación, debe liberar los recursos de forma rápida y predecible. El .NET Framework le ayuda a hacerlo proporcionando la `System.IDisposable` interfaz. Un tipo que implementa `System.IDisposable` tiene el `System.IDisposable.Dispose` método, que libera los recursos correctamente. La garantía de aplicaciones bien escritas garantiza que `System.IDisposable.Dispose` se llama al método rápidamente cuando ya no se necesita cualquier objeto que tenga un recurso limitado. Afortunadamente, la mayoría de los lenguajes .NET proporcionan compatibilidad para facilitar F# esta tarea y no es ninguna excepción. Hay dos construcciones de lenguaje útiles que admiten el patrón de Dispose `use` : el enlace `using` y la función.

## <a name="use-binding"></a>usar enlace

La `use` palabra clave tiene un formato similar al `let` del enlace:

usar*expresión* de *valor* = 

Proporciona la misma funcionalidad que un `let` enlace pero agrega una llamada a `Dispose` en el valor cuando el valor sale del ámbito. Tenga en cuenta que el compilador inserta una comprobación nula en el valor, de modo que `null`si el valor es `Dispose` , no se intenta la llamada a.

En el ejemplo siguiente se muestra cómo cerrar un archivo automáticamente mediante la `use` palabra clave.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> Puede usar `use` en expresiones de cálculo, en cuyo caso se utiliza una versión personalizada de `use` la expresión. Para obtener más información, vea [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y expresiones de [cálculo](computation-expressions.md).

## <a name="using-function"></a>Using (función)

La `using` función tiene el formato siguiente:

`using`(*expression1*) *función o lambda*

En una `using` expresión, *expression1* crea el objeto que se debe desechar. El resultado de *expression1* (el objeto que se debe desechar) se convierte en un argumento, *valor*, en *función o expresión lambda*, que es una función que espera un único argumento restante de un tipo que coincida con el valor generado por  *expression1*, o una expresión lambda que espera un argumento de ese tipo. Al final de la ejecución de la función, el tiempo de ejecución `Dispose` llama a y libera los recursos (a menos que `null`el valor sea, en cuyo caso no se intenta la llamada a Dispose).

En el ejemplo siguiente se `using` muestra la expresión con una expresión lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

En el ejemplo siguiente se `using` muestra la expresión con una función.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Tenga en cuenta que la función puede ser una función que ya tiene algunos argumentos aplicados. El siguiente ejemplo de código muestra esto. Crea un archivo que contiene la cadena `XYZ`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

La `using` función y el `use` enlace son formas casi equivalentes de lograr lo mismo. La `using` palabra clave proporciona más control sobre `Dispose` Cuándo se llama a. Cuando se usa `using`, `Dispose` se llama al final de la función o expresión lambda; cuando se usa la `use` palabra clave, `Dispose` se llama al final del bloque de código contenedor. En general, es preferible usar `use` en lugar de la `using` función.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
