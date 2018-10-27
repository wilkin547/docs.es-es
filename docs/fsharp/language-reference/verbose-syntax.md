---
title: Sintaxis detallada (F#)
description: 'Obtenga información sobre la diferencia entre la sintaxis ligera y detallado en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: e697c6fe619df7ffe12f7d4e2a234a5a5cb401ff
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044768"
---
# <a name="verbose-syntax"></a>Sintaxis detallada

Hay dos formas de sintaxis disponibles para muchas construcciones del lenguaje F #: *sintaxis detallada* y *sintaxis ligera*. La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría. La sintaxis ligera es más corta y utiliza la sangría para señalar el principio y final de las construcciones, en lugar de palabras clave adicionales como `begin`, `end`, `in`, y así sucesivamente. La sintaxis predeterminada es la sintaxis ligera. Este tema describe la sintaxis de construcciones de F # cuando no está habilitada la sintaxis ligera. Sintaxis detallada siempre está habilitada, por lo que incluso si habilita la sintaxis ligera, todavía puede utilizar la sintaxis detallada para algunas construcciones. Sintaxis ligera se puede deshabilitar mediante la `#light "off"` directiva.

## <a name="table-of-constructs"></a>Tabla de construcciones

En la tabla siguiente muestra la sintaxis ligera y detallada para construcciones del lenguaje F # en contextos donde hay una diferencia entre las dos formas. En esta tabla, los corchetes angulares (&lt;&gt;) incluya los elementos de la sintaxis proporcionada por el usuario. Consulte la documentación de cada construcción de lenguaje para obtener más información sobre la sintaxis usada dentro de estas construcciones.

<table>
<tr>
<th>Construcción de lenguaje</th>
<th>Sintaxis ligera</th>
<th>Sintaxis detallada</th>
</tr>
<tr>
<td>
expresiones compuestas
</td>
<td>

```xml
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

anidada `let` enlaces

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

```
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
<tr><td>record
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
<tr><td>clase
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
<tr><td>estructura</td><td>

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
<tr><td>unión discriminada</td><td>

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
- [Instrucciones de formato de código](code-formatting-guidelines.md)
