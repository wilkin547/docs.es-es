---
title: Delegados (F#)
description: 'Obtenga información sobre cómo trabajar con delegados en F #.'
ms.date: 05/16/2016
ms.openlocfilehash: be58997dffe8fcd949bbc2d47d86ffccc157d43e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45517101"
---
# <a name="delegates"></a>Delegados

Un delegado representa una llamada de función como un objeto. En F #, normalmente debe usar los valores de función para representar funciones como valores de primera clase; Sin embargo, los delegados se usan en .NET Framework y por lo que son necesarios al interactuar con las API que esperan. También puede usar al crear bibliotecas diseñadas para utilizan desde otros lenguajes de .NET Framework.

## <a name="syntax"></a>Sintaxis

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, `type1` representa el tipo de argumento o los tipos y `type2` representa el tipo de valor devuelto. Los tipos de argumento que se representan mediante `type1` se currifican automáticamente. Esto sugiere que, para este tipo que se utiliza una forma de tupla si están currificados los argumentos de la función de destino y una tupla entre paréntesis para los argumentos que ya están en forma de tupla. La currificación automática quita un conjunto de paréntesis, dejando un argumento de tupla que coincide con el método de destino. Consulte el ejemplo de código para la sintaxis que debe usar en cada caso.

Los delegados se pueden adjuntar a los valores de función de F # y estáticos o métodos de instancia. Los valores de función de F # se pueden pasar directamente como argumentos para delegar constructores. Para un método estático, el delegado se construye utilizando el nombre de la clase y el método. Para un método de instancia, debe proporcionar la instancia de objeto y el método en un argumento. En ambos casos, el miembro de operador de acceso a (`.`) se utiliza.

El `Invoke` método en el tipo de delegado llama a la función encapsulada. Además, los delegados se pueden pasar como valores de función indicando el nombre del método Invoke sin paréntesis.

El código siguiente muestra la sintaxis para crear delegados que representan varios métodos en una clase. Dependiendo de si el método es un método estático o un método de instancia y, si tiene argumentos en forma de tupla o currificada, la sintaxis para declarar y asignar al delegado es un poco diferente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

El código siguiente muestra algunas de las distintas formas en que puede trabajar con delegados.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

La salida de ejemplo de código anterior es como sigue.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Parámetros y argumentos](parameters-and-arguments.md)
- [Eventos](members/events.md)
