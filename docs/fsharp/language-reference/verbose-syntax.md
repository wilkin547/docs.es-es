---
title: Sintaxis detallada
description: Conozca la diferencia entre la sintaxis detallada y ligera en el lenguaje de programación de F.
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463907"
---
# <a name="verbose-syntax"></a><span data-ttu-id="95975-103">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="95975-103">Verbose Syntax</span></span>

<span data-ttu-id="95975-104">Hay dos formas de sintaxis disponibles para muchas construcciones en el lenguaje F: *sintaxis detallada* y *sintaxis ligera.*</span><span class="sxs-lookup"><span data-stu-id="95975-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="95975-105">La sintaxis detallada no es tan comúnmente utilizada, pero tiene la ventaja de ser menos sensible a la sangría.</span><span class="sxs-lookup"><span data-stu-id="95975-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="95975-106">La sintaxis ligera es más corta y utiliza la sangría para indicar el `begin` `end`principio `in`y el final de las construcciones, en lugar de palabras clave adicionales como , , , etc.</span><span class="sxs-lookup"><span data-stu-id="95975-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="95975-107">La sintaxis predeterminada es la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="95975-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="95975-108">En este tema se describe la sintaxis para las construcciones de F- cuando la sintaxis ligera no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="95975-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="95975-109">La sintaxis detallada siempre está habilitada, por lo que incluso si habilita la sintaxis ligera, todavía puede usar sintaxis detallada para algunas construcciones.</span><span class="sxs-lookup"><span data-stu-id="95975-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="95975-110">Puede deshabilitar la sintaxis `#light "off"` ligera mediante la directiva.</span><span class="sxs-lookup"><span data-stu-id="95975-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="95975-111">Tabla de Construcciones</span><span class="sxs-lookup"><span data-stu-id="95975-111">Table of Constructs</span></span>

<span data-ttu-id="95975-112">En la tabla siguiente se muestra la sintaxis ligera y detallada para las construcciones de lenguaje de F en contextos donde hay una diferencia entre los dos formularios.</span><span class="sxs-lookup"><span data-stu-id="95975-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="95975-113">En esta tabla, los&lt;&gt;corchetes angulares ( ) encierran los elementos de sintaxis proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="95975-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="95975-114">Consulte la documentación de cada construcción de lenguaje para obtener información más detallada sobre la sintaxis utilizada en estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="95975-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="95975-115">Construcción del lenguaje</span><span class="sxs-lookup"><span data-stu-id="95975-115">Language construct</span></span></th>
<th><span data-ttu-id="95975-116">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="95975-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="95975-117">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="95975-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="95975-118">expresiones compuestas</span><span class="sxs-lookup"><span data-stu-id="95975-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="95975-119">enlaces anidados `let`</span><span class="sxs-lookup"><span data-stu-id="95975-119">nested `let` bindings</span></span>

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
<span data-ttu-id="95975-120">bloque de código</span><span class="sxs-lookup"><span data-stu-id="95975-120">code block</span></span>
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
<tr><td><span data-ttu-id="95975-121">registro</span><span class="sxs-lookup"><span data-stu-id="95975-121">record</span></span>
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
<tr><td><span data-ttu-id="95975-122">clase</span><span class="sxs-lookup"><span data-stu-id="95975-122">class</span></span>
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
<tr><td><span data-ttu-id="95975-123">structure</span><span class="sxs-lookup"><span data-stu-id="95975-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-124">unión discriminada</span><span class="sxs-lookup"><span data-stu-id="95975-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-125">interfaz</span><span class="sxs-lookup"><span data-stu-id="95975-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-126">expresión de objeto</span><span class="sxs-lookup"><span data-stu-id="95975-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-127">implementación de interfaces</span><span class="sxs-lookup"><span data-stu-id="95975-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-128">tipo de extensión</span><span class="sxs-lookup"><span data-stu-id="95975-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="95975-129">module</span><span class="sxs-lookup"><span data-stu-id="95975-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="95975-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95975-130">See also</span></span>

- [<span data-ttu-id="95975-131">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="95975-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="95975-132">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="95975-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="95975-133">Instrucciones de formato de código</span><span class="sxs-lookup"><span data-stu-id="95975-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
