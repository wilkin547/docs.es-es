---
title: "Administración de recursos: palabra clave use (F#)"
description: "Obtenga información acerca de la F # palabra clave 'use' y la función 'con', que puede controlar la inicialización y la liberación de recursos."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a>Administración de recursos: palabra clave use

Este tema describe la palabra clave `use` y `using` función, que puede controlar la inicialización y la liberación de recursos.

## <a name="resources"></a>Recursos
El término *recursos* se utiliza en más de una forma. Sí, los recursos pueden ser datos que utiliza una aplicación, como cadenas, gráficos y similares, pero en este contexto, *recursos* hace referencia a los recursos de software o sistema operativo, como los contextos de dispositivo de gráficos, identificadores de archivo, red y las conexiones, objetos de simultaneidad, como los identificadores de espera etc. de la base de datos. El uso de estos recursos en aplicaciones implica la adquisición del recurso desde el sistema operativo u otro proveedor de recursos, seguido de la versión posterior del recurso para el grupo de manera que puede asignarse a otra aplicación. Se producen problemas cuando las aplicaciones no liberan recursos del grupo común.

## <a name="managing-resources"></a>Administrar recursos
Para responsable y eficazmente administrar recursos en una aplicación, debe liberar recursos inmediatamente y de una manera predecible. .NET Framework le ayuda a hacer esto proporcionando la `System.IDisposable` interfaz. Un tipo que implementa `System.IDisposable` tiene la `System.IDisposable.Dispose` método, que libera los recursos correctamente. Aplicaciones bien programadas garantizan que `System.IDisposable.Dispose` se llama inmediatamente cuando ya no es necesario ningún objeto que contiene un recurso limitado. Afortunadamente, la mayoría de los lenguajes de .NET proporciona compatibilidad para facilitar esta tarea, y F # no es ninguna excepción. Hay dos construcciones de lenguaje útiles que admiten el patrón de dispose: el `use` enlace y la `using` (función).

## <a name="use-binding"></a>utilizar el enlace
El `use` palabra clave tiene un formato similar de la `let` enlace:

usar *valor* = *expresión*

Proporciona la misma funcionalidad que un `let` enlace pero agrega una llamada a `Dispose` en el valor cuando el valor se sale del ámbito. Tenga en cuenta que el compilador inserta una comprobación de valores null en el valor, por lo que si el valor es `null`, la llamada a `Dispose` no se intenta realizar.

En el ejemplo siguiente se muestra cómo cerrar un archivo automáticamente mediante el uso de la `use` (palabra clave).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
Puede usar `use` en las expresiones de cálculo, en cuyo caso una versión personalizada de la `use` se utiliza la expresión. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).


## <a name="using-function"></a>uso de la función
El `using` función tiene la forma siguiente:

`using`(*expression1*) *función o expresión lambda*

En un `using` expresión, *expression1* crea el objeto que se debe eliminar. El resultado de *expression1* (es decir, el objeto que se debe eliminar) se convierte en un argumento, *valor*a *función o expresión lambda*, que es una función que espera un único restante argumento de tipo que coincide con el valor generado por *expression1*, o una expresión lambda que espera un argumento de ese tipo. Al final de la ejecución de la función, el runtime llama a `Dispose` y libera los recursos (a menos que el valor es `null`, en cuyo caso no se intenta realizar la llamada a Dispose).

En el ejemplo siguiente se muestra el `using` expresión con una expresión lambda.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

El siguiente ejemplo se muestra la `using` expresión con una función.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Tenga en cuenta que la función podría ser una función que tiene algunos argumentos ya aplicados. En el ejemplo de código siguiente se muestra cómo hacerlo. Se crea un archivo que contiene la cadena `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

El `using` función y el `use` enlace son maneras casi equivalentes para lograr lo mismo. El `using` palabra clave proporciona mayor control sobre cuándo `Dispose` se llama. Cuando usas `using`, `Dispose` se llama al final de la función o expresión lambda; cuando se usa el `use` palabra clave, `Dispose` se llama al final del bloque de código que lo contiene. En general, debería prefieren usar `use` en lugar de la `using` (función).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
