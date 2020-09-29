---
title: 'Funciones recursivas: palabra clave rec'
description: "Obtenga información sobre cómo se usa la palabra clave ' Rec ' de F # con la palabra clave ' Let ' para definir una función recursiva."
ms.date: 08/12/2020
ms.openlocfilehash: 1ab00ff9400129e531fd7320861b3d9625cad08c
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438074"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funciones recursivas: palabra clave rec

La `rec` palabra clave se usa junto con la `let` palabra clave para definir una función recursiva.

## <a name="syntax"></a>Sintaxis

```fsharp
// Recursive function:
let rec function-nameparameter-list =
    function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
    function1-body

and function2-nameparameter-list =
    function2-body
...
```

## <a name="remarks"></a>Observaciones

Las funciones recursivas, que se llaman a sí mismas, se identifican explícitamente en el lenguaje F # con la `rec` palabra clave. La `rec` palabra clave hace que el nombre del `let` enlace esté disponible en su cuerpo.

En el ejemplo siguiente se muestra una función recursiva que *calcula el número*<sup>de Fibonacci</sup> con la definición matemática.

```fsharp
let rec fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> En la práctica, el código como el ejemplo anterior no es el ideal porque unecessarily vuelve a calcular los valores que ya se han calculado. Esto se debe a que no es recursivo, lo que se explica más adelante en este artículo.

Los métodos son implícitamente recursivos dentro del tipo en el que se definen, lo que significa que no es necesario agregar la `rec` palabra clave. Por ejemplo:

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

Sin embargo, los enlaces Let dentro de las clases no son implícitamente recursivos. Todas `let` las funciones enlazadas a requieren la `rec` palabra clave.

## <a name="tail-recursion"></a>Recursividad de cola

En el caso de algunas funciones recursivas, es necesario refactorizar una definición más "pura" a una que sea [recursiva](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion). Esto evita los cálculos innecesarios. Por ejemplo, el generador de números de Fibonacci anterior se puede volver a escribir de la siguiente manera:

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

Se trata de una implementación más complicada. La generación de un número de Fibonacci es un buen ejemplo de un algoritmo "naive" que es matemáticamente puro pero ineficaz en la práctica. Varios aspectos hacen que sea eficaz en F # mientras sigue estando definido de forma recursiva:

* Una función interna recursiva denominada `loop` , que es un patrón de idiomático F #.
* Dos parámetros de acumulador, que pasan los valores acumulados a las llamadas recursivas.
* Una comprobación del valor de `n` para devolver un acumulado específico.

Si este ejemplo se escribió de forma iterativa con un bucle, el código tendría un aspecto similar al de dos valores diferentes acumulados hasta que se cumpliera una condición determinada.

La razón por la que se trata de la finalización del error es que la llamada recursiva no tiene que guardar ningún valor en la pila de llamadas. Todos los valores intermedios que se calculan se acumulan a través de entradas de la función interna. Esto también permite que el compilador de F # optimice el código para que sea tan rápido como si hubiera escrito algo parecido a un `while` bucle.

Es habitual escribir código de F # que procese de forma recursiva algo con una función interna y externa, como se muestra en el ejemplo anterior. La función interna utiliza la recursividad de cola, mientras que la función externa tiene una interfaz mejor para los llamadores.

## <a name="mutually-recursive-functions"></a>Funciones mutuamente recursivas

A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otra que, a su vez, llama a la primera, con cualquier número de llamadas entre. Debe definir estas funciones juntas en un `let` enlace, utilizando la `and` palabra clave para vincularlas.

En el ejemplo siguiente se muestran dos funciones mutuamente recursivas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a>Valores recursivos

También puede definir un `let` valor enlazado a que sea recursivo. Esto se hace a veces para el registro. Con F # 5 y la `nameof` función, puede hacer lo siguiente:

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
