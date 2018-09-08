---
title: Celdas de referencia (F#)
description: 'Obtenga información sobre cómo las celdas de referencia de F # son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencia.'
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192279"
---
# <a name="reference-cells"></a>Celdas de referencia

*Celdas de referencia* son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencia.

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

Los programadores de C# deben saber que `ref` en C# no es lo mismo que `ref` en F #. Las construcciones de F # equivalente son [zkratka](byrefs.md), que son un concepto diferente de las celdas de referencia.

Los valores marcan como `mutable`se pueden promover automáticamente a `'a ref` si captura una clausura; vea [valores](values/index.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Parámetros y argumentos](parameters-and-arguments.md)
- [Referencia de símbolos y operadores](symbol-and-operator-reference/index.md)
- [Valores](values/index.md)
