---
title: Sintaxis detallada
description: 'Obtenga información sobre la diferencia entre la sintaxis detallada y ligera en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4e1725b58c8cb67c074ba12fd4ca25ce0c000a1e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97595182"
---
# <a name="verbose-syntax"></a>Sintaxis detallada

Hay dos formas de sintaxis disponibles para muchas construcciones en el lenguaje F #: *Sintaxis detallada* y *Sintaxis ligera*. La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría. La sintaxis ligera es más corta y usa la sangría para indicar el principio y el final de las construcciones, en lugar de palabras clave adicionales como `begin` , `end` , `in` , etc. La sintaxis predeterminada es la sintaxis ligera. En este tema se describe la sintaxis de las construcciones de F # cuando la sintaxis ligera no está habilitada. La sintaxis detallada siempre está habilitada, por lo que incluso si habilita la sintaxis ligera, todavía puede usar la sintaxis detallada para algunas construcciones. Puede deshabilitar la sintaxis ligera mediante la `#light "off"` Directiva.

## <a name="table-of-constructs"></a>Tabla de construcciones

En la tabla siguiente se muestra la sintaxis ligera y detallada de las construcciones del lenguaje F # en contextos en los que hay una diferencia entre las dos formas. En esta tabla, los corchetes angulares ( &lt; &gt; ) encierran los elementos de sintaxis proporcionados por el usuario. Consulte la documentación de cada construcción de lenguaje para obtener información más detallada sobre la sintaxis utilizada en estas construcciones.

<table>
<tr>
<th>Construcción de lenguaje</th>
<th>Sintaxis ligera</th>
<th>Sintaxis detallada</th>
</tr>
<tr>
<td>
Expresiones compuestas
</td>
<td>

```fsharp
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

enlaces anidados `let`

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
bloque de código
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td>registro
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>class
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td>structure</td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>Unión discriminada</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>interfaz</td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>expresión de objeto</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>implementación de interfaces</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>extensión de tipo</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Directivas de compilador](compiler-directives.md)
- [Instrucciones de formato de código](../style-guide/formatting.md)
