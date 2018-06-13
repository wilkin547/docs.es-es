---
title: Sintaxis detallada (F#)
description: 'Obtenga información acerca de la diferencia entre la sintaxis ligera y detallado en el lenguaje de programación de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b0bed66b4a76c5ab11e6c9e7aaf695f864e74ca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563789"
---
# <a name="verbose-syntax"></a>Sintaxis detallada

Hay dos formas de sintaxis disponibles para muchas construcciones del lenguaje F #: *sintaxis detallada* y *sintaxis ligera*. La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría. La sintaxis ligera es más corta y utiliza la sangría para señalar el principio y final de las construcciones, en lugar de como palabras clave adicionales `begin`, `end`, `in`, y así sucesivamente. La sintaxis predeterminada es la sintaxis ligera. Este tema describe la sintaxis para las construcciones de F # cuando no está habilitada la sintaxis ligera. Sintaxis detallada siempre está habilitada, de modo que aunque se habilite la sintaxis ligera, todavía puede utilizar la sintaxis detallada para algunas construcciones. Sintaxis ligera se pueden deshabilitar mediante la `#light "off"` directiva.


## <a name="table-of-constructs"></a>Tabla de construcciones.
En la tabla siguiente muestra la sintaxis ligera y detallada para construcciones del lenguaje F # en contextos donde hay una diferencia entre las dos formas. En esta tabla, están entre corchetes angulares (&lt;&gt;) encerrar los elementos de sintaxis proporcionados por el usuario. Consulte la documentación de cada construcción de lenguaje para obtener más información acerca de la sintaxis utilizada dentro de estas construcciones.



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

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


anidada `let` enlaces

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
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

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
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

```
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

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td>record
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
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
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>estructura</td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>unión discriminada</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
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

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>expresión de objeto</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
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

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>extensión de tipo</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Directivas de compilador](compiler-directives.md)

[Instrucciones de formato de código](code-formatting-guidelines.md)
