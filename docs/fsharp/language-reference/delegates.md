---
title: Delegados (F#)
description: "Obtenga información acerca de cómo trabajar con los delegados de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a>Delegados

Un delegado representa una llamada de función como un objeto. En F #, normalmente debe utilizar valores de función para representar las funciones como valores de primera clase; Sin embargo, los delegados se utilizan en .NET Framework y por lo que son necesarios al interoperar con las API que espera. También puede usar al crear bibliotecas diseñadas para usan en otros lenguajes de .NET Framework.


## <a name="syntax"></a>Sintaxis

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Comentarios
En la sintaxis anterior, `type1` representa el tipo de argumento o los tipos y `type2` representa el tipo de valor devuelto. Los tipos de argumentos que se representan mediante `type1` se currifican automáticamente. Esto sugiere para este tipo que se utiliza una forma de tupla si los argumentos de la función de destino se currificadas y una tupla entre paréntesis para los argumentos que ya están en el formulario de la tupla. La currificación automática quita un conjunto de paréntesis, si deja un argumento de tupla que coincide con el método de destino. Consulte el ejemplo de código para la sintaxis que debe usar en cada caso.

Los delegados se pueden adjuntar a los valores de función de F # y estáticos o métodos de instancia. Los valores de función de F # se pueden pasar directamente como argumentos para constructores delegados. Para un método estático, el delegado se construye utilizando el nombre de la clase y el método. Para un método de instancia, se proporcionan la instancia de objeto y el método en un argumento. En ambos casos, el miembro de operador de acceso a (`.`) se utiliza.

El `Invoke` método en el tipo de delegado llama a la función encapsulada. Además, los delegados se pueden pasar como valores de las funciones haciendo referencia al nombre del método Invoke sin los paréntesis.

El código siguiente muestra la sintaxis para crear delegados que representan varios métodos en una clase. Dependiendo de si el método es un método estático o un método de instancia y, si tiene argumentos en la tupla o el formulario currificado, la sintaxis para declarar y asignar al delegado es un poco diferente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

El código siguiente muestra algunas de las distintas maneras en que puede trabajar con los delegados.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

El resultado del ejemplo de código anterior es la siguiente.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Parámetros y argumentos](parameters-and-arguments.md)

[Eventos](members/events.md)
