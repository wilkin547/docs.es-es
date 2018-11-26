---
title: 'Administración de recursos: palabra clave use (F#)'
description: Obtenga información sobre la F# palabra clave 'use' y la función "using", que puede controlar la inicialización y la liberación de recursos.
ms.date: 05/16/2016
ms.openlocfilehash: 300fb4113019f676625f75541d117458eab3f6ab
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296885"
---
# <a name="resource-management-the-use-keyword"></a>Administración de recursos: palabra clave use

Este tema describe la palabra clave `use` y `using` función, que puede controlar la inicialización y la liberación de recursos.

## <a name="resources"></a>Recursos

El término *recursos* se usa en más de una forma. Sí, los recursos pueden ser datos que utiliza una aplicación, como cadenas, gráficos y similares, pero en este contexto, *recursos* hace referencia a los recursos de software o del sistema operativo, como los contextos de dispositivo de gráficos, identificadores de archivo, red y las conexiones, los objetos de simultaneidad como identificadores de espera etc. de la base de datos. El uso de estos recursos por aplicaciones implica la adquisición de recursos del sistema operativo o de otro proveedor de recursos, seguida de la versión posterior del recurso en el grupo para que se puede proporcionar a otra aplicación. Se producen problemas cuando las aplicaciones no liberan recursos al grupo comunes.

## <a name="managing-resources"></a>Administrar recursos

Para forma responsable y eficazmente administrar recursos en una aplicación, se deben liberar los recursos de una manera predecible y con prontitud. .NET Framework le ayuda a hacer esto proporcionando la `System.IDisposable` interfaz. Un tipo que implementa `System.IDisposable` tiene la `System.IDisposable.Dispose` método, que libera los recursos correctamente. Las aplicaciones bien escritas garantizar que `System.IDisposable.Dispose` se llama con prontitud cuando ya no se necesita cualquier objeto que contiene un recurso limitado. Afortunadamente, la mayoría de los lenguajes de .NET proporciona soporte técnico para facilitar esta tarea, y F# es ninguna excepción. Hay dos construcciones de lenguaje útiles que admiten el patrón de dispose: el `use` enlace y el `using` función.

## <a name="use-binding"></a>Usar el enlace

El `use` palabra clave tiene un formato similar de la `let` enlace:

usar *valor* = *expresión*

Proporciona la misma funcionalidad que un `let` enlace pero agrega una llamada a `Dispose` en el valor cuando el valor se sale del ámbito. Tenga en cuenta que el compilador inserta una comprobación de null en el valor, por lo que si el valor es `null`, la llamada a `Dispose` no se ha intentado.

El ejemplo siguiente muestra cómo cerrar un archivo automáticamente con el `use` palabra clave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> Puede usar `use` en expresiones de cálculo, en cuyo caso una versión personalizada de la `use` se usa la expresión. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).

## <a name="using-function"></a>uso de la función

El `using` función tiene el formato siguiente:

`using` (*expression1*) *función o expresión lambda*

En un `using` expresión, *expression1* crea el objeto que debe eliminarse. El resultado de *expression1* (el objeto que se debe eliminar) se convierte en un argumento, *valor*a *función o lambda*, que es una función que espera un único restante de argumento de un tipo que coincide con el valor generado por *expression1*, o una expresión lambda que espera un argumento de ese tipo. Al final de la ejecución de la función, el runtime llama a `Dispose` y libera los recursos (a menos que el valor es `null`, en cuyo caso no se intenta realizar la llamada a Dispose).

En el ejemplo siguiente se muestra el `using` expresión con una expresión lambda.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

El ejemplo siguiente se muestra el `using` expresión con una función.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Tenga en cuenta que la función podría ser una función que tiene algunos argumentos ya aplicados. El siguiente ejemplo de código muestra esto. Se crea un archivo que contiene la cadena `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

El `using` función y el `use` enlace son prácticamente equivalentes formas de conseguir lo mismo. El `using` palabra clave proporciona más control sobre cuándo `Dispose` se llama. Cuando usas `using`, `Dispose` se llama al final de la función o expresión lambda; cuando se usa el `use` palabra clave, `Dispose` se llama al final del bloque de código que lo contiene. En general, es preferible usar `use` en lugar de la `using` función.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
