---
title: Sintaxis detallada (F#)
description: 'Obtenga información sobre la diferencia entre la sintaxis ligera y detallado en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45647147"
---
# <a name="verbose-syntax"></a><span data-ttu-id="752fe-103">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="752fe-103">Verbose Syntax</span></span>

<span data-ttu-id="752fe-104">Hay dos formas de sintaxis disponibles para muchas construcciones del lenguaje F #: *sintaxis detallada* y *sintaxis ligera*.</span><span class="sxs-lookup"><span data-stu-id="752fe-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="752fe-105">La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría.</span><span class="sxs-lookup"><span data-stu-id="752fe-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="752fe-106">La sintaxis ligera es más corta y utiliza la sangría para señalar el principio y final de las construcciones, en lugar de palabras clave adicionales como `begin`, `end`, `in`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="752fe-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="752fe-107">La sintaxis predeterminada es la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="752fe-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="752fe-108">Este tema describe la sintaxis de construcciones de F # cuando no está habilitada la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="752fe-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="752fe-109">Sintaxis detallada siempre está habilitada, por lo que incluso si habilita la sintaxis ligera, todavía puede utilizar la sintaxis detallada para algunas construcciones.</span><span class="sxs-lookup"><span data-stu-id="752fe-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="752fe-110">Sintaxis ligera se puede deshabilitar mediante la `#light "off"` directiva.</span><span class="sxs-lookup"><span data-stu-id="752fe-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="752fe-111">Tabla de construcciones</span><span class="sxs-lookup"><span data-stu-id="752fe-111">Table of Constructs</span></span>

<span data-ttu-id="752fe-112">En la tabla siguiente muestra la sintaxis ligera y detallada para construcciones del lenguaje F # en contextos donde hay una diferencia entre las dos formas.</span><span class="sxs-lookup"><span data-stu-id="752fe-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="752fe-113">En esta tabla, los corchetes angulares (&lt;&gt;) incluya los elementos de la sintaxis proporcionada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="752fe-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="752fe-114">Consulte la documentación de cada construcción de lenguaje para obtener más información sobre la sintaxis usada dentro de estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="752fe-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="752fe-115">Construcción de lenguaje</span><span class="sxs-lookup"><span data-stu-id="752fe-115">Language construct</span></span></th>
<th><span data-ttu-id="752fe-116">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="752fe-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="752fe-117">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="752fe-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="752fe-118">expresiones compuestas</span><span class="sxs-lookup"><span data-stu-id="752fe-118">compound expressions</span></span>
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


<span data-ttu-id="752fe-119">anidada `let` enlaces</span><span class="sxs-lookup"><span data-stu-id="752fe-119">nested `let` bindings</span></span>

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
<span data-ttu-id="752fe-120">bloque de código</span><span class="sxs-lookup"><span data-stu-id="752fe-120">code block</span></span>
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
<tr><td><span data-ttu-id="752fe-121">record</span><span class="sxs-lookup"><span data-stu-id="752fe-121">record</span></span>
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
<tr><td><span data-ttu-id="752fe-122">clase</span><span class="sxs-lookup"><span data-stu-id="752fe-122">class</span></span>
</td><td><span data-ttu-id="752fe-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="752fe-123">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="752fe-124">estructura</span><span class="sxs-lookup"><span data-stu-id="752fe-124">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-125">unión discriminada</span><span class="sxs-lookup"><span data-stu-id="752fe-125">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-126">interfaz</span><span class="sxs-lookup"><span data-stu-id="752fe-126">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-127">expresión de objeto</span><span class="sxs-lookup"><span data-stu-id="752fe-127">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-128">implementación de interfaces</span><span class="sxs-lookup"><span data-stu-id="752fe-128">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-129">extensión de tipo</span><span class="sxs-lookup"><span data-stu-id="752fe-129">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="752fe-130">module</span><span class="sxs-lookup"><span data-stu-id="752fe-130">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="752fe-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="752fe-131">See also</span></span>

- [<span data-ttu-id="752fe-132">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="752fe-132">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="752fe-133">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="752fe-133">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="752fe-134">Instrucciones de formato de código</span><span class="sxs-lookup"><span data-stu-id="752fe-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
