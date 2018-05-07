---
title: Valores NULL (F#)
description: 'Obtenga información acerca de cómo se usa el valor null en el lenguaje de programación de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 7367b35cb6e910f926179e52992d5533e5cdda0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="null-values"></a>Valores NULL

Este tema describe cómo se utiliza el valor null en F #.


## <a name="null-value"></a>Valor null
El valor null no se utiliza normalmente en F # para valores o variables. Sin embargo, null aparece como valor anormal en determinadas situaciones. Si se define un tipo de F #, no se permite null como un valor regular a menos que la [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) atributo se aplica al tipo. Si se define un tipo en otro lenguaje de. NET, null es un valor posible y, si está interoperando con estos tipos, el código de F # podría encontrar valores null.

Para un tipo definido en F # y usar estrictamente en F #, la única manera de crear un valor null directamente con la biblioteca de F # es usar [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Sin embargo, para un tipo de F # que se utilizan desde otros lenguajes. NET, o si se utiliza ese tipo con una API que no se escribe en F #, como .NET Framework, puede haber valores null.

Puede usar el `option` los tipos de F # cuándo se puede utilizar una variable de referencia con un posible valor null en otro lenguaje. NET. En lugar de null, con F # `option` tipo, use el valor de la opción `None` si no hay ningún objeto. Utilice el valor de la opción `Some(obj)` con un objeto `obj` cuando hay un objeto. Para obtener más información, consulte [opciones](../options.md).

El `null` palabra clave es una palabra clave válida en el lenguaje F #, y tendrá que usarla cuando se trabaja con la API de .NET Framework u otras API que se escribe en otro lenguaje. NET. Las dos situaciones en las que podría necesitar un valor null son al llamar a una API de .NET y pasar un valor null como argumento, y cuando interprete el valor devuelto o parámetro de salida de una llamada al método. NET.

Para pasar un valor null a un método. NET, puede utilizar el `null` palabra clave en el código de llamada. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Para interpretar un valor null que se obtiene de un método. NET, use la coincidencia de patrones, si es posible. En el ejemplo de código siguiente se muestra cómo utilizar la coincidencia de patrones para interpretar el valor null que se devuelve de `ReadLine` cuando intenta leer después del final de un flujo de entrada.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Valores NULL para los tipos de F # también pueden generarse de otras maneras, como cuando usa `Array.zeroCreate`, que llama `Unchecked.defaultof`. Debe tener cuidado con este código para mantener encapsulados los valores null. En una biblioteca diseñada únicamente para F #, no es necesario comprobar si hay valores null en cada función. Si está escribiendo una biblioteca para que interopere con otros lenguajes. NET, es posible que deba agregar comprueba si hay valores null, los parámetros de entrada y produce un `ArgumentNullException`, tal y como lo hace en el código de C# o Visual Basic.

Puede usar el código siguiente para comprobar si un valor arbitrario es null.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vea también
[Valores](index.md)

[Expresiones de coincidencia](../match-expressions.md)
