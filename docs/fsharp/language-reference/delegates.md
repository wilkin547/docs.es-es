---
title: Delegados
description: Obtenga información sobre cómo trabajar con delegados en F#.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630371"
---
# <a name="delegates"></a>Delegados

Un delegado representa una llamada de función como un objeto. En F#, normalmente debería usar valores de función para representar funciones como valores de primera clase; sin embargo, los delegados se usan en el .NET Framework y, por tanto, son necesarios cuando se interoperan con las API que los esperan. También se pueden usar al crear bibliotecas diseñadas para su uso desde otros lenguajes .NET Framework.

## <a name="syntax"></a>Sintaxis

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, `type1` representa el tipo de argumento o los `type2` tipos y representa el tipo de valor devuelto. Los tipos de argumento que se representan `type1` mediante se convierten automáticamente en currificados. Esto sugiere que, para este tipo, se usa un formato de tupla si los argumentos de la función de destino son currificados y una tupla entre paréntesis para los argumentos que ya están en el formato de tupla. La currificación automática quita un conjunto de paréntesis y mantiene un argumento de tupla que coincide con el método de destino. Consulte el ejemplo de código para la sintaxis que se debe usar en cada caso.

Los delegados se F# pueden adjuntar a valores de función y métodos estáticos o de instancia. F#los valores de función se pueden pasar directamente como argumentos a los constructores de delegado. Para un método estático, se construye el delegado utilizando el nombre de la clase y el método. Para un método de instancia, debe proporcionar la instancia de objeto y el método en un argumento. En ambos casos, se utiliza el operador de`.`acceso a miembros ().

El `Invoke` método en el tipo de delegado llama a la función encapsulada. Además, los delegados se pueden pasar como valores de función haciendo referencia al nombre del método de invocación sin los paréntesis.

En el código siguiente se muestra la sintaxis para crear delegados que representan varios métodos de una clase. Dependiendo de si el método es un método estático o un método de instancia, y si tiene argumentos en el formato de tupla o en el formato currificados, la sintaxis para declarar y asignar el delegado es un poco diferente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

En el código siguiente se muestran algunas de las distintas formas en que puede trabajar con los delegados.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

La salida del ejemplo de código anterior es la siguiente.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Parámetros y argumentos](parameters-and-arguments.md)
- [Eventos](./members/events.md)
