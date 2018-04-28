---
title: Celdas de referencia (F#)
description: 'Obtenga información acerca de cómo las celdas de referencia de F # son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencias.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e017adb2a031dff996892e2bb6585fc95f644ff9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="reference-cells"></a>Celdas de referencia

*Hacer referencia a las celdas* son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencias.

## <a name="syntax"></a>Sintaxis

```fsharp
ref expression
```

## <a name="remarks"></a>Comentarios
Se utiliza el operador `ref` antes de un valor para crear una nueva celda de referencia que encapsula el valor. A continuación, se puede cambiar el valor subyacente, porque es mutable.

Una celda de referencia contiene un valor real; no una mera dirección. Al crear una celda de referencia mediante el operador `ref`, se crea una copia del valor subyacente como valor mutable encapsulado.

Se puede desreferenciar una celda de referencia mediante el operador `!` (bang).

En el ejemplo de código siguiente se muestran la declaración y el uso de celdas de referencia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

El resultado es `50`

Las celdas de referencia son instancias del tipo de registro genérico `Ref`, que se declara como sigue.

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

El tipo `'a ref` es un sinónimo de `Ref<'a>`. Tanto el compilador como IntelliSense en el IDE, muestran el primero para este tipo, pero la definición subyacente es el segundo.

El operador `ref` crea una nueva celda de referencia. El código siguiente es la declaración del operador `ref`.

```fsharp
let ref x = { contents = x }
```

En la tabla siguiente se muestran las características que están disponibles en la celda de referencia.

|Operador, miembro o campo|Descripción|Tipo|de esquema JSON|
|--------------------------|-----------|----|----------|
|`!` (operador de desreferencia)|Devuelve el valor subyacente.|`'a ref -> 'a`|`let (!) r = r.contents`|
|`:=` (operador de asignación)|Cambia el valor subyacente.|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|`ref` (operador)|Encapsula un valor en una nueva celda de referencia.|`'a -> 'a ref`|`let ref x = { contents = x }`|
|`Value` (propiedad)|Obtiene o establece el valor subyacente.|`unit -> 'a`|`member x.Value = x.contents`|
|`contents` (campo de registro)|Obtiene o establece el valor subyacente.|`'a`|`let ref x = { contents = x }`|
Hay varias maneras de tener acceso al valor subyacente. El valor devuelto por el operador de desreferencia (`!`) no es un valor asignable. Por consiguiente, si se va a modificar el valor subyacente, se debe utilizar el operador de asignación (`:=`) en su lugar.

Tanto la propiedad `Value` como el campo `contents` son valores asignables. Así pues, se pueden utilizar para obtener acceso al valor subyacente o cambiarlo, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

La salida es la siguiente.

```
10
10
11
12
```

El campo `contents` se proporciona por motivos de compatibilidad con otras versiones de ML y generará una advertencia durante la compilación. Para deshabilitar la advertencia, utilice la opción `--mlcompatibility` del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).

El código siguiente muestra el uso de celdas de referencia al pasar parámetros. El tipo de Incrementor tiene un método Increment que toma un parámetro que incluye byref en el tipo de parámetro. Byref en el tipo de parámetro indica que los llamadores deben pasar una celda de referencia o la dirección de una variable típica del tipo especificado, en este caso int El resto del código muestra cómo llamar a incremento con ambos tipos de argumentos y muestra el uso del operador ref en una variable para crear una celda de referencia (ref myDelta1). A continuación, se muestra el uso del operador de dirección de (&amp;) para generar un argumento adecuado. Por último, el método Increment se llama de nuevo mediante el uso de una celda de referencia que se declara mediante un enlace let. La última línea del código muestra el uso de la! operador a fin de desreferenciar la celda de referencia para su impresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

Para obtener más información sobre cómo pasar por referencia, vea [parámetros y argumentos](parameters-and-arguments.md).

>[!NOTE]
Programadores de C# deben saber que ref funciona forma distinta en F # que en C#. Por ejemplo, el uso de ref cuando se pasa un argumento no tiene el mismo efecto en F # como ocurre en C#.

## <a name="consuming-c-ref-returns"></a>Utilizar en C# `ref` devuelve

A partir de F # 4.1, puedes utilizar `ref` devuelve generado en C#.  El resultado de una llamada de este tipo es un `byref<_>` puntero.

El siguiente método de C#:

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

Puede ser transparente llama F # con ninguna sintaxis especial:

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

También puede declarar funciones que pueden durar un `ref` devolver como entrada, por ejemplo:

```fsharp
let f (x: byref<int>) = &x
```

Actualmente no hay ninguna manera de generar un `ref` devuelto en F # que en C# que pueden consumir.

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Parámetros y argumentos](parameters-and-arguments.md)

[Referencia de símbolos y operadores](symbol-and-operator-reference/index.md)
